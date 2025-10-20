![[Pasted image 20241013233302.png]]
여기서는 이제 뭘 할거냐면 이전에 lec4, lec5에서 다뤘던 VAE를 한단계 더 발전시킨 F1VAE, 그러니까 VAE with first order function에 대해서 다룰거임.
근데 당연히 first order function에 대해서 먼저 다루겠지?
![[Pasted image 20241013233423.png]]
그래서 first order function이 뭔지 배우고, Concrete syntax랑 abstract syntax에 대해서 배울거임. 그리고나서 Interpreter를 구현할거고 scoping까지맛보기로 잠깐.
![[Pasted image 20241013233517.png]]
그래서 First order function이 뭐냐?
스칼라에서 같은 유형의 계산을 할때 함수를 정의해서 중복을 피하잖어.
그래서 함수는
1. 함수 이름이 필요하다.
2. 함수 인자들의 리스트가 필요하다.
3. 함수를 구성하는 body가 필요하다.
![[Pasted image 20241013233639.png]]
뭐 이건 봐도 바로 알것이고. 그래서 이걸 어케 구현할건데?
![[Pasted image 20241013235102.png]]
F1VAE는 function definition부분과 Expression부분, 두가지로 나뉘어짐.
F1VAE에서 사용되는 function은 single parameter임.
expression부분을 function을 활용하는 쪽으로 확장할거임.
![[Pasted image 20241014005757.png]]
그래서 Concrete syntax는 다음과 같음.
program은 function definition들의 나열과 expression으로 이루어져있음.
function definition은 function name(id)와 function parameter(id) 이후의 expression으로 구성됨.
그리고 expression의 한 종류로써 function application의 형태가 들어감.
![[Pasted image 20241014010004.png]]
Program은 Fundef들의 List와 expr로 이루어지고, FunDef는 함수이름, parameter, body로 이루어짐.
그리고 Expr에 함수가 적용되는 App가 추가됨.
![[Pasted image 20241014032549.png]]
위와 같은 프로그램이면 다음과 같이 파싱되어서 AST가 생성된다.
![[Pasted image 20241014032647.png]]
그래서 어떻게 평가할건데?
add3랑 mul2의 function definition을 어떻게 찾을건데 ㅋㅋ
![[Pasted image 20241014032724.png]]
VAE에서는 Variable이 들어간 Expression을 평가하기 위해, Variable이 어디에 대응되는지에 대한 environment $\sigma$를 들고다니면서 평가했음.
마찬가지로 F1VAE에서는 Function을 찾기 위해 Function environment $\Lambda$를 들고다님.
![[Pasted image 20241014034022.png]]
F1VAE program에서는 Function definition의 리스트랑 Expr만 있지, Function environment $\Lambda$가 있지는 않음.
그러면 어떻게 Function definition의 리스트를 가지고 $\Lambda$를 만드냐고?
foldLeft함수를 사용한다.
> [!gpt]
> **`foldLeft`**는 리스트를 **초기 값(Map.empty)**에서 시작하여, 각 요소(`fdef`)를 처리하면서 하나의 결과(`fenv`)를 축적하는 함수입니다. 이 경우, 초기 값은 **빈 함수 환경(Map.empty)**이고, 각 함수 정의(`fdef`)를 처리하여 함수 환경(`fenv`)을 업데이트합니다.
https://medium.com/@mohitdaxini75/scala-fold-functions-74d9d4c088a7
> [!NOTE] 
> **foldLeft:**  
The foldLeft function applies a binary operation to the elements of a collection, starting from a specified initial value and combining the elements from left to right. The signature of foldLeft is as follows: 
def foldLeft[B](z: B)(op: (B, A) => B): B
Here, z is the initial value and op is the binary operation that combines the elements. The foldLeft function starts with the initial value z and applies the operation op to each element of the collection, accumulating the result. The final result is the accumulated value.

설명 요약
- **목적**: `createFEnv` 함수는 함수 정의 리스트(`List[FunDef]`)를 받아서, 각 함수 이름을 함수 정의에 매핑하는 함수 환경(`FEnv`)을 생성합니다.
- **중요한 점**: 중복된 함수 이름이 있을 경우, **에러**를 발생시킵니다.
- **foldLeft**: 함수 정의 리스트를 순차적으로 처리하며, 초기 빈 함수 환경에서 시작하여 각 함수를 환경에 추가하는 방식으로 새로운 함수 환경을 생성합니다.
![[Pasted image 20241014050235.png]]
interpreter구현하고 당연히 sementics정의해야됨.
![[Pasted image 20241014051758.png]]
나머지는 lec5랑 똑같고 잘 읽어보셈.

