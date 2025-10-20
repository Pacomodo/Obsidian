### Chapter 12. Minimal surfaces
#### 12.1 Plateau’s problem

> [!Recall] 
> Minimal Surface는 $\mathrm{H} = 0$인 곡면이다.
> $$\mathrm{H} = \frac{\kappa_{1}+\kappa_{2}}{2} = \frac{GL+EN-2FM}{2(EG-F^{2})}$$

##### Examples 12.1.4

> [!example] Catenoid
> $$\boldsymbol{\sigma}(u,v) = (\cosh u \cos v, \cosh u \sin v, u)$$

위의 예시는 Minimal Surface입니다.
편의상 $\cosh u = f(u)$라고 합시다.
$E,F,G$는 다음과 같습니다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (f'\cos v, f'\sin v, 1) \\
\boldsymbol{\sigma}_{v} &= (-f\sin v, f\cos v, 0) \\
E = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u} &= f'^{2}+1 = \sinh ^{2}u+1 = \cosh ^{2}u = f^{2} \\
F = \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v} &= 0 \\
G = \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v} &= f^{2}
\end{align}
$$
$L, M, N$은 다음과 같습니다.
$$
\begin{align}
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} &= (-f\cos v, -f\sin v, ff') \\
\mathbf{U} &= \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert } \\
&= \frac{1}{\sqrt{f^{2}(1+f'^{2})}}(-f\cos v, -f\sin v, ff') \\
&= \frac{1}{f}(-\cos v, -\sin v, f') \\
\boldsymbol{\sigma}_{uu} &= (f\cos v, f\sin v, 0) \\
\boldsymbol{\sigma}_{uv} &= (-f'\sin v, f'\cos v, 0) \\
\boldsymbol{\sigma}_{vv} &= (-f\cos v, -f\sin v, 0) \\
L &= \boldsymbol{\sigma}_{uu}\cdot \mathbf{U} = -1 \\
M &= \boldsymbol{\sigma}_{uv}\cdot \mathbf{U} = 0 \\
N &= \boldsymbol{\sigma}_{vv}\cdot \mathbf{U} = 1
\end{align}
$$
따라서, $GL+EN-2FM = -f^{2} + f^{2} - 2\cdot 0 \cdot 0 = 0$이므로, $\mathrm{H} = 0$입니다.
___
##### Exercises 12.1.1

> [!Question] Problem
> Show that the Gaussian curvature of a minimal surface is ≤ 0 everywhere, and that it is zero everywhere if and only if the surface is an open subset of a plane.

**Proof)**
Minimal Surface의 정의를 생각하면, $\mathrm{H}$가 모든 곳에서 $0$이므로, Principal Curvature가 모든 곳에서 $\kappa_{1}+\kappa_{2} = 0$를 만족합니다.
Gaussian Curvature $K = \kappa_{1}\kappa_{2}$이므로, 모든 곳에서 $K \leq 0$임을 쉽게 확인할 수 있습니다.
$K = 0 \iff \kappa_{1} = \kappa_{2} = 0 \iff \kappa_{n} = 0 \iff L = M = N = 0$ (by Exercise 7.1.1)
##### Exercises 12.1.3

> [!Question] Problem
> Show that there is no compact minimal surface.

**Proof)**
다음 정리를 상기시킵시다.

> [!Recall] 
> If $\mathcal{S}$ is a compact surface, there is a point of $\mathcal{S}$ at which its Gaussian curvature $K$ is $> 0$.

Compact한 minimal surface가 있다고 가정하면, $K > 0$인 지점이 무조건 하나는 존재하는데, 이는 위의 Exercise와 모순입니다.
___
#### 12.2 Examples of minimal surfaces

##### Examples 12.2.5
$$
\boldsymbol{\sigma}(u, v) = \left( u-\frac{u^{3}}{3} + uv^{2},v-\frac{v^{3}}{3}+u^{2}v,u^{2}-v^{2} \right)
$$
##### Examples 12.2.6
$$
z = \ln\left( \frac{\cos y}{\cos x} \right)
$$
Note that the surface exists only when $\cos x$ and $\cos y$ are both $> 0$ or both $< 0$.

위의 예시들은 직접 확인해보세요.
___
