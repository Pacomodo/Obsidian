___
##### Problem 1

Vectors $\mathbf{A}, \mathbf{B}$ and $\mathbf{C}$ at a point are given by 
$$\begin{align}
\mathbf{A} &= A_{1}\mathbf{a}_{1}+A_{2}\mathbf{a}_{2}+A_{3}\mathbf{a}_{3} \\
\mathbf{B} &= B_{1}\mathbf{a}_{1}+B_{2}\mathbf{a}_{2}+B_{3}\mathbf{a}_{3} \\
\mathbf{C} &= C_{1}\mathbf{a}_{1}+C_{2}\mathbf{a}_{2}+C_{3}\mathbf{a}_{3} \\
\end{align}
$$
Prove that $\mathbf{A}\cdot \mathbf{B}\times \mathbf{C} = \mathbf{B}\cdot \mathbf{C}\times \mathbf{A} = \mathbf{C}\cdot \mathbf{A}\times \mathbf{B}$.
___
Sol) For convenience, I will denote $\mathbf{A}$ as $(A_{1},A_{2},A_{3})$ instead of $A_{1}\mathbf{a}_{1}+A_{2}\mathbf{a}_{2}+A_{3}\mathbf{a}_{3}$.
Similiarly, $\mathbf{B} = (B_{1},B_{2},B_{3}), \mathbf{C}=(C_{1}, C_{2}, C_{3})$.
Since we can take basis vector arbitrary, let $\mathbf{a}_{1}\perp \mathbf{a}_{2}\perp \mathbf{a}_{3}$, $\mathbf{a}_{1}\times \mathbf{a}_{2} = \mathbf{a}_{3}$ and all basis are unit vector.
Then, $\mathbf{A}\cdot \mathbf{B}\times \mathbf{C}$ is $$(A_{1},A_{2},A_{3})\cdot \begin{vmatrix}\mathbf{a}_{1} & \mathbf{a}_{2} & \mathbf{a}_{3} \\B_{1} & B_{2} & B_{3} \\C_{1} & C_{2} & C_{3}\end{vmatrix}=\begin{vmatrix}A_{1} & A_{2} & A_{3} \\B_{1} & B_{2} & B_{3} \\C_{1} & C_{2} & C_{3}\end{vmatrix}$$
$\mathbf{B}\cdot \mathbf{C}\times \mathbf{A}$ is 
$$
\begin{align}
(B_{1},B_{2},B_{3})\cdot \begin{vmatrix}
\mathbf{a}_{1} & \mathbf{a}_{2} & \mathbf{a}_{3} \\
C_{1} & C_{2} & C_{3} \\
A_{1} & A_{2} & A_{3}
\end{vmatrix}=\begin{vmatrix}
B_{1} & B_{2} & B_{3} \\
C_{1} & C_{2} & C_{3} \\
A_{1} & A_{2} & A_{3}
\end{vmatrix}
\end{align}
$$
Similarly, $\mathbf{C}\cdot \mathbf{A}\times \mathbf{B}$ is 
$$
\begin{vmatrix}
C_{1} & C_{2} & C_{3} \\
A_{1} & A_{2} & A_{3} \\
B_{1} & B_{2} & B_{3}
\end{vmatrix}
$$
Since the property of determinant, this three values are same.($\because$ Row swapped even number of times.)
___
###### Problem 2

Let $\mathbf{A} = \mathbf{a}_{1}+\alpha \mathbf{a}_{2}+\mathbf{a}_{3}$ and $\mathbf{B}=\alpha \mathbf{a}_{1}+\mathbf{a}_{2}+\mathbf{a}_{3}$. $\mathbf{A}$ and $\mathbf{B}$ at a point are normal to each other.
Find $\alpha$.
___
Sol)
$\mathbf{A}\cdot \mathbf{B} = 2\alpha+1 = 0\rightarrow\alpha=-\frac{1}{2}$
___
###### Problem 3

