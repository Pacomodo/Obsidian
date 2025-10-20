Arithmetic expression을 생각해봅시다.
AE는 무수히 많음.
이 중 유효한 AE를 가리는 것 - Concrete syntax
Parsing된 AE가 어떻게 생김 - Abstract syntax
결과는? - operational sementics
![[Pasted image 20240909134210.png]]
다음과 같은 Notation을 사용하자.
![[Pasted image 20240909134304.png]]
예를 들어, integer를 다음과 같이 정의할 수 있음.
digit은 0, ..., 9
number는 앞에 -가 올수도 있고 뒤에는 digit이 한 번 이상 반복.
(EBNF : extended Backus-Naur form)
![[Pasted image 20240909134546.png]]
예시
![[Pasted image 20240909134701.png]]
expr의 rule을 recursively하게 적용.
근데 부족한건 $+$와 $\times$의 적용 순서임.
![[Pasted image 20240909134932.png]]
모호함을 없애기 위해 왼쪽먼저 적용.
우선순위는 $\times$먼저.
abstract syntax of AE
![[Pasted image 20240909135255.png]]
![[Pasted image 20240909135330.png]]
그래서... Concrete syntax랑 Abstract syntax의 차이점은
![[Pasted image 20240909135523.png]]
같은 Abstract라도 Concrete syntax는 다를 수 있음.
예를 들어...
1번, 2번, 3번은 모두 Abstract syntax는 같음.
Concrete syntax를 파서가 잘 읽고 읽고 abstract syntax구조만 남기고 그걸 인터프리터한테 넘겨

![[Pasted image 20240909135805.png]]
Axiomatic은 하나하나 쌓기 Denotational semantics는 수학적 대상에 대응-> 의미만들기 operational semantics은?
![[Pasted image 20240909135949.png]]
Big step은 밑에 결과 써두고 위에 그 결과가 나온 원인을 써둠.
small step은 하나하나 써둠
![[Pasted image 20240909140340.png]]
![[Pasted image 20240909140424.png]]
e는 계산하면 n이 된다는 뜻.
그래서 AE를 Natural semantics로 나타내면 저렇게 됨.
![[Pasted image 20240909140735.png]]
그래서?
![[Pasted image 20240909141030.png]]
![[Pasted image 20240909141102.png]]
보면 Linear하게 정의하기 위해 왼쪽 먼저 다 하고 오른쪽을 하도록 정의했다.(순서 강제) 하지만 Big step은 그렇게 정의하지 않았다.
![[Pasted image 20240909141113.png]]
![[Pasted image 20240909141603.png]]
![[Pasted image 20240909141855.png]]
