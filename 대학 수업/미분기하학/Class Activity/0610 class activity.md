___
### Isoperimetric inequality
##### Statement
Let $\gamma$ be a simple closed curve, let $l(\gamma)$ be its length and let $A(\gamma)$ be the area contained by it. Then, $4\pi A(\gamma)\leq l(\gamma)^{2}$ and inequality holds if and only if $\gamma$ is a circle.
##### Proof Idea
1. Wirtinger’s Inequality and Green's Theorem
2. Fourier Series and Parseval’s Identity
3. Using Brahmagupta’s Formula
4. Using Euler Lagrange(Calculus)
##### Application
* 비눗방울이 구의 형태를 가지는 이유
* 이동통신 셀로 육각형을 많이 사용
* 플라토 문제와 극소 곡면

___
### Jordan curve theorem
##### Statement
$\mathbb{R}^{2}$위에 있는 Jordan Curve $\Gamma$에 대하여, $\Gamma$는 $\mathbb{R}^{2}$를 내부와 외부, 두 부분으로 나눈다.(Jordan Curve는 Simple closed curve를 이야기한다.)
##### Proof Idea
1. $\Gamma$는 $\mathbb{R}^{2}$를 seperate함을 보인다.
2. 반면 Arc는 $\mathbb{R}^{2}$를 seperate하지 못함을 보인다.
3. 1과 2로부터 $\Gamma$는 정확히 $\mathbb{R}^{2}$를 두 부분으로 나눔을 보인다.
##### Application
* Ray casting algorithm
어떤 점이 다각형 내부에 있는지 외부에 있는지 판별하는 알고리즘
* Binary image processing
___
### Hopf Umlaufsatz
##### Statement
단순 폐곡선 $C$ 위의 점이 1회 회전하는 동안 그 점에서의 접선의 방향이 변화한 양은 $\pm 2\pi$이다. 즉, Simple closed curve $C$의 Total curvature는 $\pm 2\pi$이다.
##### Proof Idea
1. Parameter field가 되는 $s_{1}s_{2}$-coordination
2. Tangent vertor의 각도 변화를 표현하는 원 $K$
3. Simple closed curve $C$

세 가지 공간 사이에 continuous한 mapping이 존재한다는 것을 증명함.

이후 다음과 같이 3개를 정의한다.
1. $C(s_{i})$를 $s$로 parametrize된 곡선 $C$ 위의 한 점이라고 정의함.
2. $f(s_{i}, s_{j})$를 다음 조건을 만족하는 원 $K$ 위의 점이라고 정의함.($\overrightarrow{C(s_{i})C(s_{j})}$과 평행하도록 원 $K$의 중심으로부터 그은 반지름이 원과 만나는 점)
3. $t(s_{i},s_{j})$를 $x$축과 $\overrightarrow{Of(s_{i},s_{j})}$가 이루는 각도라고 정의함.
이때, $0 \leq s \leq 1$에 대하여 $t(0, s)$와 $t(s, 1)$를 조사하여 증명한다.

##### Application
* Rolle-Obstrowski’s Theorem
MVT의 2차원 확장. 할선의 기울기와 접선의 기울기 간의 포함 관계 설명.
* Gauss-Bonnet Theorem
증명 과정 중간에 사용됨.
___