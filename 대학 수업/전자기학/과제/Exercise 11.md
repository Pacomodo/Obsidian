___
###### Problem 1
The constitutive parameters are $\varepsilon_{r}=3.2, \sigma = 1.5\times 10^{-4}$, and $\mu_{r}=1$. Find
(a) attenuation constant
(b) phase constant
(c) intrinsic impedance
(d) loss tangent
at $3 \text{ MHz}$.
___
Sol)
Note that when constitutive parameters $(\sigma, \varepsilon, \mu)$ is given, we can find $\alpha, \beta, \eta, \dots$.
Note that constitutive parameters $(\sigma, \varepsilon, \mu)=(1.5\times 10^{-4}, 3.2\varepsilon_{0}, \mu_{0})$. Also, note that linear frequency $f = 3\text{ MHz}$, so, the radian frequency $\omega=6\pi \times 10^{6}\text{Hz}$.
(a), (b)
So, the propagation constant $\gamma$ is
$$
\begin{align}
\gamma &= \sqrt{ j\cdot 6\pi \cdot 10^{6} \cdot \mu_{0} \cdot(1.5\cdot 10^{-4}+j\cdot6\pi \cdot 10^{6}\cdot 3.2\cdot \varepsilon_{0}) } \\
&=\sqrt{ -36\pi^{2}\cdot 10^{12}\cdot 3.2\mu_{0}\varepsilon_{0} + j(9\pi \cdot 10^{2}\cdot \mu_{0}) } \\
\xrightarrow{\varepsilon_{0}=8.854\times 10^{-12}, \mu_{0}=4\pi \times 10^{-7}} &= \sqrt{ -144\pi^{3}\cdot 3.2 \cdot 8.854\cdot 10^{-7}+j(36\pi^{2}\cdot 10^{-5}) } \\
&\approx \sqrt{ -0.01265+j(0.00355) } \\
&\approx 0.0156 +0.1136j=\alpha+\beta j
\end{align}
$$
Therefore, $\alpha \approx 0.0156, \beta \approx 0.1136$.
(c)
Intrinsic impedance $\eta$ is
$$
\begin{align}
\eta &= \sqrt{ \frac{j\omega \mu}{\sigma+j\omega\varepsilon} } \\
&=\sqrt{ \frac{j(24\pi^{2}\times 10^{-1})}{1.5\times 10^{-4}+j(3.2\times 8.854\times 6\pi \times 10^{-6})} ) } \\
&\approx 204.71 + 28.20j
\end{align}
$$
(d)
Loss tangent is
$$
\begin{align}
\frac{\sigma}{\omega\varepsilon}&= \frac{1.5\times 10^{-4}}{6\pi \times 10^{6}\times 3.2\times 8.854 \times 10^{-12}} \\
&=\frac{10^{2}}{4\pi \times 3.2 \times 8.854} \\
&\approx 0.281
\end{align}
$$
___
###### Problem 2
The electric field of a uniform plane wave propagating in a perfect dielectric medium $(\sigma = 0, \mu=\mu_{0})$ is given by $\mathbf{E} = 10\cos(3\pi \times 10^{7}t-0.2\pi x)\mathbf{a}_{z}$. Find
(a) the frequency
(b) the wavelength
(c) the phase velocity
(d) the relative permittivity of the medium
(e) the associated magnetic-field vector $\mathbf{H}$
___
Sol)
Note that $\omega=3\pi \times 10^{7}, \beta=0.2\pi$. Propagating direction is $+x$ direction, So, direction of $\mathbf{H}$ is $-y$ direction.
(a) The frequency $f = \omega / 2\pi = 15[\text{MHz}]$.
(b) The wavelength $\lambda = 2\pi / \beta = 10[\text{m}]$
(c) The phase velocity $v_{p}=\omega / \beta = 1.5 \times 10^{8}[\text{m/s}]$
(d) The relative permittivity of the medium
$$
\varepsilon_{r} = \left( \frac{c}{v_{p}} \right)^{2}\approx 4
$$
(e) Note that $\eta = \eta_{0}\sqrt{ \frac{\mu _{r}}{\varepsilon_{r}} }=\frac{\eta_{0}}{2}\rightarrow\tau=0$.
$$
\mathbf{H} = -\frac{20}{\eta_{0}}\cos(3\pi \times 10^{7}-0.2\pi x)\mathbf{a}_{y}
$$
___
###### Problem 3
The electric field of a uniform plane wave propagating in the $+z$ direction in a medium with $\mu=\mu_{0}$ is given by $$\mathbf{E}=8.4e^{-0.0432z}\cos(4\pi \times 10^{6}t -0.1829z)\mathbf{a}_{x}$$ Find the magnetic field intensity of the wave.
___
Sol)
Note that $\alpha = 0.0432, \beta=0.1829, \omega=4\pi \times 10^{6}$. Propagating direction is $+z$ direction and $\mathbf{E}$ is $+x$ direction. So, $\mathbf{H}$ is $+y$ direction.
We need to find $\lvert \eta \rvert$ and $\tau$
$$
\begin{align}
\eta &= \frac{j\omega \mu}{\gamma} \\
&= \frac{(16\pi^{2} \times 10^{-1})j}{0.0432 + 0.1829j} \\
&= \frac{16\pi^{2}j}{0.432+1.829j} \\
\Rightarrow \lvert \eta \rvert &= \left\lvert  \frac{16\pi^{2}j}{0.432+1.829j}  \right\rvert \approx 84 \\
\Rightarrow \tau  &= 0.232
\end{align}
$$
Therefore, the magnetic field intensity $\mathbf{H}$ is
$$
\mathbf{H} = 0.1e^{-0.0432z}\cos(4\pi \times 10^{6}t-0.1829z-0.232)\mathbf{a}_{y}
$$
___
