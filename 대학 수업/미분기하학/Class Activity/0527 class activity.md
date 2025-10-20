___
다음에 주어진 원환면의 곡선 $\boldsymbol{X}\circ\gamma(t)$의 $(0, -1, 0)$에서 측지 곡률은 얼마인가?
$$
\gamma(t)=(\pi, t), \boldsymbol{X}(u,v) = ((2+\cos u)\sin v, (2+\cos u)\cos v, \sin u)
$$
![[Pasted image 20240527160657.png]]
___
Sol) We want to show that $\boldsymbol{X}\circ\gamma(t)$ is **geodesic** on $\boldsymbol{X}$.
Let $\alpha(t) = \boldsymbol{X}\circ\gamma(t) = (\sin t,\cos t,0)$.
It is easy to check that $\lVert \alpha(t) \rVert = 1$, so that $\alpha(t)$ is unit speed.
Note that $\alpha''(t) = (-\sin t, -\cos t, 0)$.
Compute $\mathbf{U}$.
$$
\begin{align}
\boldsymbol{X}_{u} &= (-\sin u\sin v, -\sin u\cos v, \cos u) \\
\boldsymbol{X}_{v} &= ((2+\cos u)\cos v, -(2+\cos u)\sin v, 0) \\
\boldsymbol{X}_{u}\times \boldsymbol{X}_{v} &= ((2+\cos u)\sin v\cos u, (2+\cos u)\cos u\cos v,(2+\cos u)\sin u) \\
\mathbf{U}(u, v) &=(\cos u\sin v,\cos u\cos v,\sin u) \\
\mathbf{U}_{\alpha(t)} &= (-\sin t,-\cos t, 0)
\end{align}
$$
So, $\alpha''(t)\parallel \mathbf{U}_{\alpha(t)}$. It means $\alpha(t)$ is **geodesic**, so, $\kappa_{g} \equiv 0$.
___

