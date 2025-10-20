### Chapter 13. the Gauss-Bonnet theorem.

#### 13.2 Gauss–Bonnet for curvilinear polygons
다음 정리를 숙지합시다.

> [!Theorem]
> Let $\gamma$ be a positively-oriented unit-speed curvilinear polygon with $n$ edges on a surface $\boldsymbol{\sigma}$, and let $\alpha_{1}, \alpha_{2}, \dots, \alpha_{n}$ be the interior angles at its vertices. Then, $$\int _{0}^{\ell(\gamma)}\kappa_{g} \, ds = \sum_{i=1}^{n}\alpha_{i} - (n-2)\pi - \int _{\text{int}(\gamma)}K \, d\mathcal{A}_{\boldsymbol{\sigma}}$$

##### Exercises 13.2.1

> [!Question] Problem
> Consider the surface of revolution $$\boldsymbol{\sigma}(u, v) = (f(u)\cos v, f(u)\sin v, g(u))$$ where $\gamma(u) = (f(u),0,g(u))$ is a unit-speed curve in the $xz$-plane. Let $u_{1}<u_{2}$ be constants, let $\gamma_{1}$ and $\gamma_{2}$ be the two parallels $u=u_{1}$ and $u=u_{2}$ on $\boldsymbol{\sigma}$, and let $R$ be the region of the $uv$-plane given by $$u_{1}\leq u\leq u_{2}, \ \ \ 0<v<2\pi$$. Compute $$\int _{0}^{\ell(\gamma_{1})}\kappa_{g} \, ds, \int _{0}^{\ell(\gamma_{2})}\kappa_{g} \, ds \text{   and   } \int _{R}K \, d\mathcal{A}_{\boldsymbol{\sigma}}$$, and explain your result on the basis of the Gauss–Bonnet theorem.

