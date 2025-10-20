___
###### Problem 1

An electric flux density in free space is $\mathbf{D} = 5z^{2}\mathbf{a}_{z}\text{[C/m}^{2}]$. Find the total charge contained within a cube centered at the origin. The cube has the surfaces at $x=\pm 2, y=\pm 2,$ and $z= \pm 2$.
___
Sol)
Consider gauss law.
$$
\nabla \mathbf{D} = 10z\mathbf{a}_{z}
$$
$$
\int _{-2}^{2}\int _{-2}^{2}\int _{-2}^{2}10z \, dx  \, dy  \, dz=0
$$
___
###### Problem 2

An electric flux density in free space is $\mathbf{D} = 5z^{3}\mathbf{a}_{z}[\text{C/m}^{2}]$. Find the total charge contained within a sphere of $3\text{m}$ radius, centered at the origin.
___
Sol)
Consider gauss law.
The total electric flux emanating from a closed surface is equal to the total charge contained in the volume bounded by closed surface.
For convience, convert $\mathbf{D}$ into spherical coordinate.
$$
\mathbf{D} = 5r^{3}\cos ^{3}\theta(\cos \theta \mathbf{a}_{r}-\sin \theta \mathbf{a}_{\theta})
$$
Note that $r^{2}\sin \theta d\theta d\phi\mathbf{a}_{r}$ is $d\mathbf{S}$.
So,
$$
\begin{align}
\oint_{S}\mathbf{D}\cdot d\mathbf{S} &= \oint_{S}5r^{5}\cos ^{4}\theta \sin \theta d\theta d\phi \\
&=3^{5}\oint_{S}5\cos ^{4}\theta \sin \theta d\theta d\phi \\
&=486\pi \int_{0}^{\pi}5\cos ^{4}\theta \sin \theta \, d\theta \\
&= 486\pi \left[-\cos ^{5}\theta \right]^{\pi}_{0} \\
&=972\pi[\text{C}]
\end{align}
$$
___

