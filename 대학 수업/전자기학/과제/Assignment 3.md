##### Problem 1.
Find $\mathbf{E}$ on the $z$ axis produced by an annular ring of uniform surface charge density $\rho_{S_{0}}$ in free space. The ring occupies the region $a\leq \rho \leq b$, $0\leq \phi \leq 2\pi$ and $z=0$ in cylindrical coordinates.
___
Sol)
![[Pasted image 20241016120151.png]]
Consider $P = (0, 0, z')$ in cylindrical coordinates and point in annual ring $D = (\rho', \phi', 0)$ be given.
We want to compute $\mathbf{E}$ by treating total charge of differential surface of $D$ as a point charge.
Since differential area of $D$ is $\rho'd\rho'd\phi'$ and surface charge density is $\rho_{S_{0}}$, $Q = \rho_{S_{0}}\rho'd\rho'd\phi'$.
Differential electric field $d\mathbf{E}$ is
$$
d\mathbf{E} = \frac{Q}{4\pi \varepsilon_{0}R^{2}}\mathbf{a}_{R} = \frac{\rho_{S_{0}}\rho'd\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z'^{2})}\mathbf{a}_{R}
$$
Note that $\mathbf{a}_{R}$ is a unit vector directs from $D$ to $P$.
So,
$$
\frac{\rho_{S_{0}}\rho'd\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z'^{2})}\mathbf{a}_{R} = \frac{\rho_{S_{0}}\rho'd\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z'^{2})} \frac{-\rho' \mathbf{a}_{\rho}+z'\mathbf{a}_{z}}{\sqrt{ \rho'^{2}+z'^{2} }}
$$
Then, we can compute $\mathbf{E}$ by integrating $d\mathbf{E}$.
$$
\begin{align}
\mathbf{E} &= \iint d\mathbf{E} \\
&= \int _{0}^{2\pi} \int _{a}^{b} \frac{\rho_{S_{0}}\rho'd\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z'^{2})} \frac{-\rho' \mathbf{a}_{\rho}+z'\mathbf{a}_{z}}{\sqrt{ \rho'^{2}+z'^{2} }} \\
&= \frac{\rho_{S_{0}}}{4\pi\varepsilon_{0}}\int _{0}^{2\pi} \int _{a}^{b} \frac{\rho'}{(\rho'^{2}+z'^{2})^{3/2}} (-\rho' \mathbf{a}_{\rho}+z'\mathbf{a}_{z})d\rho'd\phi' \\
&=\frac{\rho_{S_{0}}}{4\pi\varepsilon_{0}}\int _{0}^{2\pi} \int _{a}^{b} \frac{-\rho'^{2}}{(\rho'^{2}+z'^{2})^{3/2}}\mathbf{a}_{\rho}+\frac{\rho'z'}{(\rho'^{2}+z'^{2})^{3/2}}\mathbf{a}_{z}d\rho'd\phi'
\end{align}
$$
Note that $\mathbf{a}_{\rho}$ term is different by angle $\phi$, and we integrate for all angle, $\mathbf{a}_{\rho}$ term will be cancel out. This is not applied for $\mathbf{a}_{z}$ since $\mathbf{a}_{z}$ is uniform.
$$
\begin{align}
&=\frac{\rho_{S_{0}}}{4\pi\varepsilon_{0}} \int _{0}^{2\pi} \int _{a}^{b} \frac{\rho'z'}{(\rho'^{2}+z'^{2})^{3/2}}\mathbf{a}_{z}d\rho'd\phi' \\
&=\frac{\rho_{S_{0}}z'}{2\varepsilon_{0}}\int _{a}^{b} \frac{\rho'}{(\rho'^{2}+z'^{2})^{3/2}} \, d\rho'\mathbf{a}_{z} \\
&=\frac{\rho_{S_{0}}z'}{2\varepsilon_{0}}\left[ -\frac{1}{(\rho'^{2}+z'^{2})^{1/2}} \right]_{a}^{b} \mathbf{a}_{z}\\
\therefore \mathbf{E}&= \frac{\rho_{S_{0}}z'}{2\varepsilon_{0}}\left[ \frac{1}{\sqrt{ z'^{2}+a^{2} }} - \frac{1}{\sqrt{ z'^{2}+b^{2} }} \right]\mathbf{a}_{z}
\end{align}
$$
___
