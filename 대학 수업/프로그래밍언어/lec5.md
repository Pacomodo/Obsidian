![[Pasted image 20241013162731.png]]
x+y를 계산하려면 x랑 y가 이전에 어떻게 바인딩 되었는가에 대한 "환경"을 그대로 가지고 가야됨.
>[!gpt]
> 기호 설명
> - **`⊢`**: 이 기호는 평가가 일어나는 과정(도출 과정)을 나타냅니다. 즉, 어떤 환경에서 표현식을 평가할 때 이 기호를 사용합니다.
> - 예: **`⊢ x + y ⇒ 3`**는 `x + y`가 3으로 평가된다는 뜻입니다.
> - **`⇒`**: 이 기호는 평가의 결과를 나타냅니다. 즉, 표현식이 어떤 값으로 평가되는지를 보여줍니다.
> - 예: **`x + y ⇒ 3`**은 `x + y`가 3이라는 값으로 평가됨을 의미합니다.

![[Pasted image 20241013163234.png]]
기존 AE에서는 expression을 받아서 number로 변환함.
VAE에서는 environment를 추가로 받음.
![[Pasted image 20241013163848.png]]
그래서 평가를 하는 함수 interp에는 expr과 env, 두개의 type를 받음.
![[Pasted image 20241013175010.png]]
그래서 VAE를 구현할때는 environment를 받는 interpreter를 구현해야되고, environment의 semantics를 정의해야됨.
![[Pasted image 20241013183419.png]]
Number는 그대로 number를 반환해야 될 것 같지?
Add랑 Mul은 실제로 계산하는건데, 그건 interp(l, env) + interp(r, env)로 구현하면 될듯. 왜냐면 $e_{1}, e_{2}$모두 같은 environment하에서 계산하는 것이기 때문.
val은 environment를 추가하는 역할이라고...
Val(name, init, body)로 정의됨을 생각하자.
![[Pasted image 20241013190424.png]]
그러면 interp(b, env + (x -> interp($e$, env)))로 계산하면 될듯.
Id(name)로 정의됨을 생각하자.
env에서 쓸수 있는 Id라면 그걸 가져오고, env에서 쓸 수 없는 Id라면 계산할 수 없는 free identifier이므로, 
env.getOrElse(x, error(s"free identifier: $x"))
다음과 같이 정의할 수 있다.
![[Pasted image 20241013185614.png]]
예제 1번
val x=1; x+2의 결과가 3이 나옴을 확인할 수 있다.
그 이유는 다음과 같이 확인할 수 있다. ID는 참조할 때 쓰이고 VAL은 선언될때 쓰인다는걸 생각해보자.
![[Pasted image 20241013190749.png]]
예제 2번.
val x=1; {val y=2; x+y}의 결과가 3이 나옴을 확인할 수 있다. x가 선언될 때는 맨 밑의 val, y가 선언될 때는 그 다음의 val임을 확인하자.
![[Pasted image 20241013190944.png]]
예제 3번.
val x=1; {val x=2; x} + x의 결과가 3이 나옴을 확인할 수 있다. 섀도잉이 일어난 것을 확인할 수 있다.
![[Pasted image 20241013191134.png]]
예제 4번.
{val x=1; x}+x의 결과가 나오지 않음을 확인할 수 있다.
ID에서 실패함.
![[Pasted image 20241013191351.png]]
결론
