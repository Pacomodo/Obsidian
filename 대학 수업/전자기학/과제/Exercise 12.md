___
###### Problem 1
Two perfect dieletrics meet on plane $z=0$. For $z>0$, $\varepsilon_{r_{1}}=4$ and for $z < 0$, $\varepsilon_{r_{2}}=3$. A uniform electric field $\mathbf{E}_{1} = 5\mathbf{a}_{x}-2\mathbf{a}_{y}+3\mathbf{a}_{z}[\text{kV/m}]$ exists for $z>0$. Find $\mathbf{E}_{2}$ for $z<0$.
___
Sol)
Note that meeting surface is $z=0$, so, the unit normal vector of meeting surface $S$ directed to medium 1 is $\mathbf{a}_{n}=\mathbf{a}_{z}$.
Let $\mathbf{E}_{2} = x\mathbf{a}_x+y\mathbf{a}_{y}+z\mathbf{a}_{z}$.
By boundary condition,
$$
\begin{align}
\mathbf{a}_{z}\times(\mathbf{E}_{1}-\mathbf{E}_{2}) &= \mathbf{a}_{z}\times((5-x)\mathbf{a}_{x}+(-2-y)\mathbf{a}_{y}+(3-z)\mathbf{a}_{z}) \\
&=0 \\
\Rightarrow x=5, y=-2
\end{align}
$$
$$
\begin{align}
\mathbf{a}_{z}\cdot(\mathbf{D}_{1}-\mathbf{D}_{2}) &= \varepsilon_{0}\mathbf{a}_{z}\cdot(4\mathbf{E}_{1}-3\mathbf{E}_{2}) \\
&=\varepsilon_{0}\mathbf{a}_{z}\cdot(5\mathbf{a}_{x}-2\mathbf{a}_{y}+(12-3z)\mathbf{a}_{z}) \\
&=0 \\
\Rightarrow z=4
\end{align}
$$
Therefore, $\mathbf{E}_{2} = 5\mathbf{a}_{x}-2\mathbf{a}_{y}+4\mathbf{a}_{z}[\text{kV/m}]$.
___
###### Problem 2
We locate a dielectric slab ($\varepsilon_{r}=2.1$) in the region $0\leq x\leq a$, and assume free space where $x<0$ and $x > a$. Outside the dielectric slab, there is a uniform field $\mathbf{E}_{\text{out}} = E_{0}\mathbf{a}_{x}[\text{V/m}]$. Find $\mathbf{D}, \mathbf{E},$ and $\mathbf{P}$ everywhere.
___
Sol)
I'll assume that this dielectric slab is perfect dielectric slab.
Let the meeting surface is $x=0$, so the unit normal vector of meeting surface directed to dielectric slab is $\mathbf{a}_{n} = \mathbf{a}_{x}$.
Let $\mathbf{E}_{\text{in}}=x\mathbf{a}_{x}+y\mathbf{a}_{y}+z\mathbf{a}_{z}$.
By boundary condition,
$$
\begin{align}
\mathbf{a}_{x}\times(\mathbf{E}_{\text{in}}-\mathbf{E}_{\text{out}})&=\mathbf{a}_{x}\times((x-E_{0})\mathbf{a}_{x}+y\mathbf{a}_{y}+z\mathbf{a}_{z}) \\
&= 0 \\
\Rightarrow y=0, z=0
\end{align}
$$
$$
\begin{align}
\mathbf{a}_{x}\cdot (\mathbf{D}_{\text{in}}-\mathbf{D}_{\text{out}}) &= \mathbf{a}_{x}\cdot(2.1\varepsilon_{0}\mathbf{E}_{\text{in}}-\varepsilon_{0}\mathbf{E}_{\text{out}}) \\
&=\varepsilon_{0}\mathbf{a}_{x}\cdot(2.1x-E_{0})\mathbf{a}_{x} \\
&= (2.1x-E_{0})\varepsilon_{0} = 0 \\
\Rightarrow x=\frac{E_{0}}{2.1}=\frac{10}{21}E_{0}
\end{align}
$$
Therefore,
$$
\begin{align}
\mathbf{E}_{\text{in}} = \frac{10}{21}E_{0}\mathbf{a}_{x} \ &\setminus \ \mathbf{E}_{\text{out}} = E_{0}\mathbf{a}_{x}  \\
\mathbf{D}_{\text{in}} = \varepsilon_{0}E_{0}\mathbf{a}_{x} \ &\setminus \ \mathbf{D}_{\text{out}} = \varepsilon_{0}E_{0}\mathbf{a}_{x} \\
\mathbf{P}_{\text{in}} = \frac{11}{21}\varepsilon_{0}E_{0}\mathbf{a}_{x} \ &\setminus \ \mathbf{P}_{\text{out}} = 0
\end{align}
$$
___
###### Problem 3
Medium, consisting of the region $r<a$ in spherical coordinates, is a magnetic material of permeability $\mu_{1}$, whereas medium 2, consisting of the region $r>a$, is free space. The magnetic flux densities in the two media are given by $$\begin{align}\mathbf{B}_{1}&=B_{01}(\cos \theta \mathbf{a}_{r}-\sin \theta \mathbf{a}_{\theta})\\\mathbf{B}_{2}&=B_{02}\left[ \left( 1+1.94\frac{a^{3}}{r^{3}} \right)\cos \theta \mathbf{a}_{r}-\left( 1-0.97 \frac{a^{3}}{r^{3}} \right)\sin \theta \mathbf{a}_{\theta} \right]\end{align}$$ respectively. Find $\mu_{1}$.
___
Sol)
Assume that this magnetic material has no conduction current. Note that the normal vector to the meeting surface is $\mathbf{a}_{r}$.
By Boundary condition,
$$
\begin{align}
\mathbf{a}_{r}\cdot(\mathbf{B}_{2}-\mathbf{B}_{1}) &\Rightarrow 2.94B_{02}=B_{01} \\
\mathbf{a}_{r}\times (\mathbf{H}_{2}-\mathbf{H}_{1}) &=\mathbf{a}_{r}\times\left( \frac{\mathbf{B}_{2}}{\mu_{0}}-\frac{\mathbf{B}_{1}}{\mu_{1}} \right) \\
&\Rightarrow \frac{0.03}{\mu_{0}}B_{02} = \frac{1}{\mu_{1}}B_{01}  \\
\frac{0.03}{\mu_{0}}=\frac{2.94}{\mu_{1}} &\Rightarrow \mu_{1} = 98\mu_{0}
\end{align}
$$
___
###### Problem 4
A perfect dielectric sphere with relative permittivity $\varepsilon_{r}$ centered at the origin rests in free space. In this sphere, there is an electric field intensity $\mathbf{E}_{2}=E_{0}\mathbf{a}_{z}$. Find the electric field intensity $\mathbf{E}_{1}$ on the outside surface of the sphere?
___
Sol)
For convinience, convert $\mathbf{E}_{2}$ into spherical coordinates.
$$
\mathbf{E}_{2}=E_{0}\cos \theta \mathbf{a}_{r}-E_{0}\sin \theta \mathbf{a}_{\theta}
$$
The unit normal vector to the meeting surface directed to the free space is $\mathbf{a}_{n} = \mathbf{a}_{r}$.
By boundary condition,
$$
\begin{align}
\mathbf{a}_{r}\times(\mathbf{E}_{1}-\mathbf{E}_{2}) &= 0 \\
\Rightarrow \mathbf{E}_{1} = x\mathbf{a}_{r}-E_{0}\sin \theta \mathbf{a}_{\theta}
\end{align}
$$
$$
\begin{align}
\mathbf{a}_{r}\cdot(\mathbf{D}_{1}-\mathbf{D}_{2})&=\varepsilon_{0}\mathbf{a}_{r}\cdot(\mathbf{E}_{1}-\varepsilon_{r}\mathbf{E}_{2}) \\
&=\varepsilon_{0}\cdot(x-\varepsilon_{r}E_{0}\cos \theta) = 0 \\
\Rightarrow x &=\varepsilon _{r}E_{0}\cos \theta
\end{align}
$$
$$
\mathbf{E}_{1} = \varepsilon_{r}E_{0}\cos \theta \mathbf{a}_{r}-E_{0}\sin \theta \mathbf{a}_{\theta}
$$
___
