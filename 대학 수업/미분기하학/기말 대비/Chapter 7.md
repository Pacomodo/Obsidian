___
### Chapter 7. Curvature of surfaces
#### 7.1 The second fundamental form
##### Examples 7.1.1
평면의 방정식 $\boldsymbol{\sigma}(u,v) = \mathbf{a} + u\mathbf{p}+v\mathbf{q}$를 생각해봅시다.
$\boldsymbol{\sigma}_{u} = \mathbf{p}, \boldsymbol{\sigma}_{v} = \mathbf{q}$를 만족하고, $\mathbf{p}, \mathbf{q}$는 상수 벡터입니다.
$\boldsymbol{\sigma}_{uu} = \boldsymbol{\sigma}_{uv} = \boldsymbol{\sigma}_{vv} = \mathbf{0}$이므로, 평면의 방정식에서의 제2형식은 $0$임을 확인할 수 있습니다.
##### Examples 7.1.2
회전면(Surface of revolution)의 방정식을 생각해봅시다.

> [!Recall] 회전면의 방정식
> $$\boldsymbol{\sigma}(u,v) = (f(u)\cos v, f(u)\sin v, g(u))$$

이 방정식은 $xz$평면 위에 놓여있는 곡선 $u \mapsto (f(u), 0, g(u))$을 한 바퀴 돌린 회전면입니다. 편의 상 $f(u) > 0$이라고 합시다. 이 곡선이 단위 속력(unit speed)이라고 가정합시다. 즉, $f'^{2}+g'^{2} = 1$이라고 합시다.
회전면 상에서의 $L,M,N$을 구해봅시다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (f'(u)\cos v, f'(u)\sin v, g'(u)) \\
\boldsymbol{\sigma}_{v} &= (-f(u)\sin v, f(u)\cos v, 0) \\
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} &= (-fg'\cos v,-fg'\sin v,ff') \\
\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert &= f\sqrt{ g'^{2}+f'^{2} } = f  \\
\mathbf{U}&= \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert } = (-g'\cos v,-g'\sin v,f') \\
\end{align}
$$
$$
\begin{align}
\boldsymbol{\sigma}_{uu} &= (f''\cos v,f''\sin v,g'') \\
\boldsymbol{\sigma}_{uv} &= (-f'\sin v,f'\cos v, 0) \\
\boldsymbol{\sigma}_{vv} &= (-f\cos v,-f\sin v,0) \\
L &= \boldsymbol{\sigma}_{uu}\cdot \mathbf{U} = -f''g' + f'g'' \\
M &= \boldsymbol{\sigma}_{uv}\cdot \mathbf{U} = 0 \\
N &= \boldsymbol{\sigma}_{vv}\cdot \mathbf{U} = fg'
\end{align}
$$
따라서 제 2형식은 다음과 같습니다.
$$
Ldu^{2}+2Mdudv+Ndv^{2} = (f'g''-f''g')du^{2}+(fg')dv^{2}
$$
* 이를 이용하여 단위 구(Unit sphere) $S^{2}$의 2형식을 생각해봅시다.
$xz$평면의 오른쪽 반원을 한바퀴 돌린 것이라고 생각하면 됩니다. $u,v$대신 $\theta,\varphi$라고 쓰겠습니다. 따라서, $f(\theta) = \cos \theta, g(u) = \sin \theta$라고 생각할 수 있습니다.
$f'g'' - f''g' = \sin ^{2}\theta + \cos ^{2}\theta = 1, fg' = \cos ^{2}\theta$이므로 다음과 같습니다.
$$
d\theta^{2}+\cos ^{2}\theta d\varphi^{2}
$$
* 이를 이용하여 단위 원통(Unit cylinder)의 경우를 생각해봅시다.
$xz$평면 위의 $x=1$을 한바퀴 돌린 것이라고 생각하면 됩니다. 따라서, $f(u) = 1, g(u)=u$라고 생각할 수 있습니다.($xz$평면 위의 곡선이 단위 속력을 만족해야 한다는 조건을 유념합시다.)
$f'g'' - f''g' = 0, fg' = 1$이므로 다음과 같습니다.
$$
dv^{2}
$$
##### Exercises 7.1.2

> [!Question] Problem
> Suppose that the second fundamental form of a surface patch $\boldsymbol{\sigma}$ is zero everywhere.
> Prove that $\boldsymbol{\sigma}$ is an open subset of a plane. This is the analogue for surfaces of the theorem that a curve with zero curvature everywhere is part of a straight line.

Sol)
Surface patch $\boldsymbol{\sigma}$위의 임의의 점 $\mathbf{p} = \boldsymbol{\sigma}(u_{0},v_{0})$라고 하고, 여기서 정의된 접평면을 $T_{\mathbf{p}}S$라고 합시다.
$\boldsymbol{\sigma}$의 제2형식이 모든 곳에서 $0$이라고 했으므로, 제2형식의 계수 $L, M, N$또한 모든 곳에서 $0$이 됩니다. 즉, 다음이 성립합니다.
$$
\begin{align}
L &= \boldsymbol{\sigma}_{uu}\cdot \mathbf{U} = 0 \\
M &= \boldsymbol{\sigma}_{uv}\cdot \mathbf{U} = 0\\
N &= \boldsymbol{\sigma}_{vv}\cdot \mathbf{U} = 0
\end{align}
$$
다음 보조정리를 상기시킵시다.

> [!Recall]
> $$\begin{align}
L &= -{<}\boldsymbol{\sigma}_{u}, \mathbf{U}_{u}{>} = -\boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{u}\\
M &= -{<}\boldsymbol{\sigma}_{u}, \mathbf{U}_{v}{>} = -\boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{v} \\
&= -{<}\boldsymbol{\sigma}_{v}, \mathbf{U}_{u}{>} = -\boldsymbol{\sigma}_{v}\cdot \mathbf{U}_{u} \\
N &= -{<}\boldsymbol{\sigma}_{v}, \mathbf{U}_{v}{>} = -\boldsymbol{\sigma}_{v}\cdot \mathbf{U}_{v}
\end{align}$$

이 보조정리에 대한 증명은 다음과 같습니다.
$$
\begin{align}
\frac{ \partial }{ \partial u } {<}\boldsymbol{\sigma}_{u}, \mathbf{U}{>} &= \boldsymbol{\sigma}_{uu}\cdot \mathbf{U} + \boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{u} \\
&=L + \boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{u} = 0 \\
\rightarrow L &= - {<}\boldsymbol{\sigma}_{u},\mathbf{U}_{u}{>} =-\boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{u}
\end{align}
$$
$M, N$에 대한 증명 과정도 $u$와 $v$에 대한 편미분을 해주면 됩니다.

이 보조정리를 활용하면, 다음과 같은 결과를 얻을 수 있습니다.
$$
\begin{align}
\boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{u} &= 0 \\
\boldsymbol{\sigma}_{u}\cdot \mathbf{U}_{v} &= 0 = \boldsymbol{\sigma}_{v}\cdot \mathbf{U}_{u}\\
\boldsymbol{\sigma}_{v}\cdot \mathbf{U}_{v} &= 0
\end{align}
$$
즉, $\boldsymbol{\sigma}_{u}$와 $\mathbf{U}_{u}$는 서로 수직하고, $\boldsymbol{\sigma}_{v}$와 $\mathbf{U}_{u}$또한 서로 수직합니다. $\boldsymbol{\sigma}_{u}, \boldsymbol{\sigma}_{v} \in T_{\mathbf{p}}S$이기 때문에, $\mathbf{U}_{u} \perp T_{\mathbf{p}}S$입니다.
마찬가지로, $\boldsymbol{\sigma}_{u}$와 $\mathbf{U}_{v}$는 서로 수직하고, $\boldsymbol{\sigma}_{v}$와 $\mathbf{U}_{v}$또한 서로 수직합니다. $\boldsymbol{\sigma}_{u}, \boldsymbol{\sigma}_{v} \in T_{\mathbf{p}}S$이기 때문에, $\mathbf{U}_{v} \perp T_{\mathbf{p}}S$입니다. 또한, $\mathbf{U} \perp T_{\mathbf{p}}S$이기 때문에, $\mathbf{U} \parallel \mathbf{U}_{u}$, $\mathbf{U} \parallel \mathbf{U}_{v}$가 성립합니다.

다음을 생각해봅시다.
$$
\begin{align}
\mathbf{U}\cdot \mathbf{U} = 1 \xrightarrow{\frac{ \partial }{ \partial u }  }2\mathbf{U}\cdot\mathbf{U}_{u} = 0 \\
\mathbf{U}\cdot \mathbf{U} = 1 \xrightarrow{\frac{ \partial }{ \partial v }  }2\mathbf{U}\cdot\mathbf{U}_{v} = 0 \\
\end{align}
$$
따라서, $\mathbf{U}\perp\mathbf{U}_{u}$, $\mathbf{U}\perp\mathbf{U}_{v}$가 성립합니다.
$\mathbf{U}\perp \mathbf{U}_{u}$와 $\mathbf{U}\parallel\mathbf{U}_{u}$가 동시에 성립하려면, $\mathbf{U}$와 $\mathbf{U}_{u}$ 중 하나가 $\mathbf{0}$이어야 하는데, $\mathbf{U}$는 단위 벡터이므로 $\mathbf{U}_{u} = \mathbf{0}$입니다. 마찬가지로, $\mathbf{U}_{v} = \mathbf{0}$입니다.
따라서, $\mathbf{U}$는 상수 벡터입니다.
$T_{\mathbf{p}}S \perp \mathbf{U}$임을 상기시킵시다.
$$
\begin{align}
(\boldsymbol{\sigma}\cdot \mathbf{U})_{u} &= \boldsymbol{\sigma}_{u}\cdot \mathbf{U} + \boldsymbol{\sigma}\cdot \mathbf{U}_{u} \\
\xrightarrow{\mathbf{U}_{u} = \mathbf{0}} &=\boldsymbol{\sigma}_{u}\cdot \mathbf{U} = 0 \\
(\boldsymbol{\sigma}\cdot \mathbf{U})_{v}  &=\boldsymbol{\sigma}_{v}\cdot \mathbf{U} + \boldsymbol{\sigma}\cdot \mathbf{U}_{v} \\
\xrightarrow{\mathbf{U}_{v} = \mathbf{0}} &=\boldsymbol{\sigma}_{v}\cdot \mathbf{U} = 0
\end{align}
$$
따라서, 어떠한 상수 $C$에 대하여, $\boldsymbol{\sigma}\cdot \mathbf{U} = C$입니다.
따라서, $\boldsymbol{\sigma}$는 $\mathbf{v}\cdot \mathbf{U} = C$라는 평면의 방정식의 open subset입니다.

##### Exercises 7.3.2

> [!Question] Problem
> Show that the normal curvature of any curve on a sphere of radius $r$ is $\pm \frac{1}{r}$.

Sol)
단위 속력 곡선일 때, $\kappa_{n} = \gamma''\cdot\mathbf{U}$임을 상기합시다.
$\gamma(s)$가 중심이 $\mathbf{a}$이고 반지름이 $r$인 구면 위의 단위 속력 곡선이라고 합시다. 그렇다면, $(\gamma(s)-\mathbf{a})\cdot (\gamma(s)-\mathbf{a})=r^{2}$를 만족합니다.
양변을 $s$로 미분합시다.
$2\gamma'\cdot(\gamma-\mathbf{a})=0\rightarrow\gamma'\cdot(\gamma-\mathbf{a})=0\rightarrow \gamma''\cdot(\gamma-\mathbf{a}) + \gamma'\cdot \gamma' = 0$
단위 속력 곡선이기 때문에 $\gamma'\cdot \gamma' = 1$입니다. 따라서, $\gamma''\cdot(\gamma-\mathbf{a})=-1$입니다.
$\gamma(s)$의 한 점에서의 $\mathbf{U}$는 $\pm \frac{\gamma(s)-\mathbf{a}}{r}$이므로, $\kappa_{n} = \gamma''\cdot \mathbf{U} = \pm \frac{\gamma''\cdot(\gamma-\mathbf{a})}{r} = \mp \frac{1}{r}$.
##### Exercises 7.3.3

