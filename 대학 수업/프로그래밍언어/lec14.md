![[Pasted image 20241104133736.png|center]]
![[Pasted image 20241104133748.png]]
Continuation의 의미가 뭘까...
![[Pasted image 20241104140618.png|center]]
![[Pasted image 20241104134732.png]]
대부분의 프로그래밍 언어에서는 제어문이 있음. 예를 들어, C++의 경우 break, continue, return과 같은 제어 흐름 문법이 존재함.
함수형 언어에서는 이런 것을 어떻게 표현하냐면, Continuation으로 표현함.
![[Pasted image 20241104134900.png]]
직관적으로, Continuation은 계산 과정의 남은 부분이라고 생각하면 됨.
예를 들어 저 FAE코드가 주어져 있다고 한다면 다음과 같은 과정으로 평가됨.
1. 1을 평가한다.
2. 3을 평가한다.
3. 1번과 2번에서 평가한 결과를 더한다.
4. 5를 평가한다.
5. 3번과 4번에서 평가한 결과를 곱한다.
$k$번째 단계에서의 Continuation은 $(k+1)$번째 단계부터 마지막 단계임.
예를 들어, 3번째 단계의 Continuation은 4번째 단계와 5번째 단계임.
![[Pasted image 20241104135219.png]]
그래서 Expression의 Continuation을 명시적으로 표현하는 방법은??
$k$번째 단계의 Continuation을 다음과 같은 **함수**로 간주한다.
* $k$번째 단계의 result를 인자로 받고
* $(k+1)$번째 단계부터 마지막 단계를 수행하는 함수.

