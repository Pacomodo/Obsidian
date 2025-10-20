![[Pasted image 20241023101008.png]]
재귀 함수에 대해서 배워보자.
![[Pasted image 20241023101043.png]]
재귀함수를 생각하자. 기본 case와 Recursive case를 생각할 수 있다.
![[Pasted image 20241023101134.png]]
이전에 F1VAE는 이미 recursive function을 지원한다.
왜냐고?
함수 환경 $\Lambda$는 Expression을 평가하기 전에 모든 Function Definition을 다 저장해놓기 때문이다.
![[Pasted image 20241023101328.png]]
그래서 다음과 같이 함수 환경이 정의된다.
그래서 sum을 보면 함수 환경에서 다시 또 들어가는, 재귀의 역할을 하도록 만들 수 있다.
![[Pasted image 20241023101418.png]]
근데 실질적으로 재귀함수의 역할을 하기 힘들다. Base case가 없어서 못멈추기 때문이다.
그래서, Base case를 만들어주기 위해...
Conditional을 넣는다면?
![[Pasted image 20241023102522.png]]
![[Pasted image 20241023102539.png]]
그래서 기존 F1VAE에서 Lt와 If라는 Expression을 추가하고, Boolean도 추가하자.
![[Pasted image 20241023102625.png]]
함수 환경은 다음과 같이 만들어진다.

그러면 FAE에서는 어떨까?
![[Pasted image 20241023102841.png]]
Conditional추가한다고 해서 Recursive function이 되는 것일까? 안된다!
![[Pasted image 20241023111811.png]]
일단 이 부분은 여러번 찾아봤는데, 잘 이해가 안돼서 넘어가자.
![[Pasted image 20241023111840.png]]
두가지 방법이 있는데, 먼저 1번을 보자.
![[Pasted image 20241023111918.png]]
핵심 아이디어: 재귀를 위한 함수 전달

**함수를 인자로 전달**하는 방법을 사용하면, 함수가 자신을 참조할 수 없는 문제를 해결할 수 있습니다. 예를 들어, `sum`이 자신의 이름을 모르기 때문에, `sum` 함수 자체를 인자로 전달하여 내부에서 자신을 호출할 수 있습니다. 이를 통해 재귀적으로 동작할 수 있게 만드는 것입니다.
![[Pasted image 20241023112128.png]]
그래서, sumX라는 함수는 sumY라는 함수를 인자로 받아서 인식할 수 있도록 한다.
![[Pasted image 20241023112249.png]]
그래서 감싸보자.
![[Pasted image 20241023112600.png]]
![[Pasted image 20241023112607.png]]
![[Pasted image 20241023112948.png]]
함수 Body는 거의 비슷하다.
![[Pasted image 20241023113050.png]]
![[Pasted image 20241023113530.png]]
![[Pasted image 20241023113648.png]]
![[Pasted image 20241023113704.png]]
![[Pasted image 20241023113726.png]]
![[Pasted image 20241023113754.png]]

두번째 방법:
![[Pasted image 20241023114535.png]]
![[Pasted image 20241023114553.png]]
그래서, Arithmetic comparison op, Conditionals, Recursive function definition이 필요함.
![[Pasted image 20241023115606.png]]
재귀 함수 정의는 4개의 부분으로 구성되어있다.
함수이름, Parameter이름, Function body expression, Scope expression.
![[Pasted image 20241023115702.png]]
재귀함수 정의또한 Expression이라는 사실을 기억하자.
![[Pasted image 20241023115738.png]]
![[Pasted image 20241023115810.png]]
Concrete syntax는 다음과 같다.
![[Pasted image 20241023115832.png]]
Abstract syntax는 다음과 같다.
![[Pasted image 20241023115939.png]]
그래서 인터프리터를 구현해야되고, Natural semantics를 정의해야된다.
Values에는 불리언이 들어가야 한다.
![[Pasted image 20241023120031.png]]
비교 연산자 구현
![[Pasted image 20241023120848.png]]
조건문 구현
