___
###### Problem 1
A wire along the $z$-axis has a diameter of $1\text{ mm}$ and a conductivity of $5\times 10^{7}\text{ S/m}$. An electric field of $\mathbf{E}=0.01\mathbf{a}_{z}\text{[V/m]}$ is applied. Find
(a) The current density
(b) The current in the wire (the current crossing the cross-sectional surface)
___
Sol)
(a)
By Ohm's law in point form, $\mathbf{J}_{c} = \sigma \mathbf{E}$ where $\sigma$ is the conductivity of the material and $\mathbf{J}_{c}$ is the current density of the material.
Hence,
$$
\begin{align}
\mathbf{J}_{c} &= 5\times 10^{7}\times 0.01 \mathbf{a}_{z}[\text{A/m}^{2}] \\
&= 5\times 10^{5}\mathbf{a}_{z}[\text{A/m}^{2}]
\end{align}
$$
(b)
Total current in wire is the value of surface integral of the current density.
Hence,
$$
\begin{align}
[I]_{\text{total}} &= \int _{S} \mathbf{J}_{c}\cdot d\mathbf{S}\\
&= 5\times 10^{5} \times \frac{0.001^{2}}{4} \times \pi [\text{A}] \\
&=0.125\pi[\text{A}] \\
&\approx 0.393[\text{A}]
\end{align}
$$
___
###### Problem 2
The electric field intensity in a dielectric with a dielectric constant of $2.55$ is $10\mathbf{a}_{x}\text{[kV/m]}$. Find
(a) The polarization vector
(b) The electric flux density
___
Sol)
(a)
Note that the polarization vector $\mathbf{P} =\varepsilon_{0}\chi_{e}\mathbf{E}$ where $\chi_{e}$ is electric susceptibility.
Since dielectric constant $\varepsilon_{r} = 2.55 = 1+\chi_{e}$, electric susceptibility is $1.55$.
Therefore,
$$
\begin{align}
\mathbf{P} &= 8.854\times 10^{-12}\times 1.15 \times 10 \times 10^{3}\mathbf{a}_{x}[\text{C/m}^{2}] \\
&= 1.37237 \times 10^{-7}\mathbf{a}_{x}[\text{C/m}^{2}] \\
&\approx 1.37\times 10^{-7}[\text{C/m}^{2}]
\end{align}
$$
(b)
Note that the electric flux density $\mathbf{D} = \varepsilon_{0}\mathbf{E} + \mathbf{P} = \varepsilon_{0}\varepsilon_{r}\mathbf{E}$, so,
$$
\begin{align}
\mathbf{D} &= 8.854\times 10^{-12}\times2.55\times 10\times 10^{3}\mathbf{a}_{x}[\text{C/m}^{2}] \\
&= 2.25777\times 10^{-7}\mathbf{a}_{x}[\text{C/m}^{2}] \\
&\approx 2.26\times 10^{-7}[\text{C/m}^{2}]
\end{align}
$$
___
###### Problem 3
In a region with $\mu = 4.6\mu_{0}$, the magnetic flux density is $\mathbf{B} = 10e^{-y}\mathbf{a}_{z}[\text{mWb/m}^{2}]$. Find
(a) The magnetic field intensity
(b) The magnetization vector
___
Sol)
(a)
Note that the magnetic field intensity $\mathbf{H} = \frac{\mathbf{B}}{\mu}$.
$$
\begin{align}
\mathbf{H} &= \frac{\mathbf{B}}{\mu} \\
&=\frac{10}{4.6\mu_{0}\times 10^{3}}e^{-y}\mathbf{a}_{z}[\text{A/m}]  \\
&= \frac{1}{460\mu_{0}}e^{-y}\mathbf{a}_{z}[\text{A/m}] \\
&\approx 1730 e^{-y}\mathbf{a}_{z}[\text{A/m}]
\end{align}
$$
(b)
Note that the relative permiability is $4.6$, so, the magnetic susceptibility $\chi_{m} = 3.6$.
Therefore,
$$
\begin{align}
\mathbf{M} &= \frac{\chi_{m}}{1+\chi_{m}} \frac{\mathbf{B}}{\mu _{0}} \\
&= \frac{9}{1150\mu_{0}}e^{-y}\mathbf{a}_{z}[\text{A/m}] \\
&\approx 6228 e^{-y} \mathbf{a}_{z}[\text{A/m}]
\end{align}
$$

___
