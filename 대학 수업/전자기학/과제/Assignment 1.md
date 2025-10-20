##### Problem 1.
Consider the surface given by $$\frac{x^{2}}{3}+\frac{y^{2}}{9}+\frac{z^{2}}{27} = 1\tag{1}$$ and the point $P$ at $(1, \sqrt{ 3 }, 3)$.
___

###### (a) The surface given by $z = 3$ and the one in $(1)$ intersect in the curve $L_{1}$. Find the differential length vector $d\mathbf{l}$ along $L_{1}$ at $P$ in terms of $dx$.
Let (1) is surface $S_{1}$, $z = 3$ is surface $S_{2}$.
Differentiate $S_{1}$.
$$
\tag{2}\frac{2x}{3}dx + \frac{2y}{9}dy + \frac{2z}{27}dz = 0 \\
$$
Differentiate $S_{2}$.
$$
dz = 0
$$
Since $L_{1}$ is defined by the system of equations $S_{1}$ and $S_{2}$, $L_{1}$ must follow both of them.

Note that differential vector $d\mathbf{l}$ in CS is $d\mathbf{l} =dx\mathbf{a}_{x}+dy\mathbf{a}_{y}+dz\mathbf{a}_{z}$, and we want to find $d\mathbf{l}$ along $L_{1}$ at $P = (1, \sqrt{ 3 }, 3)$.
Therefore,
$$
\begin{align}
& d\mathbf{l} = dx\mathbf{a}_{x}+dy\mathbf{a}_{y}+dz\mathbf{a}_{z} \\
\tag{3}\xrightarrow{dz=0} & d\mathbf{l} = dx\mathbf{a}_{x}+dy\mathbf{a}_{y} \\
\end{align}
$$
Summarize $(2)$ in terms of $dx$ using $dz = 0$ and by substitute $P = (1, \sqrt{ 3 }, 3)$ into $(2)$.
$$
\begin{align}
(2) & = \frac{2}{3}dx+\frac{2\sqrt{ 3 }}{9}dy = 0 \\
\rightarrow & 3dx+\sqrt{ 3 }dy = 0 \\
\tag{4} \rightarrow & dy = -\sqrt{ 3 }dx
\end{align}
$$
Substitute $(3)$ using $(4)$.
$$
d\mathbf{l} = dx(\mathbf{a}_{x}-\sqrt{ 3 }\mathbf{a}_{y})
$$
___

###### (b) The surface given by $y = \sqrt{ 3 }$ and the one in $(1)$ intersect in the curve $L_{2}$. Find the differential length vector $d\mathbf{l}$ along $L_{2}$ at $P$ in terms of $dx$.
Let $y=\sqrt{ 3 }$ is surface $S_{3}$.
Differentiate $S_{3}$.
$$
\tag{5}dy = 0
$$
Since $L_{2}$ is defined by the system of equations $S_{1}$ and $S_{3}$, $L_{2}$ must follow both of them.
Summarize $(2)$ in terms of $dx$ using $(5)$ and by substitute $P = (1,\sqrt{ 3 }, 3)$ into $(2)$.
$$
\begin{align}
(2)& = \frac{2}{3}dx + \frac{6}{27}dz = 0 \\
\rightarrow & \frac{1}{3}dx+\frac{1}{9}dz =0 \\
\tag{6} \rightarrow & dz = -3dx
\end{align}
$$
Therefore,
$$
d\mathbf{l} = dx(\mathbf{a}_{x}-3\mathbf{a}_{z})
$$
___

###### (c) Find the unit vector normal to the surface in $(1)$ at $P$.

We need to cross product the result of (a) and (b). Let this $d\mathbf{l}_{a}, d\mathbf{l}_{b}$.
$$
\begin{align}
d\mathbf{l}_{a}\times d\mathbf{l}_{b} &= \begin{vmatrix}
\mathbf{a}_{x} & \mathbf{a}_{y} & \mathbf{a}_{z} \\
dx & -\sqrt{ 3 }dx & 0 \\
dx & 0 & -3dx
\end{vmatrix} \\
&= 3\sqrt{ 3 }(dx)^{2}\mathbf{a}_{x} + 3(dx)^{2}\mathbf{a}_{y}+\sqrt{ 3 }(dx)^{2}\mathbf{a}_{z}
\end{align}
$$
Therefore, $$
\begin{align}
\mathbf{a}_{n} &= \pm \frac{d\mathbf{l}_{a}\times d\mathbf{l}_{b}}{\lvert d\mathbf{l}_{a}\times d\mathbf{l}_{b} \rvert } \\
&= \pm \frac{1}{\sqrt{ 27+9+3 }}(3\sqrt{ 3 }\mathbf{a}_{x} + 3\mathbf{a}_{y}+\sqrt{ 3 }\mathbf{a}_{z}) \\
&= \pm \frac{1}{\sqrt{ 13 }}(3\mathbf{a}_{x}+\sqrt{ 3 }\mathbf{a}_{y}+\mathbf{a}_{z})
\end{align}$$

Or more easily, we can use this facts,
$$
\mathbf{a}_{n} = \pm \frac{\nabla F}{\lVert \nabla F \rVert }
$$
This can be established when surface equation is given as a level surface $S : F(x,y,z) = C$.
$$
\begin{align}
\nabla F &= \left( \frac{ \partial F }{ \partial x }, \frac{ \partial F }{ \partial y }, \frac{ \partial F }{ \partial z }\right) \\
&= \left( \frac{2x}{3}, \frac{2y}{9}, \frac{2z}{27} \right) \\
&= \left( \frac{2}{3}, \frac{2\sqrt{ 3 }}{9}, \frac{2}{9} \right) \\
\rightarrow \mathbf{a}_{n} = \pm \frac{\nabla F}{\lVert \nabla F \rVert }&= \pm \frac{1}{\sqrt{ 13 }}(3, \sqrt{ 3 }, 1)
\end{align}
$$