> [!gpt]

이 슬라이드는 **함수 적용(Function Application)**에 대한 내용을 설명하고 있습니다. 함수 적용은 주어진 함수와 인수를 평가하여, 함수의 본문을 인수로 대체한 후 그 결과를 평가하는 과정입니다. 이 과정은 **함수 환경(Function Environment, `FEnv`)**을 활용하여 이루어집니다.

이 슬라이드에서는 함수 적용이 **인터프리터(`interp`)**에서 어떻게 처리되는지, 그리고 이와 관련된 **자연 의미론(natural semantics)**이 어떻게 정의되는지 보여주고 있습니다. 각 부분을 자세히 설명하겠습니다.

---

### 1. **함수 적용 케이스의 `interp` 함수**

```scala
def interp(expr: Expr, env: Env, fenv: FEnv): Value = expr match
  ...
  case App(f, e) =>
    val fdef = fenv.getOrElse(f, error(s"unknown function: $f"))
    interp(fdef.body, Map(fdef.param -> interp(e, env, fenv)), fenv)
```

#### 인터프리터에서 함수 적용 처리

- **`App(f, e)`**는 함수 적용을 나타내는 표현식입니다. `f`는 **함수 이름**, `e`는 **함수에 전달할 인수**입니다.
  
1. **함수 정의 검색 (`fenv.getOrElse`)**:
   - 먼저 함수 이름 `f`를 **함수 환경(`fenv`)**에서 찾아 해당 함수 정의(`fdef`)를 얻어옵니다. 
   - 만약 함수 환경에서 이름 `f`에 해당하는 함수 정의를 찾을 수 없으면, **"unknown function"** 에러를 발생시킵니다.

2. **인수 평가 및 환경 확장 (`interp(e, env, fenv)`)**:
   - 인수 `e`는 먼저 평가됩니다. 즉, 표현식 `e`를 **현재 환경(`env`)**과 **함수 환경(`fenv`)**에서 평가하여 결과 값을 얻습니다.
   - 그런 다음, **새로운 환경을 생성**하는데, 이 환경은 함수 정의에서 정의된 파라미터(`fdef.param`)를 인수 값에 매핑하는 **확장된 환경(Map)**입니다.

3. **함수 본문 평가 (`interp(fdef.body, ...)`)**:
   - 최종적으로, 함수의 본문(`fdef.body`)을 **새롭게 확장된 환경**에서 평가합니다.
   - 이 때, 함수 환경(`fenv`)은 그대로 유지하면서 본문을 평가합니다.

#### 요약
이 코드에서는 함수를 적용할 때 함수 환경에서 함수 정의를 찾고, 인수를 평가한 후 그 결과로 확장된 새로운 환경에서 함수 본문을 평가하는 방식으로 동작합니다.

---

### 2. **자연 의미론 (Natural Semantics)**

아래의 수식은 함수 적용이 어떻게 평가되는지를 자연 의미론을 통해 보여줍니다.

#### 함수 적용 자연 의미론:

$$
\frac{x_0 \in \text{Domain}(\Lambda) \quad \Lambda(x_0) = \text{def } x_0(x_1) = e_2 \quad \sigma, \Lambda \vdash e_1 \Rightarrow n_1 \quad \sigma[x_1 \mapsto n_1], \Lambda \vdash e_2 \Rightarrow n_2}{\sigma, \Lambda \vdash x_0(e_1) \Rightarrow n_2}
$$

#### 설명:

1. **함수 정의와 인수 평가**:
   - 함수 이름 $x_0$이 함수 환경($\Lambda$)에 존재해야 합니다.
   - $\Lambda(x_0) = \text{def } x_0(x_1) = e_2$는 함수 $x_0$이 파라미터 $x_1$을 받고, 본문이 $e_2$인 함수로 정의되었음을 의미합니다.

2. **인수 평가**:
   - $\sigma, \Lambda \vdash e_1 \Rightarrow n_1$는 현재 환경($\sigma$)과 함수 환경($\Lambda$)에서 인수 $e_1$을 평가한 결과가 $n_1$임을 의미합니다.

3. **확장된 환경에서 함수 본문 평가**:
   - 함수 파라미터 $x_1$을 인수 값 $n_1$에 바인딩한 확장된 환경($\sigma[x_1 \mapsto n_1]$)에서 함수 본문 $e_2$를 평가합니다.
   - $\sigma[x_1 \mapsto n_1], \Lambda \vdash e_2 \Rightarrow n_2$는 확장된 환경에서 본문 $e_2$를 평가한 결과가 $n_2$임을 의미합니다.

