___
아래 곡면이 극소곡면 minimal surface임을, 즉 평균곡률이 모든 점에서 0임을 증명해봅시다.
$$
\boldsymbol{X}(u, v) = \left( u-\frac{u^{3}}{3} + uv^{2},-v+\frac{v^{3}}{3}-vu^{2},u^{2}-v^{2} \right)
$$
___
Sol) Compute $\boldsymbol{X}_{u}, \boldsymbol{X}_{v}, \boldsymbol{U}$.
$$
\begin{align}
\boldsymbol{X}_{u} &= (1-u^{2}+v^{2},-2uv, 2u) \\
\boldsymbol{X}_{v} &= (2uv, -1+v^{2}-u^{2}, -2v) \\
\boldsymbol{X}_{u}\times \boldsymbol{X}_{v} &= (2uv^{2}+2u+2u^{3}, 2v+2u^{2}v+2v^{3}, (v^{2}-u^{2})^{2}-1+4u^{2}v^{2}) \\
&=(2uv^{2}+2u+2u^{3},2v+2u^{2}v+2v^{3},(u^{2}+v^{2})^{2}-1) \\
&=((u^{2}+v^{2}+1)(2u),(u^{2}+v^{2}+1)(2v),(u^{2}+v^{2}+1)(u^{2}+v^{2}-1)) \\
\boldsymbol{U} &= \frac{1}{\sqrt{ 4u^{2}+4v^{2}+u^{4}+v^{4}+1+2u^{2}v^{2}-2u^{2}-2v^{2} }}(2u,2v,u^{2}+v^{2}-1) \\
&= \frac{1}{u^{2}+v^{2}+1}(2u,2v,u^{2}+v^{2}-1)
\end{align}
$$
Compute $E, F, G$.
$$
\begin{align}
E = \boldsymbol{X}_{u}\cdot \boldsymbol{X}_{u} &= (1-u^{2}+v^{2})^{2}+4u^{2}v^{2}+4u^{2} \\
&=u^{4}+v^{4}+1-2u^{2}-2u^{2}v^{2}+2v^{2}+4u^{2}v^{2}+4u^{2} \\
&=u^{4}+v^{4}+1+2u^{2}+2v^{2}+2u^{2}v^{2} \\
&=(u^{2}+v^{2}+1)^{2} \\
F = \boldsymbol{X}_{u}\cdot \boldsymbol{X}_{v} &= 2uv-2u^{3}v+2uv^{3}+2uv-2uv^{3}+2u^{3}v-4uv \\
&= 0 \\
G = \boldsymbol{X}_{v}\cdot \boldsymbol{X}_{v} &= 4u^{2}v^{2} + (-1+v^{2}-u^{2})^{2}+4v^{2} \\
&= u^{4}+v^{4}+1-2v^{2}-2u^{2}v^{2}+2u^{2}+4v^{2}+4u^{2}v^{2} \\
&=(u^{2}+v^{2}+1)^{2}
\end{align}
$$
Compute $\boldsymbol{X}_{uu}, \boldsymbol{X}_{uv}, \boldsymbol{X}_{vv}$.
$$
\begin{align}
\boldsymbol{X}_{uu} &= (-2u,-2v,2) \\
\boldsymbol{X}_{uv} &= (2v,-2u,0) \\
\boldsymbol{X}_{vv} &= (2u,2v,-2)
\end{align}
$$
Compute $L, M, N$.
$$
\begin{align}
L = \boldsymbol{X}_{uu}\cdot \boldsymbol{U} &= \frac{-4u^{2}-4v^{2}+2u^{2}+2v^{2}-2}{u^{2}+v^{2}+1} \\
&=-2 \\
M = \boldsymbol{X}_{uv}\cdot \boldsymbol{U} &= 0 \\
N = \boldsymbol{X}_{vv}\cdot \boldsymbol{U} &=\frac{-2u^{2}-2v^{2}+2+4u^{2}+4v^{2}}{u^{2}+v^{2}+1} \\
&=2 
\end{align}
$$
Note that mean curvature $H$ is
$$
\mathrm{H} = \frac{GL+EN-2MF}{2(EG-F^{2})}
$$
Since $E = G$ and $L = -N$, $\mathrm{H} = 0$.
___
