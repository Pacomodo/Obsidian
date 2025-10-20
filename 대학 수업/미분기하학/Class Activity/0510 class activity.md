___

Torus: for $0<r<R$, $\boldsymbol{\sigma}(u,v) = ((R+r\cos u)\cos v, (R+r\cos u)\sin v, r\sin u)$.
* Compute $L,M,N$
- Find points where
(1) $M^{2}-LN < 0$
(2) $M^{2}-LN > 0$
(3) $M^{2}-LN = 0$ but $L^{2}+M^{2}+N^{2} \neq 0$.

___

Sol)
* Compute $L,M,N$.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (-r\sin u\cos v, -r\sin u \sin v, r\cos u) \\
\boldsymbol{\sigma}_{v} &= (-(R+r\cos u)\sin v, (R+r\cos u)\cos v, 0) \\
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}&= (-r(R+r\cos u)\cos u\cos v \\
&\ \ \ \ \ \ ,-r(R+r\cos u)\cos u\sin v \\
&\ \ \ \ \ \ ,-r(R+r\cos u)\sin u (\cos ^{2} v+\sin ^{2}v)) \\
\boldsymbol{U} &= \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert } \\ \\
&=(-\cos u\cos v, -\cos u\sin v, -\sin u) \\
\boldsymbol{\sigma}_{uu} &= (-r\cos u\cos v, -r\cos u\sin v, -r\sin u) \\
\boldsymbol{\sigma}_{uv} &= (r\sin u \sin v, -r\sin u \cos v, 0) \\
\boldsymbol{\sigma}_{vv} &= (-(R+r\cos u)\cos v,-(R+r\cos u)\sin v, 0) \\
L &= \boldsymbol{\sigma}_{uu}\cdot \boldsymbol{U} \\
&=r\cos ^{2}u\cos ^{2}v +r\cos ^{2}u\sin ^{2}v+r\sin ^{2} u \\
&=r \\
M &= \boldsymbol{\sigma}_{uv}\cdot \boldsymbol{U} \\
&= -r\cos u\sin u \cos v\sin v+r\cos u\sin u\cos v\sin v \\
&= 0 \\
N &= \boldsymbol{\sigma}_{vv}\cdot \boldsymbol{U} \\
&= (R+r\cos u)\cos u\cos ^{2}v+(R+r\cos u)\cos u\sin ^{2}v \\
&= (R+r\cos u)\cos u
\end{align}
$$

* Find points where
(1) $M^{2}-LN < 0$
(2) $M^{2}-LN > 0$
(3) $M^{2}-LN = 0$ but $L^{2}+M^{2}+N^{2} \neq 0$.
$$
D = M^{2}-LN = -r(R+r\cos u)\cos u
$$
$0 < r < R$이기 때문에 $(R+r\cos u)$는 항상 0보다 크다.
따라서, 부호를 따져주기 위해서는 $-\cos u$의 부호만 따져주면 충분하다.
따라서,
$$
\begin{align}
(1) & =\left\{ (u,v) | 0 \leq u < \frac{\pi}{2}, \frac{3\pi}{2} <u<2\pi \right\} \\
(2) & =\left\{ (u,v) | \frac{\pi}{2}<u< \frac{3\pi}{2} \right\} \\
(3) & =\left\{ (u,v) | u = \frac{\pi}{2}, \frac{3\pi}{2} \right\} 
\end{align}
$$
