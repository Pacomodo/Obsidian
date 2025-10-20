___
###### Problem 1
Find the curl of $\mathbf{A}$ and $\mathbf{B}$.
$$
\mathbf{A} = \frac{e^{-\rho^{2}}}{\rho}\mathbf{a}_{\phi} \ \ \ \ \ \mathbf{B} = 2r\cos \theta \mathbf{a}_{r}+r\mathbf{a}_{\theta}
$$
___
Sol)
Note that the curl is computed in cylindrical coordinate as 
$$
\nabla \times \mathbf{E} = \begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho }  & \frac{ \partial  }{ \partial \phi }  & \frac{ \partial  }{ \partial z }  \\
E_{\rho} & \rho E_{\phi} & E_{z}
\end{vmatrix}
$$
and in spherical coordinate as
$$
\nabla \times \mathbf{E} = \begin{vmatrix}
\frac{\mathbf{a}_{r}}{r^{2}\sin \theta} & \frac{\mathbf{a}_{\theta}}{r\sin \theta} & \frac{\mathbf{a}_{\phi}}{r} \\
\frac{ \partial  }{ \partial r }  & \frac{ \partial  }{ \partial \theta }  & \frac{ \partial  }{ \partial \phi }  \\
E_{r} & rE_{\theta} & r\sin \theta E_{\phi}
\end{vmatrix}
$$

