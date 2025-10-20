___
### Four-vertex theorem(사정점 정리)
##### Statement
Every smooth simple closed plane curve has at least 4 extrema.
##### Example
가장 간단한 예시로, 타원을 생각해볼 수 있다. 타원은 2개의 극소와 2개의 극대를 가짐을 확인할 수 있다.
##### Proof Idea of 4 vertex theorem(Osserman)
Osserman은 2개의 보조정리를 결합하여 위의 정리를 증명했다.
$\gamma$를 smooth simple closed plane curve, $C$를 $\gamma$의 외접원이라고 하면 다음 보조정리 두 개가 성립한다. 
1. $\gamma \cap C$는 최소한 2개의 원소를 지닌다.
2. 만약 $\gamma \cap C$이 $n$개의 원소를 가지고 $n>1$이라면, $\gamma$는 $2n$개 이상의 extrema을 갖는다.
1번 보조정리와 2번 보조정리를 결합하여 증명한다.
2번 보조정리는 $\gamma$를 $\gamma \cap C$의 점들로 분할하여 여러 개의 Arc들로 쪼갠 후에 Arc들의 곡률과 엮어 증명한다.
##### Application
기하학적 의미로는 평형점의 의미를 지니는데, 3차원에서는 이러한 평형점이 존재하지 않는 굄뵈츠라는 반례적 성격을 지닌 도형이 존재한다.

___
### Osculating sphere(접촉구)
##### Statement
접촉원(Osculating Circle)의 3차원 확장. 식은 다음과 같이 정의된다.
$$
\mathbf{V} = \alpha(s_{0})+\frac{1}{\kappa(s_{0})}\mathbf{N}(s_{0}) -\frac{\kappa'(s_{0})}{\kappa^{2}(s_{0})\tau(s_{0})}\mathbf{B}(s_{0})
$$
이는 공간 곡선 $\alpha$의 한 점 $\alpha(s_{0})$에서 접하는 접촉구의 식이다.
위의 식은 F-S Formula와 Rolle's Thm에 의해 유도된다.
접촉구의 접촉도가 증가할 수록 중심의 위치가 제한이 되다가 접촉도가 3이 되면 중심의 위치는 결정이 되어 버린다
___
### 3차원 로렌츠 공간
##### Statement
3차원 Lorentz 공간 $\mathbb{L}^{3}$는 다음과 같이 정의된다
$$
\mathbb{L}^{3}=\{(x,y,t)\in\mathbb{R}^3:ds^2=dx^2+dy^2-dt^2\}
$$
특수 상대성 이론에서 시공간을 Lorentz 평면(공간)의 형태로 표현하며, 벡터($\overrightarrow{v}$)들을 원점으로부터의 거리로 다음과 같이 구분한다.
$$
\begin{align}
\text{light-like vector  } (d(0,\overrightarrow{v})=0)\\
\text{space-like vector  } (d(0,\overrightarrow{v})>0)\\
\text{time-like vector  } (d(0,\overrightarrow{v})<0)\\
\end{align}
$$
___
