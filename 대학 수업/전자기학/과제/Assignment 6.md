##### Problem 1
Given the field $\mathbf{H} = 20\rho^{2}\mathbf{a}_{\phi}[\text{A/m}]$ in cylindrical coordinates.
(a) Determine the current density $\mathbf{J}$.
(b) Integrate $\mathbf{J}$ over the circular surface $\rho \leq 1, 0 \leq \phi \leq 2\pi$ and $z = 0$, to determine the total current passing through that surface in the $\mathbf{a}_{z}$ direction.
(c) Find the total current once more, this time by a line integral around the circular path $\rho = 1, 0 \leq \phi \leq 2\pi, z=0$.
___
Sol)
(a)
Use Ampere's law. Note that $\mathbf{H}$ is static field.
$$
\nabla \times \mathbf{H} = \mathbf{J}
$$
So,
$$
\begin{align}
\mathbf{J} &= \begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho } & \frac{ \partial  }{ \partial \phi } & \frac{ \partial  }{ \partial z } \\
H_{\rho} & \rho H_{\phi} & H_{z}
\end{vmatrix} \\
&= \begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho } & \frac{ \partial  }{ \partial \phi } & \frac{ \partial  }{ \partial z } \\
0 & 20 \rho^{3} & 0
\end{vmatrix} \\
&=\boxed{ 60\rho \mathbf{a}_{z} [\text{A/m}^{2}]}
\end{align}
$$

(b)
$$
\begin{align}
[I]_{\text{total}} = \int _{\phi = 0}^{2\pi} \int _{\rho=0}^{1} 60\rho^{2}\, d\rho  \, d\phi= \boxed{ 40\pi \text{[A]}}
\end{align}
$$
(c)
$$
\begin{align}\oint_{C} \mathbf{H}\cdot d\mathbf{l} &= \int _{0}^{2\pi} 20\rho^{3}\, d\phi \\
\xrightarrow{\rho = 1}&= \boxed{ 40\pi \text{[A]}}
\end{align}
$$
___
##### Problem 2
A box is defined by $0 \leq x \leq 1, 0 \leq y \leq 2, 0\leq z\leq 3$. Evaluate the both sides of the divergence theorem for the field given by $\mathbf{D}=2xy\mathbf{a}_{x}+x^{2}\mathbf{a}_{y}[\text{C/m}^{2}]$.
___
Sol)
Divergence theorem says that
$$
\oint_{S}\mathbf{D} \cdot d\mathbf{S} = \iiint_{V} \nabla \cdot \mathbf{D}dV
$$
First, right term is
$$
\begin{align}
\iiint_{V} \nabla \cdot \mathbf{D}dV &= \int _{0}^{3}\int _{0}^{2} \int _{0}^{1} 2y\, dx \, dy  \, dz \\
&=3\cdot 1\cdot 4 = \boxed{ 12 [\text{C}]}
\end{align}
$$
Second, left term is
$$
\begin{align}
\oint_{S}\mathbf{D} \cdot d\mathbf{S} &= \cancelto{ 0 }{ \int _{\text{top}} \mathbf{D}\cdot d\mathbf{S} } + \cancelto{ 0 }{ \int _{\text{bottom}} \mathbf{D}\cdot d\mathbf{S} } + \int _{\text{front}} \mathbf{D}\cdot d\mathbf{S} \\
&+\cancelto{ 0 }{ \int _{\text{back}} \mathbf{D}\cdot d\mathbf{S} } + \int _{\text{left}} \mathbf{D}\cdot d\mathbf{S}  + \int _{\text{right}} \mathbf{D}\cdot d\mathbf{S} \\
&= \int _{0}^{3}\int _{0}^{2} 2y \, dy  \, dz -\int _{0}^{1}\int _{0}^{3} x^{2}\, dz \, dx + \int _{0}^{1}\int _{0}^{3} x^{2}\, dz \, dx \\
&=\boxed{ 12\text{[C]}}
\end{align}
$$
___