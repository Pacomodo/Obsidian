- Interface는 기본적으로 껍데기로 구성되어 있음.
- 즉, 상수와 구현되지 않은 메서드로만 구성됨.
- 상수 정의 시에 특별히 상수라고 명시하지 않아도 컴파일러에 의해 상수로 변경된다.
- 메서드 정의시에 `public`하게 정의하지 않아도 Interface의 모든 메서드는 컴파일러가 `public`하게 제한자를 삽입한다.
```java
interface MyInterface{
	public static final double PI = 3.14;
	public static final int FIRST = 1;
	int THIRD = 3; // public static final int THIRD = 3;과 동일
	public abstract void run();
	void run2(); // public static void run2();
}
```
- 인터페이스의 특징
	- 객체 생성을 할 수 없다. $\leftarrow$ 구현되지 않은 메서드를 포함 하기 때문.
	- super type으로 사용할 수 있음.
	- 상속되어져서 sub class가 모든 메서드들을 구현(Overriding)해야한다.
	- 상속한 sub class들의 명세서 역할로 사용된다.
	- Polymorphism 효과
	- Subclass는 `implements (interface name), (interface name)`으로 다중 상속을 받을 수 있다.

- 예시
```java
interface MediaPlayer{
	abstract void start();
	abstract void stop();
}
```
위와 같이 정의된 interface가 있다고 하자.
```java
class VideoMediaPlayer implements Mediaplayer{
	public void start(){
		System.out.println("start..");
	}
	public void stop(){
		System.out.println("Stop..");
	}
}
```
위와 같이 구현하여야 한다.

구현된 Subclass를 다음과 같이 사용할 수 있다.
```java
class InterfaceTest{
	public static void main(String[] args){
		MediaPlayer t = new VideoMediaPlayer();
		t.start();
		t.stop();
	}
}
```