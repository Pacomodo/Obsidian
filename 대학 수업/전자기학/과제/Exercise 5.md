___
###### Problem 1

An electric field in free space is given by $\mathbf{E} = x\mathbf{a}_{x} + y\mathbf{a}_{y}+z\mathbf{a}_{z}[\text{V/m}]$. Find the work done in moving a $1\mu C$ charge through this field. Put units.
(a) from $(x=0, y=0, z=0)$ to $(x=1, y=1, z=1)$
(b) from $(\rho = 2, \phi = 0, z=1)$ to $(\rho=2, \phi=\pi / 2, z=1)$
___
Sol)
(a)
$d\mathbf{l} = dx\mathbf{a}_{x} + dy\mathbf{a}_{y}+dz\mathbf{a}_{z}$.
So,
$$
\begin{align}
V &= \int \mathbf{E}\cdot d\mathbf{l} \\
&= \int xdx+ydy+zdz \\
&=3\int_{0}^{1} t \, dt = \frac{3}{2} \text{[V]}
\end{align}
$$
So, $W = qV = 1.5\mu \text{J}$.
(b)
$d\mathbf{l} = 2d\phi \mathbf{a}_{\phi}$.
Note that conversion between cylindrical coordinates and cartesian coordinates.
$$
x=\rho \cos \phi, y=\rho \sin \phi, z=z
$$
$$
\begin{align}
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
\end{align}
$$
So,
$$
\begin{align}
\mathbf{E} &= 2\cos \phi(\cos \phi \mathbf{a}_{\rho}-\sin \phi \mathbf{a}_{\phi})+2\sin \phi(\sin \phi \mathbf{a}_{\rho}+\cos \phi \mathbf{a}_{\phi})+z\mathbf{a}_{z} \\
&=2\mathbf{a}_{\rho}+z\mathbf{a}_{z}
\end{align}
$$
So,
$$
\begin{align}
V = \int \mathbf{E}\cdot d\mathbf{l} =0
\end{align}
$$
So, $W = 0\text{J}$.
___
###### Problem 2

An electric field in free space is given by $\mathbf{E} = x\mathbf{a}_{x} + 4z\mathbf{a}_{y}+4y\mathbf{a}_{z}$. Given $V(1,1,1) = 10\text{[V]}$, Find $V(3,3,3)$. You may use the fact that $\mathbf{E}$ is a conservative field.
___
Sol)
Let $d\mathbf{l} = dx\mathbf{a}_{x}+dy\mathbf{a}_{y}+dz\mathbf{a}_{z}$.(Take path $x=y=z$).
$$
V = \int xdx+4zdy+4ydz = \int_{1}^{3} 9t \, dt=\frac{72}{2}\text{[V]} 
$$
So, voltage different between $V(1,1,1)$ and $V(3,3,3)$ is $\frac{72}{2}\text{[V]}$.
So, voltage $V(3,3,3) = -26\text{[V]}$.
___
###### Problem 3

For the vector field $\mathbf{A} = x(\mathbf{a}_{x}+\mathbf{a}_{y})$, find the absolute value of $$
\int \mathbf{A} \cdot d\mathbf{S} 
$$ over the rectangular surface having the vertices at $(2,0,0)$, $(2,2,0)$, $(2,2,2)$, and $(2, 0, 2)$.
___
Sol)
Note that $$
d\mathbf{S} = dydz\mathbf{a}_{x}
$$
So,
$$
\int \mathbf{A} \cdot d\mathbf{S} = \int _{0}^{2}\int _{0}^{2}x \, dy  \, dz=8  
$$
___
###### Problem 4

Given $\mathbf{A} = r^{2}\mathbf{a}_{r}+r\sin \theta \mathbf{a}_{\theta}$ in spherical coordinates, find the absolute value of $$
\int \mathbf{A}\cdot d\mathbf{S} 
$$ over the spherical surface defined by $r=1, 0\leq \theta \leq \pi / 2$ and $0 \leq \phi \leq \pi / 2$.
___
Sol)
Note that
$$
d\mathbf{S} = \sin \theta d\theta d\phi \mathbf{a}_{r}
$$
So,
$$
\int \mathbf{A}\cdot d\mathbf{S} = \int _{0}^{\pi/2}\int _{0}^{\pi/2} \sin \theta \, d\theta  \, d\phi = \frac{\pi}{2} 
$$
___
###### Problem 5

Consider the figure and let $\mathbf{B} = 0.2\cos 120\pi t\mathbf{a}_{z}\text{[T]}$. Assuming that the conductor joining two ends of the resistor is perfect, find $I(t)$.
![[Pasted image 20241031101141.png|center|300]]
___
Sol)
Recall Faraday's law.
$$
V=\oint_{C}\mathbf{E}\cdot d\mathbf{l} = -\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} 
$$
$$
\begin{align}
-\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} &= -\frac{d}{dt} (\pi(0.15)^{2} (0.2)\text{cos}120\pi t) \\
&= 120\pi^{2}(0.15)^{2}(0.2)\sin 120\pi t
\end{align}
$$
So, $I(t)$ is
$$
(0.48)\pi^{2}(0.15)^{2}(0.2)\sin 120\pi t = 0.00126\pi^{2} \sin 120\pi t \text{[A]}
$$
___
###### Problem 6

The location of the sliding bar in the figure is given by $x = 5t+2t^{3}$.
![[Pasted image 20241031102619.png|center|300]]
Find the emf at $t=0.4(s)$ along the closed path $C$ with the magnetic flux density given by $\mathbf{B} = 0.8x^{2}\mathbf{a}_{z}$.
___
Sol)
Note that
$$
d\mathbf{S} = dxdy\mathbf{a}_{z}
$$
So,
$$
\begin{align}
-\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} &= -\frac{d}{dt} \int _{0}^{0.2}\int _{0}^{x}0.8x^{2} \, dx  \, dy \\
&=-\frac{d}{dt} \frac{0.16}{3}(5t+2t^{3})^{3} \\
&=-(0.16)(5t+2t^{3})^{2}(6t^{2}+5)\text{[V]}
\end{align}
$$
Substitute $t=0.4$.
___
###### Problem 7

A rectangular loop of wire has corners initially at  $(a/2, b/2, 0), (-a/2, b/2, 0), (-a/2, -b/2, 0)$, and $(a/2, -b/2, 0)$. The loop begins to rotate about the $x$ axis at constant angular velocity $\omega$, with the corner at $(a/2, b/2, 0)$ moving in the $\mathbf{a}_{z}$ direction at $t=0$. The magnetic flux density is given by $\mathbf{B}=B_{0}\mathbf{a}_{z}$. Find the emf in the rotating loop and the direction of the current. Use the fact that the unit normal vector for the flat surface enclosed by the loop is in this case given by $\pm(cos\omega t \mathbf{a}_{z}-sin\omega t \mathbf{a}_{y})$, if necessary.
___
Sol)
$$
\begin{align}
-\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} &= -\frac{d}{dt} \int _{-a /2}^{a/2} \int _{-b /2}^{b/2}B_{0}\cos \omega t \, dx dy \\
&=B_{0}ab\sin \omega t
\end{align}
$$
___
