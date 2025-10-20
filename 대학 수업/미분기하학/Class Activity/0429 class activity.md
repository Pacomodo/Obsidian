___
Compute the principal curvature of $\boldsymbol{\sigma}(u,v) = (\cos u, \sin u, v)$ for each $(u, v)$ where $0 < u < 2\pi$ and $v$ is any real number.
___
곡면의 principal curvature을 구하기 위해, first fundamental coefficient $E, F, G$를 구해봅시다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (-\sin u, \cos u, 0) \\
\boldsymbol{\sigma}_{v} &= (0, 0, 1) \\
E &= \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u}=1 \\
F &= \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v}=0 \\
G &= \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v}=1 \\
\end{align}
$$
Surface의 Unit normal vector $\boldsymbol{U}$를 구해봅시다.
$$
\boldsymbol{U}=\frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert }=(\cos u, \sin u, 0)
$$
이를 이용해 Second fundamental coefficient $L, M, N$을 구해봅시다.
$$
\begin{align}
L &= \boldsymbol{\sigma}_{uu}\cdot \boldsymbol{U} = (-\cos u,-\sin u, 0)\cdot(\cos u, \sin u, 0) = -1 \\
M &= \boldsymbol{\sigma}_{uv}\cdot \boldsymbol{U} = (0,0,0)\cdot(\cos u, \sin u, 0) =0 \\
N &= \boldsymbol{\sigma}_{vv}\cdot \boldsymbol{U} = (0,0,0)\cdot(\cos u, \sin u, 0)=0
\end{align}
$$
곡면의 principal curvature를 구하기 위해, 다음 행렬의 eigenvalue를 구해봅시다.
$$
\begin{align}
\begin{pmatrix}
E & F \\
F & G
\end{pmatrix}^{-1}
\begin{pmatrix}
L & M \\
M & N
\end{pmatrix}\begin{pmatrix}
x  \\
y
\end{pmatrix} = \lambda \begin{pmatrix}
x \\
y
\end{pmatrix} \\
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}^{-1}
\begin{pmatrix}
-1 & 0 \\
0 & 0
\end{pmatrix}\begin{pmatrix}
x  \\
y
\end{pmatrix} = \lambda \begin{pmatrix}
x \\
y
\end{pmatrix} \\
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
-1 & 0 \\
0 & 0
\end{pmatrix}\begin{pmatrix}
x  \\
y
\end{pmatrix} = \lambda \begin{pmatrix}
x \\
y
\end{pmatrix} \\
\begin{pmatrix}
-1 & 0 \\
0 & 0
\end{pmatrix}\begin{pmatrix}
x  \\
y
\end{pmatrix} = \lambda \begin{pmatrix}
x \\
y
\end{pmatrix}
\end{align}
$$
이때, $\begin{pmatrix}-1&0\\0 &0\end{pmatrix}$은 diagonal matrix이므로, eigenvalue $\lambda$는 $-1, 0$입니다. 그리고 이것이 곡면의 principal curvature입니다.