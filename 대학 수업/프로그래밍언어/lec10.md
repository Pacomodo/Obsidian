![[Pasted image 20241023131056.png]]
이거 할거고
![[Pasted image 20241023131111.png]]
지금까지는 전부 함수형이고 Side effect가 없는 pure한 함수다. 변경 불가능하다. 근데 뮤테이션은 자주 쓰인다. 내용을 업데이트 하면서 프로그램의 상태를 바꿀 수 있게 해준다.
그래서 효율적인 프로그램을 만들 수 있지만, 에러가 나기가 쉽다.
![[Pasted image 20241023131303.png]]
뮤터블 데이터 구조는 생성 이후에 바뀔 수 있는 데이터 구조를 이야기 한다. imap을 보면, (x -> 3)을 더할때는 바뀌는게 아니고 쉐도잉이 일어나서 안보이는거 뿐이고, 실제로는 안바뀌어있다.
반면 뮤터블맵으로 한거는 바뀌어있다.
우리는 Box라는 뮤터블 데이터 구조를 만들 것이다.
![[Pasted image 20241023132443.png]]
이제 FAE를 BFAE로 확장해보자.(val은 설탕이라고 하자.)
![[Pasted image 20241023132603.png]]
그래서 다음과 같은게 필요하다.
박스 만들기, 조작(get, set), expr의 나열?
![[Pasted image 20241023132648.png]]
Concrete syntax는 다음과 같이 정의할 수 있다.
![[Pasted image 20241023133305.png]]
abstract syntax는 다음과 같이 정의할 수 있다.
![[Pasted image 20241023133439.png]]
그래서 이걸 어케 평가할건데?
![[Pasted image 20241023133602.png]]
이제 메모리를 쓸거야. 메모리는 주소를 벨류로 매핑하는거임.
![[Pasted image 20241023133746.png]]
박스는 메모리에 값을 저장하기 위해 메모리 셀을 할당할거야.
creation은 메모리를 할당하고 저장할거야.
getter는 read, setter는 write를 할거야.
![[Pasted image 20241023134010.png]]
![[Pasted image 20241023134020.png]]
![[Pasted image 20241023134040.png]]
![[Pasted image 20241023134053.png]]
![[Pasted image 20241023134105.png]]
![[Pasted image 20241023134159.png]]
![[Pasted image 20241023134224.png]]
![[Pasted image 20241023134254.png]]
![[Pasted image 20241023134306.png]]
![[Pasted image 20241023134318.png]]
![[Pasted image 20241023134336.png]]
![[Pasted image 20241023134407.png]]
![[Pasted image 20241023134507.png]]
![[Pasted image 20241023134540.png]]
메모리라는 타입 정의.
주소라는 타입도 정의.
벨류중 하나로 BoxV를 정의. 이건 주소를 받아야한다.
![[Pasted image 20241023134902.png]]
아래 예시를 보면 10으로 계산되야 할듯.
![[Pasted image 20241023135202.png]]
이렇게 하면 됨.
![[Pasted image 20241023135338.png]]
M은 함수니까.
![[Pasted image 20241023135528.png]]
![[Pasted image 20241023135703.png]]
