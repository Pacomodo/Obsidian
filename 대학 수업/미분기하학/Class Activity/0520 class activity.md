___
다음 곡면의 평균곡률 mean curvature가 모든 점에서 $0$임을 보이세요.
$$\boldsymbol{\sigma}(u,v) = (u, v, \ln(\cos u)-\ln(\cos v))$$
___
Sol)
We want to show that the sum of eigenvalues of matrix $$
\mathcal{M}=\begin{pmatrix}
E & F \\
F & G
\end{pmatrix}^{-1}\begin{pmatrix}
L & M \\
M & N
\end{pmatrix}
$$ is $0$. In other words, $\mathrm{Tr}(\mathcal{M}) = 0$.
Note that $\mathrm{Tr}(\mathcal{M}) = \frac{GL+EN-2FM}{EG-F^{2}}$.
Compute $\boldsymbol{\sigma}_{u}, \boldsymbol{\sigma}_{v}, \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}, \boldsymbol{U}$.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (1, 0, -\tan u) \\
\boldsymbol{\sigma}_{v} &= (0, 1, \tan v) \\
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} &= (\tan u, -\tan v, 1) \\
\boldsymbol{U} &= \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert } \\
&=\frac{1}{\sqrt{ \tan ^{2}u+\tan ^{2}v +1}}(\tan u, - \tan v, 1)
\end{align}
$$
Compute $E, F, G$.
$$
\begin{align}
E &= \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u} = 1+\tan ^{2}u = \sec ^{2}u\\
F &= \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v} = -\tan u\tan v \\
G &= \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v} = 1+\tan ^{2}v = \sec ^{2}v
\end{align}
$$
Compute $\boldsymbol{\sigma}_{uu}, \boldsymbol{\sigma}_{uv}, \boldsymbol{\sigma}_{vv}$.
$$
\begin{align}
\boldsymbol{\sigma}_{uu} &= (0, 0, -\sec ^{2}u) \\
\boldsymbol{\sigma}_{uv} &= (0, 0, 0) \\
\boldsymbol{\sigma}_{vv} &= (0, 0, \sec ^{2}v)
\end{align}
$$
Compute $L, M, N$.
$$
\begin{align}
L &= \boldsymbol{\sigma}_{uu}\cdot \boldsymbol{U} = -\frac{\sec ^{2}u}{\sqrt{ \tan ^{2} u + \tan ^{2}v+1 }} \\
M &= \boldsymbol{\sigma}_{uv}\cdot \boldsymbol{U} = 0 \\
N &= \boldsymbol{\sigma}_{vv}\cdot \boldsymbol{U} = \frac{\sec ^{2}v}{\sqrt{ \tan ^{2}u+\tan ^{2}v+1 }}
\end{align}
$$
Compute $GL + EN - 2FM$.
$$
\begin{align}
GL + EN - 2FM &= -\frac{\sec ^{2}u\sec ^{2}v}{\sqrt{ \tan ^{2}u+\tan ^{2}v+1 }}+\frac{\sec ^{2}v\sec ^{2}u}{\sqrt{ \tan ^{2}u+\tan ^{2}v+1 }} \\
&= 0
\end{align}
$$
Therefore, $\text{Mean Curvature} = \frac{\sum\lambda}{2} = \frac{\mathrm{Tr}(M)}{2} = \frac{GL+EN-2FM}{2(EG-F^{2})} = 0$.
___