그니깐, 전체 Expression $e$에서 현재 실행되는 평가 단계 $e'$이 있으면,
$$
e = (\dots, e',\dots)
$$
$$
(\lambda x.(\dots, x, \dots))(e')
$$
이걸 $e'$의 Continuation이라고 부른다.
그러면 이제 다음과 같은 예제의 Continuation을 표현해보자.
![[Pasted image 20241104140255.png]]
![[Pasted image 20241104140312.png]]
![[Pasted image 20241104140349.png]]
![[Pasted image 20241104140425.png]]
![[Pasted image 20241104140446.png]]
그래서 위와 같이 표현할 수 있다.
만약 val이라는 문법 설탕 추가하면 다음과 같이 표현할 수 있다.
![[Pasted image 20241104140537.png]]
![[Pasted image 20241104140559.png|center]]
![[Pasted image 20241104141252.png]]
일반적인 함수 호출 방식에서는 함수가 값을 반환하고, 그 반환된 값을 그다음 코드에서 사용함.
반면, CPS는 함수가 결과를 직접 반환하는 대신에 결과를 전달할 다음 동작을 의미하는 Continuation함수에 그 결과를 넘김.
direct style 예시에서는 sum(3)을 호출하고, 그 결과를 받아서 5를 곱함. 그래서 30이 됨.
CPS에서는 sumCPS 자체에서 두가지 인자를 받음.
하나는 3이고, 하나는 다음에 어떤 동작을 할 것인지를 나타내는 continuation인 $x \Rightarrow x*5$이다.
그니깐, 저 예시는 3을 받고, 무언가를 한 다음, 거기에 5를 곱하라는 뜻임.

Continuation이 Int에서 Int로 가는 함수임을 생각하면, 다음과 같이 넘기면 되지 않을까?
sum(n)을 하고 그걸 다음에 동작할 함수인 k의 인자로 넘기는겅임.
![[Pasted image 20241104142203.png]]
근데 이건 옳지 않음.
기존 sum함수에 의존하기 때문이다. 그래서 sum(n)을 sum의 body로 대체해봐.
![[Pasted image 20241104142305.png]]이렇게 되고,
![[Pasted image 20241104142339.png]]
다음과 같은 if, else 관계를 사용하면...
![[Pasted image 20241104142414.png]]
이렇게 적절하게 바꿀 수 있지만 여전히 sum(n-1)이 살아있다.
![[Pasted image 20241104142820.png]]
이렇게 되는 이유는 sum(n-1)의 continuation이 x => k(x+n)이기 때문임.
그니깐, sum(n-1) 다음에 적용될 코드들이, n을 더해서, 그걸 기존 continuation함수에 적용을 시키는 거임.
![[Pasted image 20241104163209.png]]
그래서 이렇게 바꿀 수 있다.
이걸 위의 예시를 적용시켜보면 다음과 같다.
sumCPS(3, x=>x * 5)
= sumCPS(2, x => {x=>x * 5}(x+3))
= sumCPS(1, x => {x=> {x=>x * 5}(x+3)}(x+2))
={x => {x=> {x=>x * 5}(x+3)}(x+2)}(1)
= x=> {x=>x * 5}(x+3)}(1+2)
= x=> {x=>x * 5}(x+3)}(3)
= {x=>x * 5}(3+3)
= {x=>x * 5}(6)
= 6 * 5 = 30.
![[Pasted image 20241104172246.png]]
모든 함수가 CPS로 작성되었다면, 프로그램은 다음과 같은 특성을 만족시킨다.
1. 모든 함수는 Continuation을 인자로 받는다.
2. 하나의 함수에서 Continuation은 한번만 사용된다.
3. 모든 함수 호출은 tail position이다. 즉, 이 호출이 끝나면 더이상 할 일이 없다.
4. 모든 함수는 함수 호출로 끝난다. 즉, 계산 결과를 반환한다기 보다는, 다른 함수호출로 끝나는 경우가 많기 때문임.
![[Pasted image 20241104173408.png|center]]
![[Pasted image 20241104192919.png]]
기존의 FAE가 direct style로 적혀있던 것을 상기시키자.
![[Pasted image 20241104193005.png]]
interpreter를 CPS로 바꿔보자.
Continuation을 전달하는 형태로.
![[Pasted image 20241104193105.png]]
그러면 다음에 실행될 코드는 k(interp(expr, env))가 될텐데 이건 interp가 있는 형태이기 때문에 좀 고쳐보자.
![[Pasted image 20241104193226.png]]
Function body를 안에 넣어서 풀어서 적었다.
![[Pasted image 20241104193259.png]]
Continuation을 각 함수에 적용하는 것으로 바꾸기.
![[Pasted image 20241104193329.png]]
그래서 Num, Id, Fun은 괜찮은데, 나머지가 여전히 interp를 사용하고 있으므로 바꿔보자.
![[Pasted image 20241104194445.png]]
평가를 할 때 interp(l, env)먼저 시작한다.
그래서, interp(l, env)의 continuation은 lv => k(numAdd(lv, interp(r, env)))가 된다.
즉, interp(l, env)를 한 이후에 진행되는 코드는, interp(r, env)를 하고 그 후 numAdd를 한 것을 기존 Continuation함수에 넣는 꼴이 된다.
![[Pasted image 20241104194641.png]]
그래서 이걸 다음과 같이 다시 작성할 수 있다.
이걸 interpCPS를 사용하여 재작성하면 다음과 같다.
![[Pasted image 20241104194732.png]]
이제, interp(r, env)부분도 비슷하게 재작성 할 수 있다.
이건, interp(r, env)를 한 이후에 진행되는 코드는, numAdd를 하고 기존 Continuation함수에 넣는 꼴이므로, interp(r, env)의 continuation은 rv => k(numAdd(lv, rv))이므로,
![[Pasted image 20241104195002.png]]
이렇게 작성할 수 있고, 이걸 interpCPS로 작성하면...
![[Pasted image 20241104195030.png]]
이렇게 작성할 수 있다.
Mul의 경우는 여기서 numAdd가 아니라 numMul로만 변경하면 되므로,
![[Pasted image 20241104195104.png]]
다음과 같다.
![[Pasted image 20241104204020.png]]
마찬가지로 App의 경우, 현재 평가되는 부분은 interp(f, env)이다. 이 이후에 진행되는 코드는 이걸 평가한 뒤 CloV인지 아닌지를 판단하는 부분임.
![[Pasted image 20241104204359.png]]
interp(f, env)의 Continuation은 fv => k(fv match ~)이다.
안에 또 interp(b, fenv+(p -> interp(a, env)))가 있으므로 이걸 변경.
![[Pasted image 20241104204555.png]]
Continuation을 안으로 넣기
![[Pasted image 20241104204638.png]]
![[Pasted image 20241104204703.png]]
error를 감쌀 이유는 없음(exception이기 때문에)
저기에서 먼저 평가되는 부분은 interp(a, env)부분임.
![[Pasted image 20241104204857.png]]
PPAP
![[Pasted image 20241104205027.png]]
다음 평가부분
![[Pasted image 20241104205127.png]]
평가가 다 끝난 다음 코드는 k임.
![[Pasted image 20241104205803.png]]
그래서 이렇게 작성할 수 있다.
