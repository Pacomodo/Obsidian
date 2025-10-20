- **객체지향 설계(Object-Oriented Design)** 의 다섯 가지 핵심 원칙
- 유지보수성과 확장성이 높은 코드를 만들기 위한 기본 철학

| 약어    | 원칙 이름                           | 핵심 개념                               |
| ----- | ------------------------------- | ----------------------------------- |
| **S** | Single Responsibility Principle | 클래스는 하나의 책임만 가져야 한다                 |
| **O** | Open/Closed Principle           | 확장에는 열려 있고, 수정에는 닫혀 있어야 한다          |
| **L** | Liskov Substitution Principle   | 자식 클래스는 부모 클래스의 행동을 대체할 수 있어야 한다    |
| **I** | Interface Segregation Principle | 클라이언트는 자신이 사용하지 않는 인터페이스에 의존하면 안 된다 |
| **D** | Dependency Inversion Principle  | 추상(인터페이스)에 의존해야지, 구체(구현)에 의존하면 안 된다 |

### 1. 단일 책임 원칙 (SRP, Single Responsibility Principle)

클래스는 **하나의 이유로만 변경되어야 한다.**
- 한 클래스는 오직 **하나의 기능(역할)** 만 담당해야 한다는 뜻
- 여러 기능을 한 클래스에 넣으면, 한 기능을 바꿀 때 다른 기능이 의도치 않게 깨짐.

```java
// ❌ 나쁜 예시
class Report {
    void generateReport() { ... }
    void printReport() { ... }     // 출력 관련
    void saveToFile() { ... }      // 저장 관련
}

// ✅ 좋은 예시
class ReportGenerator { void generate() { ... } }
class ReportPrinter { void print() { ... } }
class ReportSaver { void save() { ... } }
```

예를 들어, 위의 코드처럼 `Report`클래스 내에 `generateReport` 메서드가 존재하고, `printReport`와 `saveToFile`메서드는 `generateReport`메서드에 의존한다고 하면, `generateReport`메서드를 변경하면 의도치 않게 `printReport`와 `saveToFile`이 깨질 수 있다.

---
### 2. 개방-폐쇄 원칙 (OCP, Open/Closed Principle)

소프트웨어는 **확장에는 열려 있어야 하고, 수정에는 닫혀 있어야 한다.**
- 새로운 기능이 필요할 때, **기존 코드를 수정하지 않고 확장만으로 해결**할 수 있어야 함.
- 보통 **상속, 인터페이스, 다형성(Polymorphism)** 을 이용해 달성함.

```java
// ❌ 나쁜 예시
class DiscountService {
    double discount(String type, double price) {
        if (type.equals("STUDENT")) return price * 0.9;
        if (type.equals("VIP")) return price * 0.8;
        return price;
    }
}

// ✅ 좋은 예시
interface DiscountPolicy { double apply(double price); }

class StudentDiscount implements DiscountPolicy {
    public double apply(double price) { return price * 0.9; }
}
class VIPDiscount implements DiscountPolicy {
    public double apply(double price) { return price * 0.8; }
}

class DiscountService {
    private DiscountPolicy policy;
    DiscountService(DiscountPolicy policy) { this.policy = policy; }
    double discount(double price) { return policy.apply(price); }
}
```
나쁜 예시에서는 새로운 할인 정책이 추가되면 `DiscountService`를 수정해야 함.
반면 좋은 예시에서는 새로운 할인 정책이 추가되어도 `DiscountService`를 수정하지 않아도 됨.

구체적으로,
```java
interface DiscountPolicy { double apply(double price); }

class StudentDiscount implements DiscountPolicy {
    public double apply(double price) { return price * 0.9; }
}
class VIPDiscount implements DiscountPolicy {
    public double apply(double price) { return price * 0.8; }
}

class DiscountService {
    private final DiscountPolicy policy;            // ⬅ 추상에 의존
    DiscountService(DiscountPolicy policy) {        // ⬅ 의존성 주입
        this.policy = policy;
    }
    double discount(double price) {                 // ⬅ 변하지 않는 고정 규격
        return policy.apply(price);
    }
}
```
- **역할 분리**
    - `DiscountPolicy`: “할인의 규격(추상)”만 정의 → 변경 안정성↑
    - `StudentDiscount`, `VIPDiscount`: 정책 구현체 → **여기만 추가/수정**
    - `DiscountService`: “할인하라”라는 **협력의 흐름만** 담당 (정책 세부는 모름)
