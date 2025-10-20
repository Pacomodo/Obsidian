___
###### Problem 1

Express $P(3, 0, 5)$ in cylindrical coordinates.
___
Sol)
Note that the conversion between cartesian coordinates and cylindrical coordinate.
$$
\begin{align}
P(x, y, z) &\rightarrow P\left( \sqrt{ x^{2} +y^{2}}, \tan ^{-1}\left( \frac{y}{x} \right), z \right) \\
P(\rho, \phi, z) &\rightarrow P(\rho \cos \phi , \rho \sin \phi, z) \\
\end{align}
$$
$P(3, 0, 5) = P(3, 0, 5)$
___
###### Problem 2

Express $P\left( 1, \frac{\pi}{2}, -3 \right)$ in Cartesian coordinates.
___
Sol)
$P\left( 1, \frac{\pi}{2}, -3 \right) = P(0, 1, -3)$.
___
###### Problem 3

Transform the vector $\mathbf{B} = y\mathbf{a}_{x}-x\mathbf{a}_{y}+z\mathbf{a}_{z}$ into cylindrical coordinates.
___
Sol)
Note that the conversion between cartesian coordinates and cylindrical coordinate when coodinate express as cylindrical coordinates.
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
\begin{bmatrix}
\mathbf{a}_{\rho} \\
\mathbf{a}_{\phi} \\
\mathbf{a}_{z}
\end{bmatrix} &= \begin{bmatrix}
\cos \phi & \sin \phi & 0 \\
-\sin \phi & \cos \phi & 0 \\
0 & 0 & 1
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}
\end{align}
$$
Since $x=\rho \cos \phi , y=\rho \sin \phi, z=z$,
$$
\begin{align}
\mathbf{B} &= y\mathbf{a}_{x}-x\mathbf{a}_{y}+z\mathbf{a}_{z} \\
&=(\rho \sin \phi \cos \phi-\rho \cos \phi \sin \phi)\mathbf{a}_{\rho} \\
&+(-\rho \sin ^{2} \phi-\rho \cos ^{2}\phi)\mathbf{a}_{\phi} \\
&+ z\mathbf{a}_{z} \\
&= -\rho \mathbf{a}_{\phi}+z\mathbf{a}_{z}
\end{align}
$$
___
###### Problem 4

Express the vector $\mathbf{A} = (\cos \phi)\mathbf{a}_{\rho}-2\rho \mathbf{a}_{\phi}+5\mathbf{a}_{z}$ in Cartesian coordinates.
___
Sol)
Since $\rho = \sqrt{ x^{2} +y^{2}}, \cos \phi=\frac{x}{\sqrt{ x^{2}+y^{2} }}, \sin \phi=\frac{y}{\sqrt{ x^{2}+y^{2} }}$,
$$
\begin{align}
\mathbf{A} &= \frac{x}{\sqrt{ x^{2}+y^{2} }}\left( \frac{x}{\sqrt{ x^{2} +y^{2}}}\mathbf{a}_{x}+\frac{y}{\sqrt{ x^{2}+y^{2} }}\mathbf{a}_{y} \right) \\
&-2\sqrt{ x^{2}+y^{2} }\left( -\frac{y}{\sqrt{ x^{2} +y^{2}}} \mathbf{a}_{x}+\frac{x}{\sqrt{ x^{2} +y^{2}}}\mathbf{a}_{y}\right)+5\mathbf{a}_{z} \\
&= \left( \frac{x^{2}}{x^{2}+y^{2}}+2y \right)\mathbf{a}_{x}+\left( \frac{xy}{x^{2}+y^{2}}-2x \right)\mathbf{a}_{y}+5\mathbf{a}_{z}
\end{align}
$$
___
###### Problem 5

Express the vector $\mathbf{D} = (x^{2}+y^{2})^{-1}(x\mathbf{a}_{x}+y\mathbf{a}_{y})$ in cylindrical coordinates.
___
Sol)
Since $\rho=\sqrt{ x^{2}+y^{2} }, x=\rho \cos \phi,y=\rho \sin \phi$,
$$
\begin{align}
\mathbf{D} &= \frac{1}{x^{2}+y^{2}}(x\mathbf{a}_{x}+y\mathbf{a}_{y}) \\
&= \frac{1}{\rho^{2}}(\rho \cos \phi(\cos \phi \mathbf{a}_{\rho}-\sin \phi \mathbf{a}_{\phi})+\rho \sin \phi(\sin \phi \mathbf{a}_{\rho}+\cos \phi \mathbf{a}_{\phi})) \\
&=\frac{1}{\rho}\mathbf{a}_{\rho}
\end{align}
$$
___
###### Problem 6

