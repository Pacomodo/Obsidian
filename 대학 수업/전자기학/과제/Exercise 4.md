___
###### Problem 1

For the current element $Idx(\mathbf{a}_{x}+\mathbf{a}_{y})$ situated at the point $(1, -2, 2)$, find the magnetic flux density at $(2, -1, 3)$.
___
Sol)
$R^{2} = 1+1+1=3$.
$$\mathbf{a}_{R} = \frac{1}{\sqrt{ 3 }}(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z})$$
$$
\begin{align}
\mathbf{B} &= \frac{\mu_{0}}{12\sqrt{ 3 }\pi} Idx(\mathbf{a}_{x}+\mathbf{a}_{y})\times (\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z}) \\
&=\frac{I\mu_{0}dx}{12\sqrt{3}\pi}(\mathbf{a}_{z}-\mathbf{a}_{y}-\mathbf{a}_{z}+\mathbf{a}_{x}) \\
&=\boxed{ \frac{\mu_{0}Idx}{12\sqrt{ 3 }\pi}(\mathbf{a}_{x}-\mathbf{a}_{y}) }
\end{align}
$$
___
###### Problem 2

For the current $I$ on the $z$-axis directed in the positive $z$-direction from $z = z_{1}$ to $z=z_{2}$, find the magnetic flux density at a point on the $xy$-plane.
___
Sol)
Let the observation point be $P(\rho, \phi, 0)$.
$$
\begin{align}
d\mathbf{B} &= \frac{\mu_{0}}{4\pi} \frac{Idz\mathbf{a}_{z}\times(\rho\mathbf{a}_{\rho}-z\mathbf{a}_{z})}{(\rho^{2}+z^{2})^{3/2}} \\
&=\frac{Idz\mu_{0}\rho}{4\pi(\rho^{2}+z^{2})^{3/2}}\mathbf{a}_{\phi}
\end{align}
$$
Integrate $d\mathbf{B}$ from $z=z_{1}$ to $z=z_{2}$.
$$
\begin{align}
\mathbf{B} &= \int d\mathbf{B} \\
&= \left( \int_{z=z_{1}}^{z=z_{2}} \frac{I\mu_{0}\rho}{4\pi(\rho^{2}+z^{2})^{3/2}}\, dz \right)\mathbf{a}_{\phi} \\
&=\frac{I\mu_{0}\rho}{4\pi}\left[ \frac{z}{\rho^{2}\sqrt{ \rho^{2} +z^{2}}} \right]^{z=z_{2}}_{z=z_{1}}\mathbf{a}_{\phi} \\
&=\boxed{ \frac{I\mu_{0} \rho}{4\pi}\left( \frac{z_{2}}{\rho^{2}\sqrt{ \rho^{2}+z_{2}^{2} }} -\frac{z_{1}}{\rho^{2}\sqrt{ \rho^{2}+z_{1}^{2} }} \right)\mathbf{a}_{\phi} }
\end{align}
$$
___
###### Problem 3

A circular loop of radius $a$ is situated in the $xy$-plane with its center at the origin. It carries a current $I$ following in the positive $\phi$-direction. Find $\mathbf{B}$ due to the current loop at a point on the $z$-axis.
___
Sol)
Let the observation point be $P(0, 0, z)$. Consider current element at a point $P'(a, \phi, 0)$.
Current element at that point is $Iad\phi\mathbf{a}_{\phi}$.
So, $d\mathbf{B}$ is
$$
\begin{align}
d\mathbf{B} &= \frac{\mu_{0}}{4\pi} \frac{Iad\phi\mathbf{a}_{\phi}\times(-a\mathbf{a}_{\rho}+z\mathbf{a}_{z})}{(a^{2}+z^{2})^{3/2}} \\
&=\frac{Ia\mu_{0}d\phi}{4\pi} \frac{a\mathbf{a}_{z}+z\mathbf{a}_{\rho}}{(a^{2}+z^{2})^{3/2}}
\end{align}
$$
We want to integrate $d\mathbf{B}$ for all $\phi$. Note that if we integrate $\mathbf{a}_{\rho}$ for all $\phi$, it will be $0$.
$$
\begin{align}
\mathbf{B} &= \int d\mathbf{B} \\
&= \int _{\phi=0}^{\phi=2\pi} \frac{Ia^{2}\mu_{0}}{4\pi} \frac{1}{(a^{2}+z^{2})^{3/2}} \, d\phi \mathbf{a}_{z}  \\
&=\boxed{ \frac{Ia^{2}\mu_{0}}{2(a^{2}+z^{2})^{3/2}}\mathbf{a}_{z} }
\end{align}
$$
___

