##### Problem 1
The current $I$ is directed inward from infinity to the origin along the positive $x$-axis, and then outward from the origin to infinity along the positive $y$-axis. Find the magnetic flux density at $(1,\sqrt{ 3 },0)$.
![[Pasted image 20241016124926.png|center]]
___
Sol)
Let $\mathbf{B}_{x}, \mathbf{B}_{y}$ be the magnetic flux density due to current $I$ on $x$-axis and $y$-axis.
We want to compute $\mathbf{B} = \mathbf{B}_{x}+\mathbf{B}_{y}$.
First, we want to compute $\mathbf{B}_{x}$.
Consider point $P(x, 0, 0)$ on $x$-axis. Differential magnetic flux density $d\mathbf{B}_{x}$ at $(1, \sqrt{ 3 }, 0)$ defined as
$$
d\mathbf{B}_{x} = \frac{\mu_{0}}{4\pi} \frac{Id\mathbf{l}\times \mathbf{a}_{R}}{R^{2}}
$$
where $R$ is distance between $P$ and $(1, \sqrt{ 3 }, 0)$, and $\mathbf{a}_{R}$ is a unit vector directs from $P$ to $(1, \sqrt{ 3 }, 0)$.
Note that $d\mathbf{l}$ of the current is $-dx\mathbf{a}_{x}$. Also, $R^{2} = (x-1)^{2}+3$ and $\mathbf{a}_{R} = \frac{(1-x)\mathbf{a}_{x}+ \sqrt{ 3 }\mathbf{a}_{y}}{\sqrt{ (x-1)^{2}+3 }}$.
So,
$$
\begin{align}
d\mathbf{B}_{x} &= \frac{\mu_{0}}{4\pi}\cdot \frac{1}{(x-1)^{2}+3}\cdot \left[ -Idx\mathbf{a}_{x}\times\left( \frac{1}{\sqrt{ (x-1)^{2}+3 }} \right)((1-x)\mathbf{a}_{x}+\sqrt{ 3 }\mathbf{a}_{y}) \right] \\
&=\frac{\mu_{0}}{4\pi}\cdot -\frac{I\sqrt{ 3 }dx}{(x^{2}-2x+4)^{3/2}}\mathbf{a}_{z}
\end{align}
$$
So,
$$
\begin{align}
\mathbf{B}_{x} &= \int _{0}^{\infty}d\mathbf{B}_{x} \\
&=-\frac{\sqrt{ 3 }\mu_{0}I}{4\pi}\int _{0}^{\infty} \frac{1}{(x^{2}-2x+4)^{3/2}} \, dx \mathbf{a}_{z} \\
\text{Let }u=x-1\rightarrow&= -\frac{\sqrt{ 3 }\mu_{0}I}{4\pi}\underbrace{ \int _{-1}^{\infty} \frac{1}{(u^{2}+3)^{3/2}} \, du }_{ J } \mathbf{a}_{z} \\
\end{align}
$$
We want to compute inner integral. Since $1 / (u^{2}+3)^{3/2}$ is even function,
$$
J = \int _{0}^{1} \frac{1}{(u^{2}+3)^{3/2}} \, du + \int _{0}^{\infty} \frac{1}{(u^{2}+3)^{3/2}} \, du
$$
Let $u = \sqrt{ 3 }\tan t\rightarrow du=\sqrt{ 3 }\sec ^{2}tdt$. Then, $u^{2}+3\rightarrow 3(1+\tan ^{2}t)\rightarrow 3\sec ^{2}t$. So,
$$
\begin{align}
J &= \int _{0}^{\pi/6} \frac{1}{3\sqrt{ 3 }\sec ^{3}t} \sqrt{ 3 }\sec ^{2}t \, dt + \int _{0}^{\pi/2} \frac{1}{3\sqrt{ 3 }\sec ^{3}t} \sqrt{ 3 }\sec ^{2}t \, dt \\
&=\frac{1}{3}\left( \int _{0}^{\pi/6}\cos t \, dt+ \int _{0}^{\pi/2} \cos t \, dt  \right) \\
&=\frac{1}{3}\left( \frac{1}{2}+1 \right)=\frac{1}{2} 
\end{align}
$$
So,
$$
\mathbf{B}_{x} = -\frac{\mu_{0}I}{4\pi}\cdot \frac{\sqrt{ 3 }}{2}\mathbf{a}_{z}
$$

Second, we want to compute $\mathbf{B}_{y}$.
Consider point $P(0, y, 0)$ on $y$-axis. Differential magnetic flux density $d\mathbf{B}_{y}$ at $(1, \sqrt{ 3 }, 0)$ defined as
$$
d\mathbf{B}_{y} = \frac{\mu_{0}}{4\pi} \frac{Id\mathbf{l}\times \mathbf{a}_{R}}{R^{2}}
$$
where $R$ is distance between $P$ and $(1, \sqrt{ 3 }, 0)$, and $\mathbf{a}_{R}$ is a unit vector directs from $P$ to $(1, \sqrt{ 3 }, 0)$.
Note that $d\mathbf{l}$ of the current is $dy\mathbf{a}_{y}$. Also, $R^{2} = (y-\sqrt{ 3 })^{2}+1$ and $\mathbf{a}_{R} = \frac{\mathbf{a}_{x}+ (\sqrt{ 3 }-y)\mathbf{a}_{y}}{\sqrt{ (y-\sqrt{ 3 })^{2}+1 }}$.
So,
$$
\begin{align}
d\mathbf{B}_{y} &= \frac{\mu_{0}}{4\pi}\cdot \frac{1}{(y-\sqrt{ 3 })^{2}+1}\cdot \left[ Idy\mathbf{a}_{y}\times\left( \frac{1}{\sqrt{ (y-\sqrt{ 3 })^{2}+1 }} \right)(\mathbf{a}_{x}+(\sqrt{ 3 }-y)\mathbf{a}_{y}) \right] \\
&=\frac{\mu_{0}}{4\pi}\cdot -\frac{Idy}{((y-\sqrt{ 3 })^{2}+1)^{3/2}}\mathbf{a}_{z}
\end{align}
$$
So,
$$
\begin{align}
\mathbf{B}_{y} &= \int _{0}^{\infty}d\mathbf{B}_{y} \\
&= -\frac{\mu_{0}I}{4\pi} \underbrace{ \int _{0}^{\infty} \frac{1}{((y-\sqrt{ 3 })^{2}+1)^{3/2}}\, dy   }_{ K } \mathbf{a}_{z}
\end{align}
$$
We want to compute inner integral $K$.
Let $u=y - \sqrt{ 3 }$.
$$
K = \int _{-\sqrt{ 3 }}^{\infty} \frac{1}{(u^{2}+1)^{3/2}}\, du=\int _{0}^{\sqrt{ 3 }} \frac{1}{(u^{2}+1)^{3/2}}\, du + \int _{0}^{\infty} \frac{1}{(u^{2}+1)^{3/2}}\, du
$$
Let $u = \tan t$.
$$
K = \int _{0}^{\pi/3}\cos t \, dt + \int _{0}^{\pi/2}\cos t \, dt =\frac{\sqrt{ 3 }}{2}+1
$$
So,
$$
\mathbf{B}_{y} = -\frac{\mu_{0}I}{4\pi}\left( \frac{\sqrt{ 3 }}{2} +1\right)\mathbf{a}_{z}
$$
Therefore,
$$
\mathbf{B} = -\frac{\mu_{0}(\sqrt{ 3 }+1)I}{4\pi}\mathbf{a}_{z}
$$
___
