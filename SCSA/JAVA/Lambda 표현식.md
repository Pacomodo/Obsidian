### 개요

* “메서드를 하나의 식(식별자 없는 함수)”으로 표현하는 문법  
* “이름 없는 익명 함수(anonymous function)”를 간결하게 표현한 문법
즉, **메서드를 값처럼 전달할 수 있게 만든 문법**.
```java
// 기존 방식: 익명 클래스
Runnable r1 = new Runnable() {
    @Override
    public void run() {
        System.out.println("Hello Lambda!");
    }
};

// 람다식
Runnable r2 = () -> System.out.println("Hello Lambda!");
```

둘 다 같은 의미지만, **람다는 훨씬 짧고 읽기 쉬움**.

### 문법 구조
```
(매개변수) -> { 실행문 }
```

| 구성 요소     | 의미                   | 예시                  |
| --------- | -------------------- | ------------------- |
| `(매개변수)`  | 전달받을 인자들             | `(x, y)`            |
| `->`      | “~를 사용해 다음 문장을 실행하라” |                     |
| `{ 실행문 }` | 함수 본문                | `{ return x + y; }` |

예를 들어:
```java
(int x, int y) -> { return x + y; }
```

### 문법 단축 규칙

람다식은 상황에 따라 불필요한 부분 생략 가능.

| 형태                              | 코드                                                     | 설명            |
| ------------------------------- | ------------------------------------------------------ | ------------- |
| 1. 매개변수 타입 생략 가능                | `(x, y) -> x + y`                                      | 컴파일러가 타입을 추론함 |
| 2. 매개변수가 하나면 괄호 생략 가능           | `x -> x * x`                                           | 단일 인자일 때만     |
| 3. 문장이 하나면 `{}`와 `return` 생략 가능 | `(a, b) -> a + b`                                      | 바로 결과 반환 시    |
| 4. 문장이 여러 개면 `{}` 필수            | `(x, y) -> { System.out.println(x+y); return x + y; }` | 여러 줄이면 블록 사용  |

### 어디에 쓰는가?

- “단 하나의 추상 메서드”를 가진 인터페이스에서만 사용가능.(함수형 인터페이스(Functional Interface))
```java
@FunctionalInterface
interface Calculator {
    int operate(int a, int b);
}
```
이 인터페이스를 구현하는 익명 클래스를 람다로 쓸 수 있음.
```java
Calculator add = (a, b) -> a + b;
Calculator sub = (a, b) -> a - b;

System.out.println(add.operate(3, 4)); // 7
System.out.println(sub.operate(10, 4)); // 6
```
### 자바 표준 함수형 인터페이스 (java.util.function)

| 인터페이스               | 메서드                 | 설명         | 예시                               |
| ------------------- | ------------------- | ---------- | -------------------------------- |
| `Runnable`          | `void run()`        | 인자 X, 리턴 X | `() -> System.out.println("hi")` |
| `Supplier<T>`       | `T get()`           | 인자 X, 리턴 O | `() -> Math.random()`            |
| `Consumer<T>`       | `void accept(T t)`  | 인자 O, 리턴 X | `x -> System.out.println(x)`     |
| `Function<T,R>`     | `R apply(T t)`      | 인자 O, 리턴 O | `x -> x * 2`                     |
| `Predicate<T>`      | `boolean test(T t)` | 조건 검사용     | `x -> x > 10`                    |
| `BiFunction<T,U,R>` | `R apply(T,U)`      | 두 개 인자     | `(a,b) -> a+b`                   |
### 활용 예제

- 컬렉션 정렬 (Comparator)
```java
List<String> names = Arrays.asList("Bob", "Alice", "Charlie");
names.sort((a, b) -> a.length() - b.length());
System.out.println(names); // [Bob, Alice, Charlie]
```
- 필터링 (Predicate)
```java
List<Integer> nums = Arrays.asList(1,2,3,4,5,6);
nums.stream()
    .filter(n -> n % 2 == 0)
    .forEach(System.out::println); // 2,4,6
```
- 매핑 (Function)
```java
List<Integer> squares = nums.stream()
    .map(n -> n * n)
    .toList();
System.out.println(squares); // [1,4,9,16,25,36]
```

### 내부 동작
람다는 사실 **익명 클래스와 유사하게 동작**하지만, 컴파일 시 **invokedynamic** 명령어로 처리돼 더 효율적임.
즉, `new` 객체 생성 없이 JVM이 내부적으로 “함수 포인터”처럼 관리합니다.
### 자주 쓰이는 패턴

| 상황       | 코드 예시                                                             |
| -------- | ----------------------------------------------------------------- |
| 스레드 실행   | `new Thread(() -> System.out.println("Running")).start();`        |
| 콜백 함수    | `button.setOnClickListener(e -> System.out.println("Clicked!"));` |
| 정렬 기준 지정 | `list.sort((a, b) -> a.getPrice() - b.getPrice());`               |
| 조건 필터링   | `stream.filter(p -> p.isAvailable())`                             |
### 람다와 익명 클래스의 차이

| 항목      | 익명 클래스        | 람다                       |
| ------- | ------------- | ------------------------ |
| 문법      | 장황함           | 간결함                      |
| 타입      | 항상 새 클래스      | 함수형 인터페이스                |
| this 참조 | 자기 자신(익명 클래스) | 람다를 감싼 외부 객체             |
| 성능      | 클래스 생성 필요     | JVM이 최적화 (invokedynamic) |