So,
$$
\begin{align}
\nabla \times\mathbf{A} &= \begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho }  & \frac{ \partial  }{ \partial \phi }  & \frac{ \partial  }{ \partial z }  \\
0 & e^{-\rho^{2}} & 0
\end{vmatrix} \\
&= \boxed{ -2e^{-\rho^{2}}\mathbf{a}_{z} }
\end{align}
$$
$$
\begin{align}
\nabla \times \mathbf{B} &= \begin{vmatrix}
\frac{\mathbf{a}_{r}}{r^{2}\sin \theta} & \frac{\mathbf{a}_{\theta}}{r\sin \theta} & \frac{\mathbf{a}_{\phi}}{r} \\
\frac{ \partial  }{ \partial r }  & \frac{ \partial  }{ \partial \theta }  & \frac{ \partial  }{ \partial \phi }  \\
2r\cos \theta & r^{2} & 0
\end{vmatrix} \\
&= \boxed{ 2(1+\sin \theta)\mathbf{a}_{\phi} }
\end{align}
$$
___
###### Problem 2
For the following electric field, find the time rate of increase of $B_{y}$ at $t = 10^{-8}\text{s}$ for $z = 1 / 4\text{m}$.
$$
\mathbf{E} = E_{0}\cos(6\pi \times 10^{8}t-2\pi z)\mathbf{a}_{x} [\text{V/m}]
$$
___
Sol)
By the point form of Faraday's law,
$$
\begin{align}
\nabla \times \mathbf{E} &= \begin{vmatrix}
\mathbf{a}_{x} & \mathbf{a}_{y} & \mathbf{a}_{z} \\
\frac{ \partial  }{ \partial x }  & \frac{ \partial  }{ \partial y }  & \frac{ \partial  }{ \partial z }  \\
E_{x} & 0 & 0
\end{vmatrix}  \\
&= 2\pi E_{0}\sin(6\pi \times 10^{8}t-2\pi z)\mathbf{a}_{y} \\
&=2\pi E_{0}\sin\left( 6\pi-\frac{1}{2}\pi \right) \\
&= -2\pi E_{0} \\
&= -\frac{ \partial \mathbf{B} }{ \partial t }
\end{align}
$$
So the time rate of increase of $B_{y}$ at $t=10^{-8}(s)$ for $z = 1 / 4(m)$ is $2\pi E_{0}$.
___
###### Problem 3
For the following electric field, find $\mathbf{B}$ that satisfies Faraday's law in point form.
$$
\mathbf{E} = E_{0}\mathbf{a}_{y}\cos(3\pi \times 10^{8}t+0.2\pi(4x+3z))
$$
___
Sol)
$$
\begin{align}
\nabla \times \mathbf{E} &= \begin{vmatrix}
\mathbf{a}_{x} & \mathbf{a}_{y} & \mathbf{a}_{z} \\
\frac{ \partial  }{ \partial x }  & \frac{ \partial  }{ \partial y }  & \frac{ \partial  }{ \partial z }  \\
0 & E_{y} & 0
\end{vmatrix}  \\
&= -\frac{ \partial E_{y} }{ \partial z }\mathbf{a}_{x}+\frac{ \partial E_{y} }{ \partial x } \mathbf{a}_{z}  \\
&=0.6\pi E_{0}\sin(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{x} \\
&- 0.8\pi E_{0} \sin(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{z} \\
&= -\frac{ \partial \mathbf{B} }{ \partial t }
\end{align}
$$
$$
\begin{align}
\mathbf{B} &= -\frac{0.6\pi E_{0}}{3\pi \times 10^{8}}\cos(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{x} \\
&+\frac{0.8\pi E_{0}}{3\pi \times 10^{8}}\cos(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{z} \\
&= -(2\times 10^{-9})E_{0}\cos(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{x} \\
&+ \left( \frac{8}{3}\times 10^{-9} \right)E_{0}\cos(3\pi \times 10^{8}t+0.2\pi(4x+3z))\mathbf{a}_{z}
\end{align}
$$
___
###### Problem 4
In a certain region, $$\mathbf{J}=(2y\mathbf{a}_{x}+xz\mathbf{a}_{y}+z^{3}\mathbf{a}_{z})\sin(10^{4}t)$$ Find $\rho_{v}$ if $\rho_{v}(x, y, z,0) = 0$.
___
Sol)
By Law of conservation of charge,
$$
\begin{align}
\nabla \cdot \mathbf{J} &= 3z^{2}\sin(10^{4}t) \\
&= -\frac{ \partial \rho_{v} }{ \partial t } \\
\xrightarrow{\text{integrate with }t}\rho_{v}&=\boxed{ 3\times10^{-4}z^{2}(\cos(10^{4}t)-1)[\text{C/m}^{3}]}
\end{align}
$$
___
###### Problem 5
Evaluate the both sides of Stoke's theorem for the field $$\mathbf{H} = \rho \cos \phi \mathbf{a}_{\rho}+\sin \phi \mathbf{a}_{\phi}$$ and the region defined by $0 \leq \rho \leq 5, 0\leq \phi \leq \pi / 2,$ and $z = 0$.
___
Sol)
Note that Stoke's theorem states that
$$
\int _{S}(\nabla \times \mathbf{H}) \cdot\, d\mathbf{S} = \oint_{\partial S}\mathbf{H} \cdot d\mathbf{l}
$$
where $S$ is the area of region and $\partial S$ is closed path that makes region.
Since the region is defined in $z = 0$ plane, $d\mathbf{S}$ directs to $+z$ direction.
$$
\begin{align}
\int _{S} (\nabla \times \mathbf{H})\cdot d\mathbf{S} &= \int _{S}\begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho }  & \frac{ \partial  }{ \partial \phi }  & \frac{ \partial  }{ \partial z }  \\
\rho \cos \phi & \rho \sin \phi & 0
\end{vmatrix} \, \cdot \rho d\rho d\phi\mathbf{a}_{z} \\
&= \int _{S} (\sin \phi+\rho\sin \phi)\, d\rho \, d\phi \\
&= \int _{0}^{\pi/2}\int _{0}^{5}\sin \phi (1+\rho)\, d\rho  \, d\phi \\
&= \int _{0}^{\pi/2} \sin \phi\, d\phi \cdot \int _{0}^{5}(1+\rho) \, d\rho \\
&=\frac{35}{2}  
\end{align}
$$
$$
\begin{align}
\oint_{\partial S}\mathbf{H}\cdot d\mathbf{l} &= \int_{0}^{5}\rho \cos(0)  \, d\rho +\int_{0}^{\pi/2}  5\sin \phi\, d\phi + \int_{5}^{0}  \rho \cos\left( \frac{\pi}{2} \right)\, d\rho \\
&= \frac{25}{2} + 5 = \frac{35}{2}
\end{align}
$$
___
###### Problem 6
A cube is defined by $1\leq x\leq 1.2, 1\leq y\leq 1.2, 1\leq z\leq 1.2$. If $\mathbf{D} =2x^{2}y\mathbf{a}_{x}+3x^{2}y^{2}\mathbf{a}_{y}[\text{C/m}^{2}]$

(a) Find the total flux leaving the closed surface of the cube.
(b) Evaluate $\nabla \cdot \mathbf{D}$ at the center of the cube.
(c) Estimate the total charge enclosed within the cube by using $Q = \displaystyle \int_{V} \rho_{v} \, dv \approx \rho_v\Delta x\Delta y\Delta z = \rho_{v}\Delta v$.
___
Sol)
(a)
By Gauss's law and divergence theorem,
$$
\begin{align}
\oint_{S}\mathbf{D}\cdot d\mathbf{S} &= \iiint_{V}\nabla \cdot \mathbf{D} \, dv \\
&= \int _{1}^{1.2}\int _{1}^{1.2}\int _{1}^{1.2}(4xy+6x^{2}y)\, dx  \, dy  \, dz \\
&=0.2\int _{1}^{1.2}[2x^{2}y+2x^{3}y]^{1.2}_{1}  \, dy \\
&= 0.2 \int _{1}^{1.2}2\cdot 0.44y+2\cdot0.728\cdot y  \, dy \\
&=0.2\cdot 1.168 \cdot 0.44 = 0.102784[\text{C}]
\end{align}
$$
(b)
$$
\begin{align}
(\nabla \cdot \mathbf{D})_{\text{center}} &= (4xy+6x^{2}y)_{\text{center}} \\
&= 4.84 + 7.986 \\
&= 12.826
\end{align}
$$
(c)
Since $\rho_{v} \approx (\nabla \cdot \mathbf{D})_{\text{center}}$,
$$
\begin{align}
Q &= \rho_{v}\Delta v \\
&\approx (\nabla \cdot \mathbf{D})_{\text{center}}\cdot (0.2)^{3} \\
&= 0.102608 [\text{C}]
\end{align}
$$
___
###### Problem 7
Given the field $\displaystyle \mathbf{D} = 6\rho \sin \frac{1}{2}\phi \mathbf{a}_{\rho}+\frac{3}{2}\rho \cos \frac{1}{2}\phi \mathbf{a}_{\phi}[\text{C/m}^{2}]$, evaluate the both sides of the divergence theorem for the region bounded by $\rho=2, \phi=0, \phi=\pi, z=0,$ and $z = 5$.
___
Sol)
![[Pasted image 20241127053154.png|center|400]]
Here is the region.
Divergence theorem states that
$$
\oint_{S}\mathbf{D}\cdot d\mathbf{S} = \iiint_{V}\nabla \cdot \mathbf{D}\,dv
$$
$$
\begin{align}
\oint_{S}\mathbf{D}\cdot d\mathbf{S}&= \cancelto{ 0 }{ \int_{\text{top}}\mathbf{D} \cdot d\mathbf{S} }+\cancelto{ 0 }{ \int_{\text{bottom}} \mathbf{D} \cdot d\mathbf{S }}+\int_{\text{round side}}  \mathbf{D} \cdot d\mathbf{S} \\
&+ \int_{\text{left1}} \mathbf{D} \cdot d\mathbf{S} +\cancelto{ 0 }{ \int_{\text{left2}} \mathbf{D}\cdot d\mathbf{S} } \\
&= \int _{z=0}^{z=5}\int _{\phi=0}^{\phi=\pi} 24\sin\left( \frac{1}{2}\phi \right)\, d\phi  \, dz - \int_{\rho=0}^{\rho=2} \int_{z=0}^{z=5} \frac{3}{2}\rho  \, dz  \, d\rho  \\
&= 5\cdot 24\cdot 2 - 5\cdot 3 = 5\cdot 45 = \boxed{ 225 \text{[C]}}
\end{align}
$$
$$
\begin{align}
\iiint_{V} \nabla \cdot \mathbf{D} \, dv &= \iiint_{V} \left(\frac{1}{\rho}\frac{ \partial  }{ \partial \rho }\rho D_{\rho} + \frac{1}{\rho}\frac{ \partial  }{ \partial \phi } D_{\phi} + \frac{ \partial  }{ \partial z } D_{z} \right) \rho d\rho d\phi dz \\
&= \iiint_{V} \left(\frac{1}{\rho}12\rho \sin\left( \frac{1}{2}\phi \right) -\frac{1}{\rho} \frac{3}{4}\rho\sin\left( \frac{1}{2}\phi \right) + 0 \right) \rho d\rho d\phi dz \\
&= \iiint_{V} \frac{45}{4}\rho \sin\left( \frac{1}{2}\phi \right) d\rho d\phi dz \\
&=\frac{45}{4}\cdot 5\cdot 2\cdot 2 = \boxed{ 225 \text{[C]}}
\end{align}
$$
___
