###### 오류
- 컴파일 시 발생하는 오류
- 실행 시 발생하는 오류
	- 에러 : 개발자가 처리할 수 없는 오류
	- 예외 ; 개발자가 처리할 수 있는 오류

###### 예외 종류
- Exception
	- RuntimeException : 컴파일러가 예외발생여부를 체크해주지 못한다.
		- NullPointerException, ArrayIndexOutOfBoundsException, NumberFormatException, ClassCastException, ArithmeticException...
	- IOException, SQLException... : 컴파일러가 예외발생여부를 체크한다.

###### 예외 처리
- try~catch~finally (finally는 try블럭과 같이 쓰인다.)
예를 들어, 다음과 같은 내용을 생각하자.
```java
void m(A a){
	try{
		sop(a.hashCode());
	} catch(NullPointException e) {
	
	} finally {
	// 예외가 발생하든 안하든 finally구문은 항상 실행된다.
	}
}
```

- throws

메서드를 호출한 곳으로 예외를 "떠넘긴다".
```java
void a(C c){
	b(c); // b호출!!
	// 예외는 여기로 떠넘겨짐.
}

void b(C c) throws NullPointerException{
	sop(c.toString()); // 어 근데 오류났어
}
```

- throw

강제로 예외를 발생시킨다.
```java
void m(int i) throws IOException {
	if (i < 0){
		throw IOException;
	}
}
```

![[image.png]]