**Proof)**
회전면 위에 놓여있는 $\gamma_{1}$의 모습을 생각해봅시다. $\gamma_{1}$은 $xy$-평면에 평행한 원의 모습으로 나옴을 알 수 있습니다. 그리고 이에 대한 식은 $\gamma_{1}=(f(u_{1})\cos v, f(u_{1})\sin v, g(u_{1}))$으로 나옵니다. $\ell(\gamma_{1}) = 2\pi f(u_{1})$으로 나옴을 쉽게 알 수 있습니다.
$\kappa_{g}$를 $ds$로 적분하므로, $\kappa_{g}$는 길이 $s$에 대한 함수임을 유념합시다.
$\gamma$가 단위 속력 곡선일 때의 $\kappa_{g}$의 공식, $\kappa_{g} = \gamma''\cdot(\mathbf{U}\times \gamma')$를 생각해봅시다. 이를 활용하려면, $\gamma_{1}$이 단위 속력이어야 하는데, $v$에 대한 함수로 생각한다면 $\gamma_{1}$은 단위 속력이 아닙니다. $\gamma_{1}$을 길이 $s$에 대한 함수로 간주하여, $\frac{d\gamma_{1}}{ds}$을 구해봅시다.
$$
\begin{align}
\frac{ d\gamma_{1} }{ ds } &= \frac{ d\gamma_{1} }{ dv } \frac{ dv }{ ds } \\
&= \frac{ d\gamma_{1} }{ dv } \frac{1}{\frac{ ds }{ dv } }=
\frac{1}{f(u_{1})}f(u_{1})(-\sin v,\cos v, 0) \\
&=(-\sin v, \cos v, 0)
\end{align}
$$
마찬가지로, $\frac{ d^{2}\gamma_{1} }{ ds^{2} }$를 구해봅시다.
$$
\begin{align}
\frac{ d^{2}\gamma_{1} }{ ds^{2} } &=  \frac{ d^{2}\gamma_{1} }{ dv^{2} }\left( \frac{ dv }{ ds }  \right)^{2} + \cancel{ \frac{ d\gamma_{1} }{ dv } \frac{ d^{2}v }{ ds^{2} } }  \\
&= -\frac{1}{f(u_{1})}(\cos v, \sin v, 0)
\end{align}
$$
Unit normal vector $\mathbf{U}$를 구해봅시다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (f'(u)\cos v,f'(u)\sin v, g'(u)) \\
\boldsymbol{\sigma}_{v} &= (-f(u)\sin v, f(u)\cos v, 0) \\
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} &= (-fg'\cos v,fg'\sin v,ff') \\
\mathbf{U} &= \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert } \\
&=(g'\cos v,g'\sin v, f')
\end{align}
$$
$\gamma$는 unit speed이기 때문에 $f'^{2}+g'^{2}=1$임을 사용했습니다.
$\mathbf{U}\times \frac{ d\gamma_{1} }{ ds }$를 구해봅시다.
$$
\begin{align}
\mathbf{U}\times \frac{ d\gamma_{1} }{ ds } &= (g'\cos v,g'\sin v, f')\times(-\sin v, \cos v, 0) \\
&=(-f'\cos v, -f'\sin v, g')
\end{align}
$$
$\kappa_{g}$를 구해봅시다.
$$
\begin{align}
\kappa_{g} &= \frac{ d^{2}\gamma_{1} }{ ds^{2} }\cdot\left(\mathbf{U}\times \frac{ d\gamma_{1} }{ ds }\right) \\
&= -\frac{1}{f(u_{1})}(\cos v, \sin v, 0)\cdot(-f'(u_{1})\cos v, -f'(u_{1})\sin v, g'(u_{1})) \\
&=\frac{f'(u_{1})}{f(u_{1})}
\end{align}
$$
따라서, 이를 구하면 다음과 같습니다.
$$
\int _{0}^{\ell(\gamma_{1})}\kappa_{g} \, ds = \int _{0}^{2\pi f(u_{1})} \frac{f'(u_{1})}{f(u_{1})} \, ds = 2\pi f'(u_{1})
$$
마찬가지로, $\gamma_{2}$도 다음과 같습니다.
$$
\int _{0}^{\ell(\gamma_{2})}\kappa_{g} \, ds = 2\pi f'(u_{2})
$$
회전면에 대한 가우스 곡률이 아래와 같음을 상기시킵시다.
$$
K = -\frac{f''}{f}
$$
따라서, 다음과 같습니다.
$$
\begin{align}
\int _{R}K \, d\mathcal{A}_{\boldsymbol{\sigma}} &= \int_{0}^{2\pi} \int_{u_{1}}^{u_{2}}-\frac{f''}{f}  f\, du  \, dv \\
&= 2\pi f'(u_{1}) - 2\pi f'(u_{2}) \\
&= \int _{0}^{\ell(\gamma_{1})}\kappa_{g} \, ds - \int _{0}^{\ell(\gamma_{2})}\kappa_{g} \, ds
\end{align}
$$
![[Pasted image 20240616215631.png|center|300]]
위의 그림에서, 위의 Theorem을 적용한 결과라고 볼 수 있습니다.
이때, $n = 4$이고 $\sum\alpha = 2\pi$이고, $\gamma = -\gamma_{1} \cup (A\rightarrow B)\cup\gamma_{2} \cup (B \to A)$이므로, 위의 정리를 적용한 결과임을 쉽게 확인할 수 있습니다.
#### 13.4 Gauss–Bonnet for compact surfaces
문제를 해결하기 전에, 다음 정리들을 숙지합시다.

> [!Theorem]
> If $\mathcal{S}$ is a compact surface, there is a point of $\mathcal{S}$ at which its Gaussian curvature $K$ is $> 0$.

> [!Theorem]
> Let $\mathcal{S}$ be a compact surface. Then, for any triangulation of $\mathcal{S}$,
> $$\int_{\mathcal{S}}Kd\mathcal{A} = 2\pi \chi$$ where $\chi$is the Euler number of the triangulation.

> [!Theorem]
> The Euler number of the compact surface $T_{g}$ of genus $g$ is $2 − 2g$.
##### Exercises 13.4.1

> [!Question] Problem
> Show that, if a compact surface $\mathcal{S}$ is diﬀeomorphic to the torus $T_{1}$, then $$\int_{\mathcal{S}}Kd\mathcal{A} = 0$$. Can such a surface $\mathcal{S}$ have $K = 0$ everywhere?

**Proof)**
위의 정리를 사용합시다. $T_{1}$의 Genus가 $g = 1$임을 생각하면, $\chi(T_{1}) = 0$입니다.
따라서, $\int _{\mathcal{S}}K d\mathcal{A} = 2\pi \chi = 0$입니다.
이러한 Surface $\mathcal{S}$는 Compact하므로, 위의 정리에 의해서 $K$가 $0$보다 큰 점이 존재합니다. 따라서 모든 곳에서 $K = 0$이 될 수 없습니다.
##### Exercises 13.4.2
> [!Question] Problem
> Suppose that $\mathcal{S}$ is a compact surface whose Gaussian curvature $K$ is $> 0$ everywhere. Show that $\mathcal{S}$ is diﬀeomorphic to a sphere. Is the converse of this statement true?

**Proof)**
$(\Rightarrow)$
위의 정리를 사용합시다.
$$
\int _{\mathcal{S}} K\, d\mathcal{A} =2\pi \chi = 2\pi(2-2g) = 4\pi(1-g)
$$
따라서, $K$는 모든 점에서 $>0$이라고 했으므로, $4\pi(1-g) > 0$이어야 합니다.
이때, Genus는 음이 아닌 정수이므로, $g = 0$입니다. 따라서, $\mathcal{S}$는 $T_{0}$와 diffeomorphic합니다.
$(\not\Leftarrow)$
반구와 Cylinder를 이은 긴 콩알 모양의 Surface를 생각해봅시다.
이 Surface는 $T_{0}$와 diffeomorphic하지만, Cylinder부분에서 $K = 0$이므로, 거짓입니다.