$\mathbf{A} = 2\mathbf{a}_{x}+4\mathbf{a}_{y}+10\mathbf{a}_{z}$ and $\mathbf{B} = -5\mathbf{a}_{\rho}+\mathbf{a}_{\phi}-3\mathbf{a}_{z}$. Find the angle between $\mathbf{A}$ and $\mathbf{B}$ at $P(0, 2, -5)$.
___
Sol)
First, convert $\mathbf{B}$ into cartesian coordinates.
$$
\begin{align}
\mathbf{B} &= -5(\cos \phi \mathbf{a}_{x}+\sin \phi \mathbf{a}_{y})+(-\sin \phi \mathbf{a}_{x}+\cos \phi \mathbf{a}_{y})-3\mathbf{a}_{z} \\
&= -5(\mathbf{a}_{y})+(-\mathbf{a}_{x})-3\mathbf{a}_{z} \\
&=-\mathbf{a}_{x}-5\mathbf{a}_{y}-3\mathbf{a}_{z}
\end{align}
$$
So, angle betweeen $\mathbf{A}$ and $\mathbf{B}$ is
$$
\begin{align}
\mathbf{A}\cdot \mathbf{B} &= -2-20-30=-52 \\
\lvert \mathbf{A} \rvert &=\sqrt{ 120 } \\
\lvert \mathbf{B} \rvert &=\sqrt{ 35 } \\
\theta &=\cos ^{-1}\left( -\frac{52}{\sqrt{ 120 }\sqrt{ 35 }} \right) =\boxed{ \cos ^{-1}\left( -\frac{26}{5\sqrt{ 42 }} \right) }\approx 2.50\text{ rad}
\end{align}
$$
___
###### Problem 7

A circle is given by $\rho=2$ and $z=0$. Express the unit vector $\mathbf{a}_{t}$ in Cartesian coordinates that is tangent to the circle at $(-\sqrt{ 3 }, 1, 0)$.

___
Sol)
$\mathbf{a}_{t} = \mp(\frac{1}{2}\mathbf{a}_{x}+\frac{\sqrt{ 3 }}{2}\mathbf{a}_{y})$.
___
###### Problem 8

Express point $P(-2, 6, 0)$ in spherical coordinates.
___
Sol)
Note that the conversion between cartesian coordinates and spherical coordinates.
$$
r = \sqrt{x^{2}+y^{2}+z^{2}}, \theta=\arctan\left( \frac{\sqrt{ x^{2}+y^{2} }}{z} \right),\phi=\arctan\left( \frac{y}{x} \right)
$$
So, $P(-2, 6, 0)=P\left( 2\sqrt{ 10 }, \frac{\pi}{2} , \arctan(-3)\right)$
___
###### Problem 9

Express point $P\left( 10, \frac{\pi}{4}, \frac{\pi}{3} \right)$ in Cartesian coordinates.
___
Sol)
$$
x=r\sin \theta \cos \phi, y=r\sin \theta \sin \phi, z=r\cos \theta
$$
So, $P\left( 10, \frac{\pi}{4}, \frac{\pi}{3} \right)=P\left( \frac{5\sqrt{ 2 }}{2},\frac{5\sqrt{ 6 }}{2},5\sqrt{ 2 } \right)$
___
###### Problem 10

Express the vector $\mathbf{G} = (\frac{xz}{y})\mathbf{a}_{x}$ in spherical coordinates.
___
Sol)
$$
\frac{xz}{y}=\frac{r^{2}\sin \theta \cos \phi \cos \theta}{r\sin \theta \sin \phi} = \frac{r\cos \theta}{\tan \phi}
$$
$$
\begin{align}
\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}&=\begin{bmatrix}
\sin \theta \cos \phi & \cos \theta \cos \phi & -\sin \phi \\
\sin \theta \sin \phi & \cos \theta \sin \phi & \cos \phi \\
\cos \theta & -\sin \theta & 0
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{r} \\
\mathbf{a}_{\theta} \\
\mathbf{a}_{\phi}
\end{bmatrix}
\end{align}
$$
So,
$$
\begin{align}
\mathbf{G} &= \left( \frac{xz}{y} \right)\mathbf{a}_{x} \\
&= \boxed{ \frac{r\cos \theta}{\tan \phi}(\sin \theta \cos \phi \mathbf{a}_{r}+\cos \theta \cos \phi \mathbf{a}_{\theta}-\sin \phi \mathbf{a}_{\phi}) } \\
\end{align}
$$
___
###### Problem 11

