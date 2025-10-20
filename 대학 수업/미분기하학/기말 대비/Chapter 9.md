### Chapter 9. Geodesics
#### 9.1 Deﬁnition and basic properties
Geodesic의 정의를 상기시킵시다.

> [!Definition]
> $\gamma$ on a surface $\mathcal{S}$ is geodesic $\iff$ $\gamma'' = 0$ or $\gamma''\perp T_{\gamma'}\mathcal{S}$.

##### Propositions 9.1.2

> [!Theorem]
> Any geodesic has constant speed.

**Proof)**
$\gamma'\cdot \gamma'' = 0 \rightarrow 2\gamma'\cdot \gamma'' = 0 \rightarrow \frac{d}{dt}{<}\gamma',\gamma'{>}=0\rightarrow{<}\gamma',\gamma'{>} = C\rightarrow\lVert \gamma' \rVert=C$
##### Propositions 9.1.3

> [!Theorem]
> A unit-speed curve on a surface is a geodesic $\iff$ $\kappa_{g} = 0$ everywhere.

**Proof)**
$(\Rightarrow)$
$\kappa_{g} = \gamma''\cdot(\mathbf{U}\times \gamma') = 0$ since $\mathbf{U}\times \gamma' \in T_{\gamma'}\mathcal{S}$.
$(\Leftarrow)$
$\kappa_{g} = \gamma''\cdot(\mathbf{U}\times \gamma') = 0 \rightarrow \gamma''\perp(\mathbf{U}\times \gamma')$
$\gamma''\perp \gamma'$(Since unit-speed)
So, $\gamma''\perp T_{\gamma'}\mathcal{S}$.
___
#### 9.2 Geodesic equations

다음 정리를 상기시킵시다.
> [!Theorem]
> $\gamma = \boldsymbol{\sigma}(u(t), v(t))$ is **Geodesic**
> $$\iff \star \begin{cases}
\displaystyle\frac{d}{dt} (Eu'+Fv') = \frac{1}{2}\left(E_{u}(u')^{2}+2F_{u}(u')(v')+G_{u}(v')^{2}\right) \\[5pt]
\displaystyle\frac{d}{dt} (Fu'+Gv') = \frac{1}{2}\left(E_{v}(u')^{2}+2F_{v}(u')(v')+G_{v}(v')^{2}\right) 
\end{cases}$$
##### Examples 9.2.2
구에 대한 Geodesic을 Geodesic Equation으로 구함.
존나 복잡한데 계산원툴
##### Examples 9.2.8
> [!example] $\boldsymbol{\sigma}(u,v)=(\cos u,\sin u, v)$
![[__ (1)_page-0001.jpg|center|300]]

먼저 $E,F,G$를 계산해봅시다.
$$
\begin{cases}
\boldsymbol{\sigma}_{u} = (-\sin u, \cos u, 0) \\[3pt]
\boldsymbol{\sigma}_{v} = ( \ \ \ \ \ \ 0\ \ \ \ , \ \ \ \ 0\ \ , 1)
\end{cases}
$$
$$
\begin{cases}
E = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u} = 1  \\
F = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v} = 0 \\
G = \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v} = 1
\end{cases}
$$
따라서 Geodesic Equation은 다음과 같이 작성할 수 있습니다.
$$
\begin{align}
&\star\begin{cases}
\displaystyle\frac{d}{dt} (Eu'+Fv') = \frac{1}{2}\left(E_{u}(u')^{2}+2F_{u}(u')(v')+G_{u}(v')^{2}\right) \\[5pt]
\displaystyle\frac{d}{dt} (Fu'+Gv') = \frac{1}{2}\left(E_{v}(u')^{2}+2F_{v}(u')(v')+G_{v}(v')^{2}\right) 
\end{cases} \\
\Rightarrow &\star\begin{cases}
\displaystyle\frac{d}{dt} (u') = 0 \\[5pt]
\displaystyle\frac{d}{dt} (v') = 0
\end{cases} \\
\Rightarrow &\ \begin{cases}
u''(t) = 0 \\[5pt]
v''(t) = 0
\end{cases} \\
\Rightarrow &\ \begin{cases}
u(t) = c_{1}t+d_{1} \\[5pt]
v(t) = c_{2}t+d_{2}
\end{cases} \\
\end{align}
$$
$$
\begin{align}
\Rightarrow \gamma(t) &= \boldsymbol{\sigma}(c_{1}t+d_{1}, c_{2}t+d_{2}) \\
&= (\cos(c_{1}t+d_{1}),\sin(c_{1}t+d_{1}),c_{2}t+d_{2})
\end{align}
$$

만약, $c_{1} = 0$라면, $\gamma(t) = (\cos d_{1}, \sin d_{1}, c_{2}t+d_{2})$이 됩니다.
즉, $x, y$는 고정되있고 $t$에 따라서 $z$의 값만 변하므로, 원기둥의 특정 세로 선이라고 할 수 있습니다.
![[__ (2)_page-0001.jpg|center|300]]

만약, $c_{2}=0$라면, $\gamma(t) = (\cos(c_{1}t+d_{1}),\sin(c_{1}t+d_{1}), d_{2})$가 됩니다.
즉, $z$의 값은 고정되있고 $t$에 따라서 $x, y$의 값만 변하므로, 원기둥의 특정 가로 선이라고 할 수 있습니다.
![[__ (3)_page-0001.jpg|center|300]]

만약, $c_{1}c_{2}\neq 0$라면, $\gamma(t) =(\cos(c_{1}t+d_{1}),\sin(c_{1}t+d_{1}),c_{2}t+d_{2})$가 됩니다.
즉, Helix의 모양을 가지게 됩니다.
![[__ (4)_page-0001.jpg|center|300]]

##### Exercises 9.2.2

> [!Question] Problem
> Use Corollary 9.2.7 to ﬁnd all the geodesics on a circular cone.

**Proof)**
Corollary 9.2.7은 다음과 같은 Statement이다.

> [!Theorem]
> Any local isometry between two surfaces takes the geodesics of one surface to the geodesics of the other.

등거리 사상(Isometry)은 한 Surface의 Geodesic을 다른 Surface의 Geodesic으로 옮긴다는 정리다.

$$
\boldsymbol{\sigma}(u,v) = (u\cos v,u\sin v, u)
$$
where $u > 0, 0<v<2\pi$가 Circular cone인데, 이 Surface를 재매개화해서 Isometry로 만들면, $\boldsymbol{\sigma}(u,v) = (u\sqrt{ 2 }\cos \frac{v}{\sqrt{ 2 }}, u\sqrt{ 2 }\sin \frac{v}{\sqrt{ 2 }}, 0)$이다.(Exercise 6.2.1의 내용).
Isometry인지 판단하는 방법은 재매개화를 해서 제1형식이 같은지 확인하면 된다.
저렇게 Surface를 재매개화하면 $xy$-평면과 동일하고, 여기 위에서의 직선만을 따지면 된다.

##### Exercises 9.2.3

> [!Question] Problem
> Find the geodesics on the unit cylinder by solving the geodesic equations.

**Proof)**
위에서 함.

