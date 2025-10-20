![[Pasted image 20241014182953.png]]
![[Pasted image 20241023071810.png]]
위의 FVAE에 적힌 코드는 value 1을 variable x에 할당하고, 환경 $\sigma$ $[x\mapsto 1]$을 기반으로 하여 body expression $x+2$를 계산한다.
아래에 적힌 코드는 lambda function을 사용해서, $x \Rightarrow x+2$라는 함수의 argument $x$에 $1$을 할당하고, 그걸 환경으로 가지는 $x+2$을 계산한다.
![[Pasted image 20241023075426.png]]
그래서 일반적으로, $\text{val }x = e_{1};e_{2}$는 $(\lambda x.e_{2})(e_{1})$과 같다.
즉, $e_{1}$을 $x$에 할당한 뒤, 그걸 환경으로 하여 $e_{2}$를 계산하는 것과, $x$를 argument로 가지는 람다 펑션에서, $x$에 $e_{1}$를 할당하고, 그걸 기반으로 $e_{2}$를 계산하는 것과 동일하다.

Val의 경우...
![[Pasted image 20241023075448.png]]
기존 환경 $\sigma$에서, $\text{val }x=e_{1};e_{2}$는 $v_{2}$로 평가된다. 왜? 그 이유는...
기존 환경 $\sigma$에서 $e_{1}$은 $v_{1}$으로 평가되고, 따라서, 기존 환경 $\sigma$에 $[x\vdash v_{1}]$을 추가한 환경에서 $e_{2}$는 $v_{2}$로 평가되기 때문이다.

람다 펑션 $(\lambda x.e_{2})(e_{1})$의 경우...
![[Pasted image 20241023075523.png]]

