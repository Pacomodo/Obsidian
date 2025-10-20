___
###### Problem 1
The magnetic field in free space is given by $$\mathbf{H}(x,t) = 10\cos(10^{8}t-\beta x)\mathbf{a}_{y}[\text{A/m}]$$ Find
(a) $\beta$
(b) $\lambda$
(c) $\mathbf{E}$
___
Sol)
Note that $\omega = 10^{8}, v_{p} = 3\times 10^{8}$ in free space, so, $\beta = 1 / 3$.
$f = 10^{8} / 2\pi$, so, $\lambda = 6\pi$.
Wave goes to $+x$ direction. So,
$\mathbf{E} = -10\eta_{0}\cos\left( 10^{8}t - \frac{1}{3}x \right)\mathbf{a}_{z} \approx - 3770\cos\left( 10^{8}t-\frac{1}{3}x \right)\mathbf{a}_{z}$.
$$
\begin{align}
\beta &= \boxed{ \frac{1}{3} } \\
\lambda &= \boxed{ 6\pi  }\\
\mathbf{E} &= \boxed{ -3770\cos\left( 10^{8}t-\frac{1}{3}x \right)\mathbf{a}_{z} }
\end{align}
$$
___
###### Problem 2
The electric field in free space is given by $$\mathbf{E}(x,y,z,t) = (10\mathbf{a}_{y} + 5\mathbf{a}_{z})\cos(\omega t + 2y-4z)\text{[V/m]}$$ Find $\mathbf{H}$.
___
Sol)
Note that $\mathbf{a}_{E}, \mathbf{a}_{H}, \mathbf{a}_{S}$ follows right-hand rule, where $\mathbf{a}_{E}, \mathbf{a}_{H}, \mathbf{a}_{S}$ are unit vector of $\mathbf{E}, \mathbf{H}, \mathbf{S}$.($\mathbf{S}$ is Poynting vector where its direction is direction of propagation.)
$$
\begin{align}
\mathbf{E}(x,y,z,t) &= (10\mathbf{a}_{y} + 5\mathbf{a}_{z})\cos(\omega t + 2y-4z) \\
&= 5\sqrt{ 5 } \frac{\left( 2\mathbf{a}_{y}+\mathbf{a}_{z} \right)}{\sqrt{ 5 }}\cos(\omega t -(-2y+4z)) \\
&=5\sqrt{ 5 }\mathbf{a}_{E}\cos(\omega t - (-2y+4z))
\end{align}
$$
We set $(2\mathbf{a}_{y}+\mathbf{a}_{z}) / \sqrt{ 5 }$ as $\mathbf{a}_{E}$. Also, the direction of propagation is $-2\mathbf{a}_{y} + 4\mathbf{a}_{z}$, so, $\mathbf{a}_{S} = (-\mathbf{a}_{y}+2\mathbf{a}_{z}) / \sqrt{ 5 }$.
Therefore, $\mathbf{a}_{H} = \mathbf{a}_{S}\times \mathbf{a}_{E}$, $\mathbf{a}_{H} = -\mathbf{a}_{x}$.
Hence,
$$
\begin{align}
\mathbf{H}(x,y,z,t) &= \frac{5\sqrt{ 5 }}{\eta_{0}}\mathbf{a}_{H}\cos(\omega t+2y-4z) \\
&= \boxed{ -\frac{5\sqrt{ 5 }}{\eta_{0}}\cos(\omega t+2y-4z)\mathbf{a}_{x} }
\end{align}
$$
___