> [!Question] Problem
> Compute the geodesic curvature of any circle on sphere (not necessarily a great circle).

Sol)
다음과 같은 Proposition을 상기합시다.

> [!Recall]
> $\gamma(s)$를 $\boldsymbol{\sigma}$위에 놓여있는 단위 속력 곡선이라고 합시다. $\kappa$를 $\gamma$의 곡률이라고 합시다. $\theta$를 $\gamma$의 Unit normal vector $\mathbf{N}$과 $\boldsymbol{\sigma}$의 Unit normal vector $\mathbf{U}$사이의 각도라고 합시다. 그러면 다음과 같은 식이 성립합니다.
> 1. $\kappa^{2} = \kappa_{n}^{2} + \kappa_{g}^{2}$
> 2. $\kappa_{n} = \kappa \cos \theta$ and $\kappa_{g} = \kappa \sin \theta$

반지름이 $R$인 구면을 생각해봅시다.
구면 위에 놓인 임의의 원 $C_{1}$이 결정짓는 평면을 $P_{1}$이라고 합시다. $P_{1}$과 평행한 평면 $P_{2}$를 생각하는데, $P_{2}$와 구면이 만나는 점들의 모임이 구면 위의 대원(great circle)이 되도록 $P_{2}$를 생각해봅시다. 그리고 이 대원을 $C_{2}$라고 해봅시다. 즉, 위도와 경도에서 위도를 생각해봅시다. $C_{1}$이 위치한 위도를 $\theta$라고 합시다.(이건 직접 그림 그려보는게 더 빠를듯)
$C_{1}$의 반지름을 $r$이라고 합시다. 구면의 반지름을 $R$이라고 했으므로, $C_{2}$의 반지름은 $R$입니다.
$C_{1}$위의 한 점에서 나오는 Unit normal vector $\mathbf{N}$과 그 점에서 나오며 구면과 수직한 Unit normal vector $\mathbf{U}$를 생각합시다. 둘 사이의 각도는 $\theta$입니다.
$C_{1}$의 곡률 $\kappa$는 $\frac{1}{r}$입니다. 또한, $r = R\cos \theta$입니다.
따라서, $C_{1}$의 geodesic curvature $\kappa_{g} = \kappa \sin \theta = \frac{1}{R\cos \theta}\sin \theta = \pm \frac{1}{R}\tan \theta$입니다.

___