4. **최종 평가**:
   - 결국, 함수 적용 $x_0(e_1)$의 결과는 $n_2$입니다. 즉, 인수 $e_1$을 평가하여 함수 파라미터 $x_1$에 바인딩한 후, 함수 본문을 평가한 결과가 최종 결과가 됩니다.

---

### 요약

이 슬라이드는 **함수 적용**이 어떻게 이루어지는지 설명합니다.

1. 인터프리터 코드(`interp`)에서는 함수 이름을 함수 환경(FEnv)에서 찾고, 인수를 평가한 후, 함수 본문을 새롭게 확장된 환경에서 평가하는 방식을 보여줍니다.
   - 만약 함수 환경에 함수 이름이 없으면 에러가 발생합니다.
   - 확장된 환경에서 함수 본문을 평가하는 과정이 중요합니다.

2. 자연 의미론에서는 수식을 통해 함수 적용이 이루어지는 과정을 수학적으로 표현하고 있습니다.
   - 함수가 환경에서 정의되어 있는지 확인하고, 인수를 평가한 후 확장된 환경에서 함수 본문을 평가하여 최종 결과를 도출합니다.

이러한 방식으로, 함수 적용이 이루어지는 과정을 설명하고 함수 환경의 역할을 강조하고 있습니다.

![[Pasted image 20241014053615.png]]
예시.
함수환경이 주어진 상황에서 inc(2)의 결과는 3이 나온다.
왜?
APP를 확인해봐!
inc가 함수환경에 있니? ㅇㅇ 그거 def inc(x) = x+1이라는 함수로 매핑되어있어.
ok.
그러면 2는 뭐야? 아 그건 평가 해보니까 그냥 2잖아. ok.
그러면 x를 2에 매핑시키는 새로운 환경($\sigma$)을 가지고 함수 내부로 들어갈게~
함수 내부는 x+1이야. 그 결과는 3이야.
왜?
아 일단 x랑 2를 더해야지. x는 ID인데, 그거 $\sigma$에 있니?
ㅇㅇ 그거 2에 매칭돼.
ok. 그러니까 x는 2구나.
1은 1이고.
그래서 x+1은 3으로 결과가 나오는거야.
아하. 그래서 최종 결과가 3으로 나오는구나.
___
![[Pasted image 20241014054158.png]]
지금까지 시맨틱은 스태틱 스코핑을 사용했어.
일단 첫번째 예시 코드 보면 y가 free variable이잖어ㅋㅋ
그래서 박살나겠지.
근데 다이나믹 스코핑을 한다면 알잘딱 해서 val y=2일때는 3일때로 계산하고 val y=4일때는 7일때로 계산해서 10이 나오도록 한다고
![[Pasted image 20241014054402.png]]
엥 근데 그거 어케함?
그거 생각보다 의외로 간단한데...
function application부분에서 기존의 환경을 들고가도록 한다면??
![[Pasted image 20241014054505.png]]
닥치고 예시를봐
이게 기존 스태틱 스코핑이야.
보면 함수 정의부분에 y가 사용되는데, 이 y는 그 이전에 어디에서도 사용되지 않았던 y야. 갑자기 툭 튀어나온거임...
그래서 보면 오류나서 다 박살날 것 처럼 생겼지?
차근차근 보자고
함수환경 $\Lambda$가 있는 상황에서 val y=2; add(1)을 평가해보자.
그러면 처음엔 val이 실행되겠지.
그리고 y = 2라는 환경 $\sigma_{0}$가 만들어져.
그걸 들고 add(1)을 실행할건데, APP이 실행되겠지.
그러면 add를 함수환경 $\Lambda$에서 찾을 것이고, 그래서 add가 def add(x) = x+y랑 매칭이 된다는 사실을 확인할 수 있을 거야.
아 그러면 x랑 1이랑 매핑되겠네. 그걸 새로운 환경으로 들고간다고 했으니까 그걸 $\sigma_{1}$이라고하자.
이제 함수 내부에서는 $\sigma_{1}$이라는 환경으로 x+y를 평가할건데....
근데 y가 자유변수네? 좆됬네?
그래서 이걸 만약에 기존 환경에 새로운 환경을 추가하는 방식으로 들고다닌다면
![[Pasted image 20241014060914.png]]
문제 해결!!!
굳
![[Pasted image 20241014060934.png]]
요약하면 이런거고 함수 평가하는 APP부분을 신경써서 보면 될듯.
새로운 환경으로 만들고 그걸 들고 함수 내부를 평가하는 방식이라는 개념을 챙기면 될듯???그리고 그걸 static scoping이라고 부르고.
