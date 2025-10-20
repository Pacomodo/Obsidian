##### Problem 1.

Express $\mathbf{D} = \rho(z^{2}+1)\mathbf{a}_{\rho}-\rho z\cos \phi \mathbf{a}_{\phi}$ in rectangular coordinates at $x=3, y=4, z=1$.
___
Sol)
Note that the conversion between cartesian coordinates and cylindrical coordinates.
$$
\begin{align}
P(x,y,z)&\rightarrow P\left( \sqrt{ x^{2}+y^{2} }, \tan ^{-1}\left( \frac{y}{x} \right), z \right) \\
P(\rho, \phi, z) &\rightarrow P(\rho \cos \phi, \rho \sin \phi, z) \\
\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix} &= \begin{bmatrix}
\cos \phi & -\sin \phi & 0 \\
\sin \phi & \cos \phi & 0 \\
0 & 0 & 1
\end{bmatrix} \begin{bmatrix}
\mathbf{a}_{\rho} \\
\mathbf{a}_{\phi} \\
\mathbf{a}_{z}
\end{bmatrix} \\
\begin{bmatrix}
\mathbf{a}_{\rho} \\
\mathbf{a}_{\phi} \\
\mathbf{a}_{z}
\end{bmatrix} &= \begin{bmatrix}
\cos \phi & \sin \phi & 0 \\
-\sin \phi & \cos \phi & 0 \\
0 & 0 & 1
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}
\end{align}
$$
Since $x=3, y=4$, $\rho = 5$. Also, $\cos \phi = \frac{3}{5}, \sin \phi = \frac{4}{5}$.
Hence,
$$
\begin{align}
\mathbf{D} &= \rho(z^{2}+1)\mathbf{a}_{\rho}-\rho z\cos \phi \mathbf{a}_{\phi} \\
&=10\left( \frac{3}{5}\mathbf{a}_{x}+\frac{4}{5}\mathbf{a}_{y} \right)-5\cdot 1\cdot \frac{3}{5}\left( -\frac{4}{5}\mathbf{a}_{x} + \frac{3}{5}\mathbf{a}_{y} \right) \\
&= 6\mathbf{a}_{x}+8\mathbf{a}_{y}+\frac{12}{5}\mathbf{a}_{x}-\frac{9}{5}\mathbf{a}_{y} \\
&=\frac{42}{5}\mathbf{a}_{x}+\frac{31}{5}\mathbf{a}_{y}
\end{align}
$$
___
##### Problem 2

$\mathbf{B}$ is given below is at $(-3, 4, 0)$. Find $\mathbf{A}\cdot \mathbf{B}$ when $\mathbf{A} = \mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z}$.
$$
\mathbf{B} = \frac{10}{r}\mathbf{a}_{r}+r\cos \theta \mathbf{a}_{\theta}+\mathbf{a}_{\phi}
$$
___
Sol)
We want to express $\mathbf{B}$ into cartesian coordinates.
Note that the conversion between cartesian coordinates and spherical coordinates.
$$
\begin{align}
P(x, y, z)&\rightarrow P\left( \sqrt{ x^{2}+y^{2}+z^{2} }, \tan ^{-1}\left( \frac{\sqrt{ x^{2}+y^{2} }}{z} \right), \tan ^{-1}\left( \frac{y}{x} \right) \right) \\
P(r, \theta, \phi)&\rightarrow P(r\sin \theta \cos \phi, r\sin \theta \sin \phi, r\cos \theta)
\end{align}
$$
Since $x=-3, y=4, z=0\rightarrow$ $r = 5, \theta=\frac{\pi}{2}, \phi=\tan ^{-1}\left( -\frac{4}{3} \right)+\pi$. Note that I take $\left( -\frac{\pi}{2}, \frac{\pi}{2} \right)$ as image of $\tan ^{-1}$ function.
Note that the conversion between cartesian coordinates and spherical coordinates.
$$
\begin{align}
\begin{bmatrix}
\mathbf{a}_{r} \\
\mathbf{a}_{\theta} \\
\mathbf{a}_{\phi}
\end{bmatrix} &= \begin{bmatrix}
\sin \theta\cos \phi & \sin \theta\sin \phi & \cos \theta \\
\cos \theta \cos \phi & \cos \theta \sin \phi & -\sin \theta \\
-\sin \phi & \cos \phi & 0
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}
\end{align}
$$
Since $\theta = \frac{\pi}{2}\rightarrow \sin \theta = 1, \cos \theta=0$. Since $r=5 \rightarrow \sin \phi=\frac{4}{5}, \cos \phi=-\frac{3}{5}$.
So,
$$
\begin{align}
\begin{bmatrix}
\mathbf{a}_{r} \\
\mathbf{a}_{\theta} \\
\mathbf{a}_{\phi}
\end{bmatrix} &= \begin{bmatrix}
-\frac{3}{5} & \frac{4}{5} & 0 \\
0 & 0 & -1 \\
-\frac{4}{5} & -\frac{3}{5} & 0
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}
\end{align}
$$
$$
\begin{align}
\mathbf{B} &= \frac{10}{r}\mathbf{a}_{r}+r\cos \theta \mathbf{a}_{\theta}+\mathbf{a}_{\phi} \\
&=\frac{10}{5}\left( -\frac{3}{5}\mathbf{a}_{x}+\frac{4}{5}\mathbf{a}_{y} \right)+\left( -\frac{4}{5}\mathbf{a}_{x} -\frac{3}{5}\mathbf{a}_{y} \right) \\
&=-2\mathbf{a}_{x}+\mathbf{a}_{y}
\end{align}
$$
So, $\mathbf{A}\cdot \mathbf{B} = 1\cdot-2 +1\cdot 1+ 1 \cdot 0 = -1$.
___