기존 환경 $\sigma$에서 $\lambda x.e_{2}$를 받으면, $\left<\lambda x.e_{2}, \sigma\right>$라는 클로져 형성. 람다 펑션은 이 클로져로 평가된다. $\lambda x.e_{2}$가 클로저로 평가된다는 사실을 알았다. App은 이제 클로져 안의 환경 $\sigma$를 토대로 하여, 기존 환경 $\sigma$에서 평가된 $e_{1}$을 $[x\mapsto v_{1}]$을 클로져 안의 환경 $\sigma$에 추가하여, 그것을 토대로 $e_{2}$를 $v_{2}$로 평가한다.
![[Pasted image 20241023081404.png]]
자, 이제 우리는 $\text{val }x=e_{1};e_{2}$가 사실은 $(\lambda x.e_{2})(e_{1})$과 실제로 동일하게 작동한다는 사실을 알았으므로, 이를 토대로 하여, Expr에서 val부분을 없앤 FAE를 만들 수 있다. 기존 FVAE에서는 Val이 따로 Expr의 구성요소로 존재했다는 사실을 기억하자.
![[Pasted image 20241023081626.png]]
문법적 설탕의 정의는, 위에서 했던 것 처럼, 즉, Val이 Fun으로 표현할 수 있었던 것처럼, 어떤 Syntatic element가 또다른 Syntatic element로 표현될 수 있다면 그 Syntatic element를 Syntatic sugar(설탕)이라고 한다. Val이 여기서는 Sugar의 역할을 한다고 볼 수 있다.
![[Pasted image 20241023081849.png]]
Desugaring은 이러한 Sugar를 없애는 변환을 말한다.
즉, Expr에서 Expr로 가는 함수를 이야기한다.
![[Pasted image 20241023081937.png]]
그래서 우리는 Val을 다음과 같이 표현할 수 있다. 근데 이게 실제로 맞을까?
아니다. 왜냐하면 안에 들어있는 $e_{1}, e_{2}$도 $\mathbb{E}$의 원소이기 때문이다. 그래서, $e_{1}$이랑 $e_{2}$에게도 Desugaring을 해줘야 옳다고 할 수 있다.
![[Pasted image 20241023082134.png]]
단적으로, 이런 예시를 생각해보자.
오른쪽의 빨간 $e_{2}$는 실제로 Val부분이 남아있기 때문에, Desugar가 되지 않았다!
![[Pasted image 20241023082236.png]]
그래서 Desugar를 적으면 이렇게 할 수 있다. $e_{2}$에게도 Desugar를 적용하고, $e_{1}$한테도 Desugar를 적용해서, 그걸 람다 함수에 집어넣은 꼴로 변환시켜야 한다.
![[Pasted image 20241023082402.png]]
따라서, 덧셈과 곱셈, 함수에게도 Desugaring을 해줘야한다.
![[Pasted image 20241023082459.png]]
그래서 이걸 Desugaring 해보자.
먼저 $1$을 $e_{1}$, $2+(\text{val }y=3;x*y)$를 $e_{2}$라고 하자.
Desugaring 규칙에 따라서,
$(\lambda x.D[e_{2}])(D[e_{1}])$이 된다.
$D[e_{1}]$, 즉, $D[1]$는 $1$이다.
$D[e_{2}]$, 즉, $D[\text{2} + (\text{val }y=3; x*y)] = D[2] + D[\text{val }y=3;x*y]$...
그래서 결론적으로 다음과 같다.
$$
(\lambda x.(2+(\lambda y.x*y)(3)))(1)
$$
![[Pasted image 20241023085801.png]]
이 Desugar를 다음과 같이 구현할 수 있다.
![[Pasted image 20241023085847.png]]
![[Pasted image 20241023085915.png]]
대부분의 언어들은 Syntatic Sugar를 가지고 있다.
![[Pasted image 20241023085944.png]]
스칼라의 경우 for yield와 같은 것... 등등
이제 FVAE에서 Syntatic sugar를 전부 제거한 거를 Lambda calculus(LC)라고 부른다.
![[Pasted image 20241023090106.png]]
구성요소는 단 세가지. Variable Lookup, function, application뿐이다.
이전에 FVAE에서 Val(Variable definition)을 Function definition과 Application으로 나타내었다.
![[Pasted image 20241023090225.png]]
그러면 다른 요소들은 어떤 식으로 나타낼 수 있을까?
당장 Num은 어떻게 나타냄? Church encoding을 사용하면 된다...
![[Pasted image 20241023091126.png]]
핵심 아이디어는 자연수 $n$을 function으로 간주하는데, 또다른 함수 $f$와 $x$를 인자로 받아 $f$를 $n$번 적용하는 함수로 간주한다.
그러면 덧셈과 곱셈은?
해석하면, $D[e_{2}]$의 결과는 Desugaring을 거쳤기 때문에, 함수와 argument(함수일수도 있고 어쨌든...)를 인자로 받는 함수라고 생각할 수 있다. 예를 들어, $e_{2}$가 $3$이면 $D[e_{2}]=f(f(f(x)))$가 됨.
덧셈의 경우라면, $D[e_{2}]$의 결과, 즉, 그 함수를 $D[e_{1}]$의 $x$인자로 넣는다.
곱셈의 경우는 $D[e_{1}]$의 함수 인자로 넣는다.
![[Pasted image 20241023093501.png]]
예를 들어 다음과 같은 예시를 보자.
$D[1]$은 $\lambda f.\lambda x.f(x)$로 표현된다.
$$
\underbrace{ (\lambda f.\lambda x.f(x)) }_{\text{람다펑션} }\underbrace{ (f) }_{ arg_{1} }\underbrace{ ((\lambda f.\lambda x.f(x))(f)(x)) }_{ arg_{2} }
$$
람다 펑션의 적용은 함수 arg1을 받고, arg2를 받아서, 결과물인 $f(arg_{2})$를 내보낸다.
따라서, 두번째 줄에서 세번째 줄로 넘어가게 된다.
![[Pasted image 20241023094743.png]]
그래서, Church encoding을 사용하면 다른 boolean이나 list, pair와 같은것도 LC로 표현할 수 있다.
![[Pasted image 20241023094828.png]]
핵심 아이디어는 boolean $b$도 결국 함수인데, 어떤 함수냐면, **두 개의 인자 $t,f$를 받고**, $b$가 참이라면 $t$를, 거짓이라면 $f$를 적용하는 함수라고 생각하는 것이다.
True는 $\lambda t.\lambda f.t$라는 함수로 Desugaring.
False는 $\lambda t.\lambda f.f$라는 함수로 Desugaring.
$\text{if}(e_{1}) \ e_{2} \text{ else }e_{3}$는 $D[e_{1}](D[e_{2}])(D[e_{3}])$.
비슷한 논리로, $e_{1} \&\& e_{2}$는 $\text{if}(e_{1}) \ e_{2} \text{ else }e_{1}$으로 간주해서 $D[e_{1}](D[e_{2}])(D[e_{1}])$으로 작성한다.
$e_{1}\mid\mid e_{2}$는 $D[e_{1}](D[e_{1}])(D[e_{2}])$
부정은 $f$와 $t$의 순서를 바꿔서 넣는 함수로 간주.
$e_{1}\&\&e_{2}$가 왜 $D[e_{1}](D[e_{2}])(f)$라고 못쓰냐면, $f$는 variable이여서 평가가 필요하기 때문이다.
$f$가 실제로 $false$를 의미하는 것이 아닐수도 있다는 뜻이다.
![[Pasted image 20241023100735.png]]
그래서, LC는 Turing complete하다.

