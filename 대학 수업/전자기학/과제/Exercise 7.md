___
###### Problem 1

Given $\mathbf{J}=x\mathbf{a}_{x} + y\mathbf{a}_{y}+z\mathbf{a}_{z} [\text{A/m}^{2}]$, find the time rate of decrease of the charge contained within the volume bounded by the cylinders $\rho=1$ and $\rho=2$ and the planes $z=0$ and $z=1$.
___
Sol)
First, change $\mathbf{J}$ into cylidrical coordinates.
$$
\begin{align}
\mathbf{J} &= x\mathbf{a}_{x}+y\mathbf{a}_{y}+z\mathbf{a}_{z} \\
&= \rho \cos \phi \mathbf{a}_{x} + \rho \sin \phi \mathbf{a}_{y}+z\mathbf{a}_{z} \\
&= \rho \cos \phi(\cos \phi \mathbf{a}_{\rho}-\sin \phi \mathbf{a}_{\phi}) + \rho \sin \phi (\sin \phi\mathbf{a}_{\rho}+\cos \phi \mathbf{a}_{\phi})+z\mathbf{a}_{z} \\
&= \rho \mathbf{a}_{\rho}+z\mathbf{a}_{z}
\end{align}
$$
We use the Law of conservation of charge. Let $V$ be the volume bounded by $S$.
$$
\begin{align}
-\frac{d}{dt} \int _{V}\rho_{Q} \, dV &=\oint_{S}\mathbf{J}\cdot d\mathbf{S}  \\
&= \int _{\text{top}} \mathbf{J}\cdot d\mathbf{S} + \int _{\text{bottom}}\mathbf{J} \cdot d\mathbf{S}+\int _{\text{inner}}\mathbf{J}\cdot d\mathbf{S} + \int _{\text{outer}} \mathbf{J}\cdot d\mathbf{S} \\
\end{align}
$$
$$
\begin{align}
\int _{\text{top}} \mathbf{J}\cdot d\mathbf{S} &= \int _{0}^{2\pi} \int_{1}^{2}  \rho \, d\rho  \, d\phi=3\pi \\
\int _{\text{bottom}} \mathbf{J}\cdot d\mathbf{S} &= 0 \\ 
\int _{\text{inner}} \mathbf{J}\cdot d\mathbf{S} &= \int_{0}^{1}\int_{0}^{2\pi}  -\, d\phi  \, dz=-2\pi \\ 
\int _{\text{outer}} \mathbf{J}\cdot d\mathbf{S} &= \int_{0}^{1}\int_{0}^{2\pi}  4\, d\phi  \, dz=8\pi \\
\end{align}
$$
So,
$$
\boxed{ \oint_{S}\mathbf{J}\cdot d\mathbf{S} = 9\pi \text{[A]} }
$$
Or, we can use divergence theorem.
$$
\begin{align}
\oint_{S}\mathbf{J}\cdot d\mathbf{S} = \int _{V}2+1 \, dV =3\int _{V} \, dV=\boxed{ 9\pi [\text{A}] }
\end{align}
$$
___
###### Problem 2

A volume charge density is given in spherical coordinates as $$\rho_{v}=\frac{1}{r^{2}}e^{-t}[\text{C/m}^{3}]$$ Find the outward current crossing the surface of the sphere of which radius is $r$, centered at the origin.
___
Sol)
We want to use the Law of conservation of charge. Let the surface of the sphere given in problem $S$. Let $V$ be the volume bounded by $S$.
$$
\begin{align}
\oint_{S}\mathbf{J}\cdot d\mathbf{S} &= -\frac{d}{dt} \int _{V}\rho_{v} \, dV \\
&= -\frac{d}{dt} e^{-t} \int_{\phi=0}^{\phi=2\pi} \int_{\theta=0}^{\theta=\pi} \int _{r=0}^{r} \sin \theta \, dr  \, d\theta  \, d\phi  \\
&= -\frac{d}{dt}(e^{-t})(4\pi r) \\
&=\boxed{ 4\pi r e^{-t} [\text{A}] }
\end{align}
$$
___
###### Problem 3

Charge is distributed with uniform density $\rho_{0}[\text{C/m}^{3}]$ in the region $a < r < 2a$ in spherical coordinates. Find $\mathbf{D}$ everywhere.
___
Sol)
We will use Gauss law.
For the region $r \leq a$, $\mathbf{D} = 0$.
Note that this situation has spherical symmetry, so, it depends on only $r$, not $\theta$ or $\phi$.
So, $\mathbf{D}$ has only $\mathbf{D}_{r}$ term.
For the region $a < r < 2a$,
$$
\begin{align}
\oint_{S}\mathbf{D}\cdot d\mathbf{S} &= \frac{4\rho_{0}\pi(r^{3}-a^{3})}{3} \\
\int _{\phi=0}^{\phi=2\pi}\int_{\theta=0}^{\theta=\pi} \mathbf{D}_{r} r^{2}\sin \theta\, d\theta  \, d\phi &= 4\pi r^{2}\mathbf{D}_{r}  \\
\mathbf{D} &=\frac{\rho_{0}(r^{3}-a^{3})}{3r^{2}}\mathbf{a}_{r}
\end{align}
$$
For the region $2a \leq r$,
$$
\begin{align}
\oint_{S}\mathbf{D}\cdot d\mathbf{S} &= \frac{28\rho_{0}\pi a^{3}}{3} \\
\int _{\phi=0}^{\phi=2\pi}\int_{\theta=0}^{\theta=\pi} \mathbf{D}_{r} r^{2}\sin \theta\, d\theta  \, d\phi &= 4\pi r^{2}\mathbf{D}_{r}  \\
\mathbf{D} &=\frac{7\rho_{0}a^{3}}{3r^{2}}\mathbf{a}_{r}
\end{align}
$$
___