- **OCP 달성**  
    새 정책이 필요하면 `class NewYearDiscount implements DiscountPolicy { ... }`만 추가하고 생성자에 그 정책을 **주입**해주면 끝. `DiscountService`는 수정 없음.
- **테스트 용이성**  
    서비스 테스트 시, 가짜 정책(테스트 더블)을 주입해 **케이스를 독립적으로** 검증 가능.

---

### 3. 리스코프 치환 원칙 (LSP, Liskov Substitution Principle)

**부모 클래스 객체를 자식 클래스 객체로 대체해도 프로그램이 정상 동작해야 한다.**

- 즉, “IS-A 관계”가 성립해야 함.
- 자식이 부모의 기능을 **의미를 유지한 채로 확장**해야 한다는 뜻.

```java
class Bird {
    void fly() { System.out.println("날 수 있다"); }
}

class Sparrow extends Bird {}           // ✅ 정상
class Penguin extends Bird {            // ❌ LSP 위반
    @Override void fly() { throw new UnsupportedOperationException("펭귄은 못 날아요!"); }
}
```

`Bird` 대신 `Penguin`을 넣으면 코드가 깨지므로, **리스코프 원칙 위반**임.

다시 말하면 다음과 같음. **상속이 단순히 "코드를 재사용"하기 위한 수단이 아니라, 의미적으로도 일관성 있는 관계를 유지해야 한다**는 걸 강조하는 원칙임.  
즉, 부모 타입으로 선언된 코드가 자식 클래스로 대체돼도 **의도된 행위가 깨지면 안 된다**는 뜻.

이 코드를 사용하는 클라이언트가 있다고 가정해 보자.
```java
void makeBirdFly(Bird b) {
    b.fly();
}
```
이 메서드는 **"모든 새는 날 수 있다"** 는 가정 하에 작성된 코드임.  
즉, `Bird`의 인터페이스(행동 계약, contract)는 “`fly()`가 반드시 가능하다”는 의미를 포함한다.
```java
makeBirdFly(new Sparrow());  // "날 수 있다" 출력 → 문제 없음
```
- 참새는 진짜로 날 수 있으니까 `Bird`의 행위를 그대로 유지하며 확장한 경우임.
- 따라서 **리스코프 치환 원칙을 준수**한다.
```java
makeBirdFly(new Penguin());  // ❗️예외 발생: 펭귄은 못 날아요!
```
- `Penguin`은 `Bird`를 상속했지만 `fly()`를 오버라이드하면서 “날 수 없다”로 의미를 깨버림.
- 이제 클라이언트는 `Bird` 대신 `Penguin`을 넘기면 **프로그램이 정상적으로 동작하지 않는다.**

즉, **“펭귄은 새이지만, 의미상 Bird(=날 수 있는 새)”가 아니다.**  
따라서 **“Penguin is-a Bird” 관계가 깨진 것**임.

즉, 부모의 규칙을 확장(extend)할 수는 있어도 부모의 기대 행동(expectation)을 **변경하면 안 된다.**

문제의 근본은 클래스 설계에 있어 **추상화(Abstraction)가 잘못되었다는 점**임.  
“새(Bird)”를 “모든 새는 날 수 있다”로 정의했기 때문에, 펭귄처럼 예외적인 새가 들어오면 문제가 생긴다.
- 해결 방법 1 : 추상화 수정하기
부모 클래스 `Bird`에서 “모든 새는 날 수 있다”는 가정을 빼버리고, “날 수 있는 새”와 “날 수 없는 새”를 따로 나누면 LSP 위반이 사라진다.