Express the unit vector in the direction of $\mathbf{F} = (1 / r^{2})[\cos \phi \mathbf{a}_{r}+(\sin \phi / \sin \theta)\mathbf{a}_{\phi}]$ at $P(0.8, \pi / 6, \pi / 4)$ in spherical coordinates.
___
Sol)
$$
\begin{align}
\mathbf{F} &= \frac{25}{16}\left( \frac{\sqrt{ 2 }}{2}\mathbf{a}_{r}+\frac{\frac{\sqrt{ 2 }}{2}}{\frac{1}{2}}\mathbf{a}_{\phi} \right) \\
&= \frac{25\sqrt{ 2 }}{32}\left( \mathbf{a}_{r}+2\mathbf{a}_{\phi} \right) \\
\mathbf{a}_{\mathbf{F}}&=\boxed{ \frac{1}{\sqrt{ 5 }}(\mathbf{a}_{r}+2\mathbf{a}_{\phi}) }\approx 0.45\mathbf{a}_{r}+0.89\mathbf{a}_{\phi}
\end{align}
$$
___
###### Problem 12

A vector is expressed in spherical coordinates by $\mathbf{A}=\frac{25}{r^{2}}\mathbf{a}_{r}$. Find the angle that $\mathbf{A}$ makes with the vector $\mathbf{B} = 2\mathbf{a}_{x}-2\mathbf{a}_{y}+\mathbf{a}_{z}$ at the point $(x=-3, y=4, z=-5)$.

___
Sol)
Note that the conversion between spherical coordinates and cartesian coordinates.
$$
\begin{align}
\begin{bmatrix}
\mathbf{a}_{r} \\
\mathbf{a}_{\theta} \\
\mathbf{a}_{\phi}
\end{bmatrix}&=\begin{bmatrix}
\sin \theta \cos \phi & \sin \theta \sin \phi & \cos \theta \\
\cos \theta \cos \phi  & \cos \theta \sin \phi & -\sin \theta \\
-\sin \phi & \cos \phi & 0
\end{bmatrix}\begin{bmatrix}
\mathbf{a}_{x} \\
\mathbf{a}_{y} \\
\mathbf{a}_{z}
\end{bmatrix}
\end{align}
$$
Note that $r=\sqrt{ x^{2}+y^{2}+z^{2} }$, $\sin \theta = \frac{\sqrt{ x^{2}+y^{2} }}{r}, \cos \theta =\frac{z}{r}$, $\sin \phi = \frac{y}{\sqrt{ x^{2}+y^{2} }}, \cos \phi =\frac{x}{\sqrt{ x^{2}+y^{2} }}$.
So, $\sin \theta=\frac{\sqrt{ 2 }}{2}, \cos \theta=-\frac{\sqrt{ 2 }}{2}, \sin \phi=\frac{4}{5}, \cos \phi=-\frac{3}{5}$.
So, 
$$\mathbf{A}=\frac{1}{2}\mathbf{a}_{r} = \frac{1}{2}\left( -\frac{3\sqrt{ 2 }}{10}\mathbf{a}_{x}+\frac{2\sqrt{ 2 }}{5}\mathbf{a}_{y}-\frac{\sqrt{ 2 }}{2}\mathbf{a}_{z} \right)$$
Angle between $\mathbf{A}$ and $\mathbf{B}$ is
$$
\begin{align}
\cos \alpha &= \frac{\mathbf{A}\cdot \mathbf{B}}{\lvert \mathbf{A} \rvert\lvert \mathbf{B} \rvert  } \\
&=\frac{\left( -\frac{3\sqrt{ 2 }}{10}-\frac{2\sqrt{ 2 }}{5}-\frac{\sqrt{ 2 }}{4} \right)}{\sqrt{ \frac{18}{400}+\frac{2}{25}+\frac{2}{16} }\cdot \sqrt{ 4+4+1 }} \\
&=\frac{ -\sqrt{ 2 }\left( \frac{7}{10}+\frac{1}{4} \right)}{3\sqrt{ \frac{1}{4} }} \\
&= -\frac{\sqrt{ 2 }\left( \frac{7}{5}+\frac{1}{2} \right)}{3}=-\frac{19\sqrt{ 2 }}{30}\\
\alpha&=\boxed{ \cos ^{-1}\left( -\frac{19\sqrt{ 2 }}{30} \right) }\approx 2.68\text{ rad}
\end{align}
$$
___
###### Problem 13

A closed surface is identified by the surfaces $r=2, r=6, \theta=30^{\circ}, \theta=60^{\circ}, \phi=20^{\circ}, \phi=60^{\circ}$. Find the area of the closed surface.

