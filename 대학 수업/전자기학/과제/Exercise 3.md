___
###### Problem 1

Point charges of 1C and -2C are located at $(0, 0, 0)$ and $(1,1,1)$, respectively, in free space. Find the electrostatic force acting on each charge.
___
Sol)
Let point charge of 1C be $Q_{1}$ and point charge of -2C be $Q_{2}$. Then, the unit vector $\mathbf{a}_{12}$ that directs from $Q_{1}$ to $Q_{2}$, and the unit vector $\mathbf{a}_{21}$ that directs from $Q_{2}$ to $Q_{1}$ are
$$
\begin{align}
\mathbf{a}_{12} &= \frac{1}{\sqrt{ 3 }}(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z}) \\
\mathbf{a}_{21} &= -\frac{1}{\sqrt{ 3 }}(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z})
\end{align}
$$
So, the electrostatic force $\mathbf{F}_{1}$ acting on $Q_{1}$ is
$$
\mathbf{F}_{1} = \frac{1}{6\sqrt{ 3 }\pi\varepsilon_{0}}(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z})[\text{N}]
$$
Electrostatic force $\mathbf{F}_{2}$ acting on $Q_{2}$ is
$$
\mathbf{F}_{2} = -\frac{1}{6\sqrt{ 3 }\pi\varepsilon_{0}}(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z})[\text{N}]
$$
___
###### Problem 2

A uniform line charge of $\rho_{L_{0}}[\text{C/m}]$ is located along the line defined by $x=6$ and $y=8$. Find $\mathbf{E}$ at a point $P(x, y, z)$.
___
Sol)
Move this line charge into $z$-axis. Then, it is same problem that find $\mathbf{E}$ at a point $P(x-6, y-8, z)=P'(x', y',z)=P'(\rho, \phi, z)$.
We know that $\mathbf{E}$ due to infinitely long line charge.
$$
\mathbf{E} = \frac{\rho_{L_{0}}}{2\pi\varepsilon_{0}\rho}\mathbf{a}_{\rho}
$$
where
$$
\begin{align}
\rho &= \sqrt{ x'^{2}+y'^{2} } \\
&= \sqrt{ (x-6)^{2}+(y-8)^{2} } \\
\mathbf{a}_{\rho} &= \cos \phi\mathbf{a}_{x'}+\sin \phi\mathbf{a}_{y'} \\
&=\frac{x-6}{\sqrt{ (x-6)^{2}+(y-8)^{2} }}\mathbf{a}_{x}+\frac{y-8}{\sqrt{ (x-6)^{2}+(y-8)^{2} }}\mathbf{a}_{y}
\end{align}
$$
So,
$$
\mathbf{E} = \frac{\rho_{L_{0}}}{2\pi\varepsilon_{0}} \frac{1}{(x-6)^{2}+(y-8)^{2}}[(x-6)\mathbf{a}_{x}+(y-8)\mathbf{a}_{y}] [\text{V/m}]
$$
___
###### Problem 3

A uniform line charge of $\rho_{L_{0}}[\text{C/m}]$ is located along the line defined by $y=-2$ and $z=5$. Find $\mathbf{E}$ at a point on the $z=0$ plane.
___
Sol)
$$
\mathbf{E} = \frac{\rho_{L_{0}}}{2\pi \varepsilon_{0}} \frac{1}{(y+2)^{2}+25}[(y+2)\mathbf{a}_{y}-25\mathbf{a}_{z}] [\text{V/m}]
$$
___
###### Problem 4

A radially dependent surface charge is distributed on an infinite flat sheet in the $xy$ plane and is characterized in cylindrical coordinates by surface density $\rho_{s} = \rho_{0}/\rho[\text{C/m}^{2}]$, where $\rho_{0}$ is a constant. Find $\mathbf{E}$ everywhere on the $z$ axis.   

Hint) 
1) Find the charge on a differential surface at $(\rho', \phi', 0)$. This charge can be considered as a point charge. 
2) Use Coulomb’s law to find $d\mathbf{E}$ due to the point charge. 
3) Integrate $d\mathbf{E}$ with respect to $\rho'$ and $\phi'$. 
4) Prove and use $$\int _{0}^{2\pi}\mathbf{a}_{\rho} \, d\phi = 0$$if necessary.
6) Use $$\int \frac{1}{(a^{2}+x^{2})^{3/2}} \, dx =\frac{x}{a^{2}\sqrt{ a^{2}+x^{2} }}$$ if necessary.
___
Sol)
Let observation point $P = (0, 0, z)$. Differential surface at $(\rho', \phi', 0)$ is $\rho' d\rho'd\phi'$.
So,
$$
d\mathbf{E} = \frac{\rho_{0}d\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z^{2})^{3/2}}(z\mathbf{a}_{z}-\rho'\mathbf{a}_{\rho'})
$$
So, integrate $d\mathbf{E}$ with $\rho'$ and $\phi'$.
$$
\begin{align}
\mathbf{E} &= \int _{0}^{2\pi}\int _{0}^{\infty} \frac{\rho_{0}d\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z^{2})^{3/2}}(z\mathbf{a}_{z}-\rho'\mathbf{a}_{\rho'}) \\
&= \int _{0}^{2\pi}\int _{0}^{\infty} \frac{\rho_{0}zd\rho'd\phi'}{4\pi \varepsilon_{0}(\rho'^{2}+z^{2})^{3/2}}\mathbf{a}_{z} \\
&=\frac{\rho_{0}z}{4\pi \varepsilon_{0}}\int _{0}^{2\pi}\int _{0}^{\infty} \frac{1}{(\rho'^{2}+z^{2})^{3/2}}d\rho'd\phi'\mathbf{a}_{z} \\
&= \frac{\rho_{0}z}{2\varepsilon_{0}}\int _{0}^{\infty} \frac{1}{(\rho'^{2}+z^{2})^{3/2}}d\rho'\mathbf{a}_{z} \\
&= \frac{\rho_{0}z}{2\varepsilon_{0}}\left[\frac{\rho'}{z^{2}\sqrt{ z^{2}+\rho'^{2} }}\right]_{0}^{\infty}\mathbf{a}_{z} \\
&=\frac{\rho_{0}}{2\varepsilon_{0}z}\mathbf{a}_{z} \\
&=\boxed{ \frac{\rho_{0}}{2\varepsilon_{0}z}\mathbf{a}_{z} [\text{V/m}]}
\end{align}
$$