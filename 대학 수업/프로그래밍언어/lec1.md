___
패턴 매칭할 때 모든 Case Cover를 수행해야함.
근데 단순히 걍 막 박으면 안됨.
예를 들어...
```scala
def isEvenBranch(t: Tree): Boolean = t match
	case Branch(_, n, _) if n % 2 == 0 => true
	case Branch(_, n, _) if n % 2 == 1 => false
	case Leaf(_) => false
```
는 안돌아감.
그 이유는 scala가 타입체크만 하기 때문임.
그냥 _ 를 쓰자.
___
함수에 함수를 넣거나 함수에 함수를 반환할 수 있음
함수에 함수를 할당할 수 있다.
예를 들어...
```scala
val inc: Int => Int = (x: Int) => x + 1
```
inc는 int에서 int로 가는 함수인데 그 함수는 (x: Int) => x+1임
___
리스트의 패턴 매칭
예시1)
```scala
def getSnd(list: List[Int]): Int = list match
	case _ :: x :: _ => x
	case _ => 0
```
2번째 원소 반환
예시 2)
```scala
def filterOddAndDouble(list: List[Int]): List[Int] = list match
	case Nil => Nil 
	case x :: xs if x % 2 == 1 => x * 2 :: filterOddAndDouble(xs)
	case _ :: xs => filterOddAndDouble(xs)
```
홀수 찾고 2배하는 함수. 반환값은 리스트
예시 3)
```scala
list.length // 4 : Int
list.map(_ * 2) // List(6, 2, 4, 8) : List[Int]
list.filter(_ % 2 == 1) // List(3, 1) : List[Int]
list.foldLeft(0)(_ + _) // 0 + 3 + 1 + 2 + 4 = 10 : Int
list.flatMap(x => List(x, -x)) // List(3, -3, ..., 4, -4): List[Int]
list.map(x => List(x, -x)).flatten // List(3, -3, ..., 4, -4): List[Int]
```
foldLeft는 python reduce랑 같음.
___
option은 러스트랑 같은듯
null쓰지말고 option쓰세요
While Scala supports null to represent the absence of a value, DO NOT USE NULL IN THIS COURSE. 
Instead, an option (Option\[T\]) is a container that may or may not contain a value of type T: 
1. Some(x) represents a value x and
2. None represents the absence of a value 
```scala
val some: Option[Int] = Some(42)
val none: Option[Int] = None

// Operations/functions on options
some.map(_ + 1) // Some(43) : Option[Int]
none.map(_ + 1) // None : Option[Int]
some.getOrElse(7) // 42 : Int
none.getOrElse(7) // 7 : Int
some.fold(7)(_ * 2) // 42 * 2 = 84 : Int
none.fold(7)(_ * 2) // 7 : Int
```
pair는 T와 U를 담는 container임.
->를 사용해서도 만들 수 이씀.