```java
abstract class Bird { }

interface Flyable {
    void fly();
}

class Sparrow extends Bird implements Flyable {
    public void fly() { System.out.println("날 수 있다"); }
}

class Penguin extends Bird {
    void swim() { System.out.println("수영할 수 있다"); }
}
```
→ 이제 `Bird`는 “새”의 일반 개념만 담당하고, `Flyable` 인터페이스가 “날 수 있음”이라는 행위를 별도로 표현한다.
이제 `makeBirdFly()`는 이렇게 바뀌어야 한다.
```java
void makeBirdFly(Flyable bird) {
    bird.fly();
}
```
→ 따라서, **타입 수준에서 오류를 방지**했기 때문에 LSP 위반이 근본적으로 사라짐.

* 해결 방법 2 : 행동 제약 완화
혹은 `Bird`의 기본 계약을 약하게 정의할 수도 있음.
```java
class Bird {
    void fly() { System.out.println("날 수 있는 새라면 날 수 있다."); }
}
```
이 경우 `Penguin`의 `fly()`가 아무 동작도 하지 않거나, “펭귄은 날지 않습니다.”라고 출력하도록 하면, 계약 위반이 아님.
```java
class Penguin extends Bird {
    @Override
    void fly() { System.out.println("펭귄은 날지 않습니다."); }
}
```
→ `UnsupportedOperationException`을 던지는 건 “계약 위반”이지만, “fly()를 구현했지만 다르게 동작한다”는 건 “확장”에 해당하므로 OK.

---
### 4. 인터페이스 분리 원칙 (ISP, Interface Segregation Principle)

**한 인터페이스가 너무 많은 기능을 가지면 안 됨.**
* 클라이언트는 자신이 쓰지 않는 메서드에 의존하면 안 됨.

```java
// ❌ 나쁜 예시
interface Machine {
    void print();
    void scan();
    void fax();
}

class Printer implements Machine {
    public void print() { ... }
    public void scan() { throw new UnsupportedOperationException(); } // ❌
    public void fax()  { throw new UnsupportedOperationException(); }
}

// ✅ 좋은 예시
interface Printer { void print(); }
interface Scanner { void scan(); }
interface Fax { void fax(); }

class SimplePrinter implements Printer { public void print() { ... } }
class MultiFunctionMachine implements Printer, Scanner, Fax { ... }
```
예를 들어 Machine이라는 interface에 print, scan, fax라는 추상 메서드를 정의하면, 실제로 Printer라는 class에서는 scan, fax를 하지 못한다.

각각의 메서드를 가진 interface로 분리하고, 각 인터페이스를 상속받아서 구체화를 해야한다.

---
### 5. 의존 역전 원칙 (DIP, Dependency Inversion Principle)

**상위 모듈은 하위 모듈에 의존하면 안 되며, 둘 다 추상에 의존해야 한다.**
즉, “**구체 클래스(Concrete Class)**” 가 아니라 “**인터페이스(추상)**” 에 의존해야 함.

```java
// ❌ 나쁜 예시
class MySQLDatabase {
    void connect() { ... }
}
class ProductRepository {
    private MySQLDatabase db = new MySQLDatabase();  // ❌ 구체 클래스에 의존
    void save(Product p) { db.connect(); ... }
}

// ✅ 좋은 예시
interface Database { void connect(); }
class MySQLDatabase implements Database { public void connect() { ... } }
class OracleDatabase implements Database { public void connect() { ... } }

class ProductRepository {
    private Database db;   // ✅ 추상에 의존
    ProductRepository(Database db) { this.db = db; }
    void save(Product p) { db.connect(); ... }
}
```

좋은 예시에서 데이터베이스 종류가 바뀌어도 `ProductRepository`는 수정할 필요가 없음.

---
### 요약

| 원칙  | 요약                   | 키워드           |
| --- | -------------------- | ------------- |
| SRP | 클래스는 한 가지 일만 해라      | 책임 분리         |
| OCP | 수정 없이 확장 가능해야 한다     | 다형성, 인터페이스    |
| LSP | 자식은 부모를 대체할 수 있어야 한다 | 상속 일관성        |
| ISP | 인터페이스는 작게 쪼개라        | 인터페이스 분리      |
| DIP | 추상에 의존해라             | 의존성 주입, 인터페이스 |

---
