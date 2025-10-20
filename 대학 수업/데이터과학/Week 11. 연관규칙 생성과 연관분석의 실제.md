### 지표를 이용한 연관규칙의 분석

![[Pasted image 20240513151240.png]]
![[Pasted image 20240513151437.png]]
$\text{Support(최강야구)}= \frac{\text{최강야구 포함 트랜잭션}}{\text{전체 트랜잭션}} = \frac{2}{4}$
최강야구를 본 사람이 환승연애를 볼 비율
$\text{Support(최강야구}\to \text{환승연애)} = \frac{\text{최강야구 \& 환승연애 포함 트랜잭션}}{\text{전체 트랜잭션}} = \frac{1}{4}$
![[Pasted image 20240513151836.png]]
$\text{Confidence(최강야구}\to \text{환승연애)} = \frac{\frac{1}{4}}{\frac{2}{4}} = \frac{1}{2}$
나는 Solo -> 놀면 뭐하니
환승연애 -> 나는 solo와 최강야구
높은 Confidence를 갖는 연관 규칙이 반드시 유의미 하지는 않는다.
예를 들어 다음과 같은 Confidence를 생각해보자.
Confidence(20학번 입학 $\to$기대수명 300세 미만) = (20학번 입학자 中 기대수명도 300세 미만인 비율) = 1
근데 이건 20학번이든 21학번이든 22학번이든 항상 1임.
왜? Confidence(A$\to$B)에서 B가 일어날 확률이 너무 크니깐 의미가 없어짐.

새 지표는 Confidence 값에 사건 B의 비율을 나누면 좋겠다.
![[Pasted image 20240513152616.png]]
Confidence(A$\to$B) = (A전체 중 AB인 비율)
Lift($A \to B$) = Support($A \to B$) / Support($A$)Support($B$)
Lift($B \to A$) = Support($B \to A$) / Support($A$)Support($B$)
둘은 같다. 즉, 방향성이 없다.

https://colab.research.google.com/drive/10BbM7hFKf6SINt0FXuPXa479r51cFBLY?hl=ko#scrollTo=umr8r2L9xaSE

### 지지도를 이용한 시퀀스 마이닝

![[Pasted image 20240513161640.png]]
${<}\{3\}, \{1,4\}{>}$ 어떤 시점에서 3을 겪은 바 있는 사람이 이후 시점에서 1, 4를 겪을 확률
![[Pasted image 20240513162423.png]]
A가 ${<}\{2\}, \{2,3\}{>}$을 subsequence로 가지나? YES. time stamp 1과 time stamp 2를 보자.
B는? NO
C는? YES
D는? YES
E는? NO
따라서, $s({<}\{3\}, \{1,4\}{>}) = \frac{3}{5} = 0.6$
$s({<}\{3\},\{5\}{>}) = \frac{4}{5} = 0.8$