___
Sol)
Let this closed surface be $S$.
Then, $S = S_{\text{left}}+S_{\text{right}}+\cdots+S_{\text{bottom}}$. In other words, $S$ consisted of 6 surfaces.
$$
\begin{align}
S_{\text{left}} &= \int_{\phi=20^{\circ}}^{\phi=60^{\circ}} \int_{\theta=30^{\circ}}^{\theta=60^{\circ}} r^{2}\sin \theta \, d\theta  \, d\phi \\
&=4[40^{\circ}][-\cos \theta]^{\pi/3}_{\pi / 6}=4[40^{\circ}]\left[ \frac{\sqrt{ 3 }-1}{2} \right] \\
S_{\text{right}}&=36[40^{\circ}]\left[ \frac{\sqrt{ 3 }-1}{2} \right] \\
S_{\text{left}}+S_{\text{right}}&=20[40^{\circ}](\sqrt{ 3 }-1)
\end{align}
$$
$$
\begin{align}
S_{\text{front}} &= \int_{\theta=30^{\circ}}^{\theta=60^{\circ}} \int_{r=2}^{r=6} r \, dr  \, d\theta  \\
&=\frac{\pi}{6}\cdot 16 \\
S_{\text{back}} &=\frac{\pi}{6}\cdot 16 \\
S_{\text{front}}+S_{\text{back}} &=\frac{16\pi}{3}
\end{align}
$$
$$
\begin{align}
S_{\text{top}} &= \int_{\phi=20^{\circ}}^{\phi=60^{\circ}} \int_{r=2}^{r=6} r\sin \theta \, dr  \, d\phi \\
&=16\cdot[40^{\circ}]\cdot \frac{1}{2} \\
S_{\text{bottom}} &=16[40^{\circ}] \frac{\sqrt{ 3 }}{2} \\
S_{\text{top}}+S_{\text{bottom}}&=8[40^{\circ}](\sqrt{ 3 }+1)
\end{align}
$$
So,
$$
\begin{align}
S&=[40^{\circ}](28\sqrt{ 3 }-12)+\frac{16\pi}{3} \\
&=\frac{2\pi}{9}(28\sqrt{ 3}-12)+\frac{48\pi}{9} \\
&=\boxed{\frac{2\pi}{9}(28\sqrt{ 3 }+12)} \approx 42.24
\end{align}
$$
___
###### Problem 13(Correction for typo)

A closed surface is identified by the surfaces $r=2, r=4, \theta=30^{\circ}, \theta=50^{\circ}, \phi=20^{\circ}, \phi=60^{\circ}$. Find the area of the closed surface.

___
Sol)
Sol)
Let this closed surface be $S$.
Then, $S = S_{\text{left}}+S_{\text{right}}+\cdots+S_{\text{bottom}}$. In other words, $S$ consisted of 6 surfaces.
$$
\begin{align}
S_{\text{left}} &= \int_{\phi=20^{\circ}}^{\phi=60^{\circ}} \int_{\theta=30^{\circ}}^{\theta=50^{\circ}} r^{2}\sin \theta \, d\theta  \, d\phi \\
&=4[40^{\circ}][-\cos \theta]^{50^{\circ}}_{30^{\circ}} \\
S_{\text{right}}&=16[40^{\circ}][-\cos \theta]^{50^{\circ}}_{30^{\circ}} \\
S_{\text{left}}+S_{\text{right}}&=20[40^{\circ}][-\cos \theta]^{50^{\circ}}_{30^{\circ}}
\end{align}
$$
$$
\begin{align}
S_{\text{front}} &= \int_{\theta=30^{\circ}}^{\theta=50^{\circ}} \int_{r=2}^{r=4} r \, dr  \, d\theta  \\
&=20^{\circ}\cdot 6 \\
S_{\text{back}} &=20^{\circ}\cdot 6 \\
S_{\text{front}}+S_{\text{back}} &=40^{\circ}\cdot 6
\end{align}
$$
$$
\begin{align}
S_{\text{top}} &= \int_{\phi=20^{\circ}}^{\phi=60^{\circ}} \int_{r=2}^{r=4} r\sin \theta \, dr  \, d\phi \\
&=6\cdot[40^{\circ}]\cdot \sin 30^{\circ} \\
S_{\text{bottom}} &=6[40^{\circ}] \sin 50^{\circ} \\
S_{\text{top}}+S_{\text{bottom}}&=6[40^{\circ}](\sin 50^{\circ}+\sin 30^{\circ})
\end{align}
$$
So,
$$
\begin{align}
S&=[40^{\circ}](-20\cos 50^{\circ}+20\cos 30^{\circ}+6+6\sin 50^{\circ}+6\sin 30^{\circ}) \\
&=\boxed{ \frac{2\pi}{9}\left( 10\sqrt{ 3 }+9+6\sin \frac{5\pi}{18} -20\cos \frac{5\pi}{18}\right) } \approx 12.61
\end{align}
$$
___