##### Exercises 9.2.5

> [!Question] Problem
> Let $\gamma(t)$ be a unit-speed curve on the helicoid $$\boldsymbol{\sigma}(u,v)=(u\cos v,u\sin v, v)$$
> Show that $$u'^{2}+(1+u^{2})v'^{2} = 1$$
> Show that $$v'=\frac{a}{1+u^{2}}$$
> Find Geodesic when $a = 0$ or $a = 1$
> 그 뒤로 곁다리 문제 더 있는데 안나올듯

> [!example] $\boldsymbol{\sigma}(u,v)=(u\cos v, u\sin v, v)$
> ![[__ (5)_page-0001.jpg|center|300]]

먼저 $E,F,G$를 계산해봅시다.
$$
\begin{cases}
\boldsymbol{\sigma}_{u} = (\ \ \ \ \ \cos v, \ \  \  \sin v  ,0) \\[3pt]
\boldsymbol{\sigma}_{v} = ( -u\sin v, u\cos v, 1)
\end{cases}
$$
$$
\begin{cases}
E = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u} = 1  \\
F = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v} = 0 \\
G = \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v} = u^{2}+1
\end{cases}
$$
1. **$\gamma$ is unit speed.**
$\gamma$가 unit speed가 되는 조건을 따져봅시다.
Geodesic의 정의에서는 $\gamma$가 unit speed일 수도 있고, 아닐 수도 있음에 유의합시다. ($\gamma$가 unit speed일 때라면 $\kappa_{g}$와의 관계성을 이야기 할 수 있습니다.)
$$
\begin{align}
1=\lVert \gamma' \rVert ^{2} &= \gamma'\cdot \gamma' \\
&=(\boldsymbol{\sigma}_{u}u'+\boldsymbol{\sigma}_{v}v')\cdot(\boldsymbol{\sigma}_{u}u'+\boldsymbol{\sigma}_{v}v') \\
&= \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u}(u')^{2} + 2\boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v}(u')(v')+\boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v}(v')^{2} \\
&= E(u')^{2}+2F(u')(v')+G(v')^{2} \\
\xrightarrow{E, F, G} &= (u')^{2}+(u^{2}+1)(v')^{2}
\end{align}
$$
따라서 다음 조건을 만족하면 $\gamma$가 unit speed가 된다고 말할 수 있습니다.

2. **$\gamma$ is geodesic.**
$\gamma$가 Geodesic이라면 Geodesic equation을 만족시켜야 합니다.
$$
\begin{align}
&\star\begin{cases}
\displaystyle\frac{d}{dt} (Eu'+Fv') = \frac{1}{2}\left(E_{u}(u')^{2}+2F_{u}(u')(v')+G_{u}(v')^{2}\right) \\[5pt]
\displaystyle\frac{d}{dt} (Fu'+Gv') = \frac{1}{2}\left(E_{v}(u')^{2}+2F_{v}(u')(v')+G_{v}(v')^{2}\right) 
\end{cases} \\
\Rightarrow &\star\begin{cases}
\displaystyle\frac{d}{dt} (u') = \frac{1}{2}(2u(v')^{2}) =u(v')^{2} \\[5pt]
\displaystyle\frac{d}{dt} ((u^{2}+1)v') = 0
\end{cases} \\
\Rightarrow &\ \begin{cases}
u'' = u(v')^{2} \\[5pt]
(u^{2}+1)v' = c \text{ (for some constant)}
\end{cases} \\
&\Rightarrow v' = \frac{c}{u^{2}+1} \\
\Rightarrow &\ u''=u\left( \frac{c}{u^{2}+1} \right)^{2}
\end{align}
$$
따라서 다음 ODE를 풀면 Geodesic을 구할 수 있다고 말할 수 있습니다.
Unit speed인 Geodesic을 구하고 싶다면, 위의 조건과 더 엮어서 식을 더 정리할 수도 있을 것입니다.