Given vectors $\mathbf{A} = 2\mathbf{a}_{1}+5\mathbf{a}_{3}$ and $\mathbf{B}=\mathbf{a}_{1}-3\mathbf{a}_{2}+4\mathbf{a}_{3}$ at a point, Find $\lvert \mathbf{A}\times \mathbf{B} \rvert+\mathbf{A}\cdot \mathbf{B}$.
___
Sol)
$\mathbf{A}\cdot \mathbf{B} = 2+20=22$
$\lvert \mathbf{A}\times \mathbf{B} \rvert = \lvert \begin{vmatrix}\mathbf{a}_{1}&\mathbf{a}_{2}&\mathbf{a}_{3}\\2&0&5\\1&-3&4\end{vmatrix} \rvert=\sqrt{ 15^{2} +3^{2}+6^{2}}=\sqrt{ 270 }=3\sqrt{ 30 }$
So, the answer is $22+3\sqrt{ 30 }$.
___
###### Problem 4

The two planes, $x+y=0$ and $y+z=1$ intersect in the line $L$. Find the differential length vector $d\mathbf{l}$ along $L$ in terms of $dz$.
___
Sol)
$x+y=0\rightarrow dx=-dy$
$y+z=1\rightarrow dy=-dz$
$d\mathbf{l} = dx\mathbf{a}_{x}+dy\mathbf{a}_{y}+dz\mathbf{a}_{z}=dz\mathbf{a}_{x}-dz\mathbf{a}_{y}+dz\mathbf{a}_{z}$.
___
###### Problem 5

Find the differential length vector $d\mathbf{l}$ along the line passing through the two points, $(1,1,1)$ and $(3,-2,4)$.
___
Sol)
We can express $x, y, z$ in terms of $t$.
$$
\begin{align}
x &= 2t+1 \\
y &= -3t+1 \\
z &= 3t+1
\end{align}
$$
Differentiate them.
$dx = 2dt, dy=-3dt, dz=3dt$.
If we express $d\mathbf{l}$ in terms of $dt$, $d\mathbf{l} = 2dt\mathbf{a}_{x}-3dt\mathbf{a}_{y}+3dt\mathbf{a}_{z}$.
___
###### Problem 6

Find the expression for the unit vector normal to the curve $x=y^{2}=z^{3}$ and the line $x=y=z$ at a point $(1,1,1)$.
___
Sol)
1. $dx=2ydy=3zdz\rightarrow dx=2dy=3dz$
So, $d\mathbf{l}$ along the curve is $dx(\mathbf{a}_{x}+\frac{1}{2}\mathbf{a}_{y}+\frac{1}{3}\mathbf{a}_{z})$.
2. $dx=dy=dz$
So, $d\mathbf{l}$ along the line is $dx(\mathbf{a}_{x}+\mathbf{a}_{y}+\mathbf{a}_{z})$.
Vector normal to both curve is $\pm (d\mathbf{l}_{1}\times d\mathbf{l}_{2}) =\pm(dx)^{2}\left( \frac{1}{6}\mathbf{a}_{x}-\frac{2}{3}\mathbf{a}_{y}+\frac{1}{2}\mathbf{a}_{z} \right)$.
Make it unit.
The answer is $\pm \frac{1}{\sqrt{ 26 }}(\mathbf{a}_{x}-4\mathbf{a}_{y}+3\mathbf{a}_{z})$.
___
###### Problem 7

Find the unit vector normal to the surface defined by $x^{2}+y^{2}+4z^{2}=8$ at the point $(2,0,1)$.
___
Sol)
Let $F(x,y,z) = x^{2}+y^{2}+4z^{2}$.
$\nabla F = (2x,2y,8z)=(4,0,8)\rightarrow \mathbf{a}_{n} = \pm \nabla F/\lvert \nabla F \rvert=\pm \frac{1}{\sqrt{ 5 }}(\mathbf{a}_{x}+2\mathbf{a}_{z})$.
___
