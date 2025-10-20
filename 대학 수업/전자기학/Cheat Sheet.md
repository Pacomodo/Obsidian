###### Differential length, surface, volume
$$
\begin{align}
d\mathbf{l} &= d\rho \mathbf{a}_{\rho}+\rho d\phi \mathbf{a}_{\phi}+dz\mathbf{a}_{z} \\
d\mathbf{l} &= dr\mathbf{a}_{r}+r d\theta \mathbf{a}_{\theta}+r\sin \theta d\phi \mathbf{a}_{\phi}
\end{align}
$$
###### Useful integrals
$$
\int \frac{1}{(a^{2}+x^{2})^{3/2}} \, dx =\frac{x}{a^{2}\sqrt{ a^{2}+x^{2} }}
$$
###### Conversion between coordinates
$$
\begin{align}
P(x, y, z) &\rightarrow P\left( \sqrt{ x^{2} +y^{2}}, \tan ^{-1}\left( \frac{y}{x} \right), z \right) \\
P(\rho, \phi, z) &\rightarrow P(\rho \cos \phi , \rho \sin \phi, z) \\
\end{align}
$$
$$
x=r\sin \theta \cos \phi, y=r\sin \theta \sin \phi, z=r\cos \theta
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
###### Columb's Law
$$
\mathbf{F}_{1} = \frac{Q_{1}Q_{2}}{4\pi \varepsilon_{0}R^{2}}\mathbf{a}_{21}
$$
전하 $Q_{1}$이 받는 힘 $\mathbf{F}_{1}$의 방향은 $Q_{2}$에서 $Q_{1}$으로 향하는 반직선.
$$
\varepsilon_{0} = 8.854\times 10^{-12}\left[ \frac{C^{2}}{N\cdot m^{2}} =\frac{F}{m}\right]
$$
###### Electric Field Intensity
$\mathbf{E} = \frac{\mathbf{F}}{q}\left[ \frac{N}{C}=\frac{N\cdot m}{C\cdot m}=\frac{V}{m}\right]\rightarrow \mathbf{F} = q\mathbf{E}$
###### $\mathbf{E}$ due to two charges
$+q$ at $\left( 0, 0, \frac{d}{2} \right)$, $-q$ at $\left( 0, 0, -\frac{d}{2} \right)$.
###### $\mathbf{E}$ due to an infinitely long line charge
$$
\mathbf{E}=\frac{\rho_{L_{0}}}{2\pi \varepsilon_{0}\rho}\mathbf{a}_{\rho}
$$
###### $\mathbf{E}$ due to an infinitely long surface charge on $yz$ plane
$$
\mathbf{E} = \frac{\rho_{S_{0}}}{2\varepsilon_{0}}\mathbf{a}_{n}
$$
###### Magnetic field
$$
d\mathbf{F}_{1} = I_{1}d\mathbf{l}_{1}\times \boxed{ \frac{\mu_{0}}{4\pi} \frac{I_{2}d\mathbf{l}_{2}\times \mathbf{a}_{21}}{R^{2}} }\to \mathbf{B}_{2}
$$
$$
\mathbf{B} = \frac{\mu_{0}}{4\pi} \frac{Id\mathbf{l}\times \mathbf{a}_{R}}{R^{2}}
$$

###### $\mathbf{B}$ due to a infinitely long line current
$$
\mathbf{B} = \frac{\mu_{0}I}{2\pi \rho}\mathbf{a}_{\phi}
$$
###### $\mathbf{B}$ due to a infinite sheet
$$
\mathbf{B} = \frac{\mu_{0}\mathbf{J}_{s}\times \mathbf{a}_{n}}{2}
$$
###### Lorents Force
$$
\mathbf{F} = q\mathbf{E} + q\mathbf{v}\times \mathbf{B}
$$
###### Work done in charge
$$
W=qV, V = \int \mathbf{E}\cdot d\mathbf{l} 
$$
###### Conservative, Nonconservative
$$
\oint\mathbf{F}\cdot d\mathbf{l} = 0
$$
Conservative $\Leftrightarrow$ Path independent.
###### Faraday's Law
EMF around the closed path is equal to the time rate of decrease of the magnetic flux crossing the surface enclosed by the closed path.
$$
\oint_{C}\mathbf{E}\cdot d\mathbf{l} = -\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} 
$$
###### Gauss' law for the Electric field
The total electric flux emanating from a closed surface $S$ is equal to the total charge contained in the volume bounded by the closed surface $S$.
$$
\oint_{S} \mathbf{D}\cdot d\mathbf{S} = [Q]_{V} = \int _{V}\rho \, dV
$$
###### Gauss' law for the Magnetic field
The total magnetic flux emanating from a closed surface is equal to zero.
$$
\oint_{S}\mathbf{B}\cdot d\mathbf{S} = 0
$$
###### Ampere's circuit law
The circulation of the magnetic field intensity vector $\mathbf{H}$ around a closed path $C$ is equal to 
the total currents crossing the surface enclosed by the closed path $C$.
$$
\oint_{C}\mathbf{H}\cdot d\mathbf{l} = [I]_{S} = \int _{S}\mathbf{J}\cdot d\mathbf{S} + \frac{d}{dt} \int _{S}\mathbf{D}\cdot d\mathbf{S}  
$$
###### Law of conservation of Charge
The net current due to flow of charges emanating from a closed surface $S$ is equal to the time rate of decrease of the charge within the volume $V$ bounded by $S$.
$$
\oint_{S}\mathbf{J}\cdot d\mathbf{S}=-\frac{d}{dt} \int _{V}\rho \, dV 
$$
###### Divergence theorem
$$
\oint_{S} \mathbf{F}\cdot d\mathbf{S} = \iiint_{V} \nabla \cdot \mathbf{F}dV
$$
미분 가능해야 함.
$$
\nabla \cdot \mathbf{F} = \frac{1}{r^2}\frac{\partial}{\partial r} r^2 F_r +  \frac{1}{r \sin \theta} \frac{\partial}{\partial \theta} \sin \theta F_\theta + \frac{1}{r \sin \theta} \frac{\partial}{\partial \phi} F_\phi
$$
$$
\nabla \cdot \mathbf{F} = \frac{1}{\rho}\frac{\partial}{\partial \rho} \rho F_\rho +  \frac{1}{\rho} \frac{\partial}{\partial \phi} F_\phi + \frac{\partial}{\partial z} F_z
$$
###### Stokes Theorem and curl
$$
\oint_{C}\mathbf{F}\cdot d\mathbf{l} = \int _{S}(\nabla \times \mathbf{F})\cdot d\mathbf{S} 
$$
$$
\nabla \times \mathbf{E} = \begin{vmatrix}
\frac{\mathbf{a}_{\rho}}{\rho} & \mathbf{a}_{\phi} & \frac{\mathbf{a}_{z}}{\rho} \\
\frac{ \partial  }{ \partial \rho }  & \frac{ \partial  }{ \partial \phi }  & \frac{ \partial  }{ \partial z }  \\
E_{\rho} & \rho E_{\phi} & E_{z}
\end{vmatrix}
$$
$$
\nabla \times \mathbf{E} = \begin{vmatrix}
\frac{\mathbf{a}_{r}}{r^{2}\sin \theta} & \frac{\mathbf{a}_{\theta}}{r\sin \theta} & \frac{\mathbf{a}_{\phi}}{r} \\
\frac{ \partial  }{ \partial r }  & \frac{ \partial  }{ \partial \theta }  & \frac{ \partial  }{ \partial \phi }  \\
E_{r} & rE_{\theta} & r\sin \theta E_{\phi}
\end{vmatrix}
$$
###### Point form of Maxwell Equation
$$
\begin{align}
\nabla \times \mathbf{E} &= -\frac{ \partial \mathbf{B} }{ \partial t } \\
\nabla \times \mathbf{H} &= \mathbf{J} + \frac{ \partial \mathbf{D} }{ \partial t } \\
\nabla \cdot \mathbf{D} &= \rho_{v} \\
\nabla \cdot \mathbf{B} &= 0 \\
\nabla \cdot \mathbf{J} &= -\frac{ \partial \rho_{v} }{ \partial t } 
\end{align}
$$
###### Uniform plane wave in free space
Go to [[Uniform plane wave in free space]].
$$
\begin{align}
\mathbf{E}(z, t) &= \begin{cases}
\frac{\eta_{0}}{2}J_{s}\left( t-\frac{z}{v_{p}} \right)\mathbf{a}_{x} & \text{ for }z>0 \\
\frac{\eta_{0}}{2}J_{s}\left( t+\frac{z}{v_{p}} \right)\mathbf{a}_{x} & \text{ for }z<0 \\
\end{cases} \\
\mathbf{H}(z, t) &= \begin{cases}
\frac{1}{2}J_{s}\left( t-\frac{z}{v_{p}} \right)\mathbf{a}_{y} & \text{ for }z>0 \\
-\frac{1}{2}J_{s}\left( t+\frac{z}{v_{p}} \right)\mathbf{a}_{y} & \text{ for }z<0 \\
\end{cases}
\end{align}
$$
Electromagnatic field due to the surface current $\mathbf{J}_{s}(t) = -J_{s}(t)\mathbf{a}_{x}$ on the infinite sheet in the $xy$-plane. ($z=0$)
###### Sinusoidal time-varying uniform plane wave
The electromagnetic field due to the surface current $\mathbf{J}_{s}(t) = -J_{s_{0}}\cos \omega t\mathbf{a}_{x}$.
$$
\begin{align}
\mathbf{E}(z, t) &= \begin{cases}
\frac{\eta_{0}J_{s_{0}}}{2}\cos\left( \omega t-\beta z \right)\mathbf{a}_{x} & \text{ for }z>0 \\
\frac{\eta_{0}J_{s_{0}}}{2}\cos\left( \omega t+\beta z \right)\mathbf{a}_{x} & \text{ for }z<0 \\
\end{cases} \\
\mathbf{H}(z, t) &= \begin{cases}
\frac{J_{s_{0}}}{2}\cos\left( \omega t- \beta z \right)\mathbf{a}_{y} & \text{ for }z>0 \\
-\frac{J_{s_{0}}}{2}\cos\left( \omega t+\beta z \right)\mathbf{a}_{y} & \text{ for }z<0 \\
\end{cases}
\end{align}
$$
where $\beta = \omega / v_{p}$.
###### Parameters to note
1. Argument $\phi = \omega t \mp \beta z$ is the **phase** of the fields.
2. $\frac{ \partial \phi }{ \partial t } = \omega$ is **radian frequency**.
3. $f = \frac{\omega}{2\pi}$ is **linear frequency**, which is the number of times the phase changes by $2\pi \text{ rad}$ in one second for a fixed $z$.
4. $\left\lvert  \frac{ \partial \phi }{ \partial t }  \right\rvert=\beta$ is **phase constant**, the magnitude of the rate of change of phase with $z$ for a fixed $t$.
5. $\lambda = \frac{2\pi}{\beta}$ is **wave length**, the distance of the phase changes by $2\pi \text{ rad}$ for a fixed $t$.
6. $v_{p}=\frac{\omega}{\beta}$ is **phase velocity**, which is constant in free space.($\approx 3\times 10^{8} \text{ m/s}$)
7. $\lambda f = \frac{\omega}{\beta} = v_{p}$.
8. $\eta_{0} = \frac{\lvert \mathbf{E} \rvert}{\lvert \mathbf{H} \rvert}$ is **intrinsic impedence**, $\approx 377\Omega$ in free space.
9. $\mathbf{S} = \mathbf{E}\times \mathbf{H}$ is **Poynting vector**, and they follow right-hand rule. Unit is $\text{W/m}^{2}$, which means instantaneous power density. Average power flow over $1$ period is $\left< S_{z}\right> = \frac{\eta_{0}J_{s_{0}}^{2}}{8}$.
###### Conductor, Dielectrics, Magnetics(Constitutive Parameters)
$\varepsilon_{0} = 8.854\times 10^{-12}[\text{F/m}], \mu_{0} = 4\pi \times 10^{-7} [\text{H/m}]$
$\mathbf{J}_{c} = \sigma \mathbf{E}$ (Ohm's law in point form), $\sigma$ is **conductivity**.
$\mathbf{P} = \varepsilon_{0}\chi_{e}\mathbf{E}[\text{C/m}^{2}]$ // $\chi_{e}$ is **electric susceptibility**. // $\varepsilon_{r}$ is **relative permittivity** or **dielectric constant**. // $\varepsilon$ is **permittivity**.
$$
\begin{align}
\mathbf{D} &= \varepsilon_{0}\mathbf{E}+\mathbf{P} \\
&=\varepsilon_{0}(1+\chi_{e})\mathbf{E} \\
&= \varepsilon_{0}\varepsilon_{r}\mathbf{E} \\
&=\varepsilon \mathbf{E}
\end{align}
$$
$\mathbf{M} = \frac{\chi_{m}}{1+\chi_{m}} \frac{\mathbf{B}}{\mu_{0}}[\text{A/m}]$ // $\chi_{m}$ is **magnetic susceptibility**. // $\mu_{r}$ is **relative permeability** // $\mu$ is **permeability**.
$$
\begin{align}
\mathbf{H} &= \frac{\mathbf{B}}{\mu_{0}} - \mathbf{M} \\
&= \frac{\mathbf{B}}{\mu_{0}(1+\chi_{m})} \\
&=\frac{\mathbf{B}}{\mu_{0}\mu_{r}} \\
&=\frac{\mathbf{B}}{\mu}
\end{align}
$$
$$
\oint_{C} \mathbf{H}\cdot d\mathbf{l} = \int _{S}\mathbf{J}\cdot d\mathbf{S} + \frac{d}{dt} \int _{S} \mathbf{D}\cdot d\mathbf{S}  
$$
###### Wave in arbitrary material
$$
\begin{align}
\mathbf{E}(z, t) &= \left\{ \begin{aligned}
&\frac{\lvert \eta \rvert J_{S_{0}}}{2} e^{-\alpha z}\cos(\omega t-\beta z+\tau)\mathbf{a}_{x} &\text{for }z>0 \\
&\frac{\lvert \eta \rvert J_{S_{0}}}{2} e^{\alpha z}\cos(\omega t+\beta z+\tau)\mathbf{a}_{x}  &\text{for }z<0
\end{aligned}\right. \\
\mathbf{H}(z, t) &= \left\{\begin{aligned}
\frac{J_{S_{0}}}{2} e^{-\alpha z}\cos(\omega t-\beta z)\mathbf{a}_{y} \ \ \ \ \text{for }z>0 \\
-\frac{J_{S_{0}}}{2}  e^{\alpha z}\cos(\omega t+\beta z)\mathbf{a}_{y} \ \ \ \ \text{for }z<0
\end{aligned}\right.
\end{align}
$$
Surface current density $\mathbf{J}_{s}(t) = -J_{S_{0}}\cos \omega t\mathbf{a}_{x}$ for $z = 0$.
Go to [[Wave in arbitrary material]]. $\eta = \lvert \eta \rvert e^{j\tau}$
###### Constants relations
* Constitutive Params + $\omega$ $\to$ Others

**Propagation constant**: $\gamma = \alpha+j\beta = \sqrt{ j\omega \mu(\sigma+j\omega\varepsilon) }$
**Intrinsic impedance**: $\eta = \sqrt{ \frac{j\omega \mu}{\sigma+j\omega\varepsilon} }$
**Attenuation constant**: $\alpha = \frac{\omega \sqrt{ \mu\varepsilon }}{\sqrt{ 2 }}\left[ \sqrt{ 1+\left( \frac{\sigma}{\omega \varepsilon} \right)^{2} }-1 \right]^{1/2}$
**Phase constant**: $\beta = \frac{\omega \sqrt{ \mu\varepsilon }}{\sqrt{ 2 }}\left[ \sqrt{ 1+\left( \frac{\sigma}{\omega \varepsilon} \right)^{2} }+1 \right]^{1/2}$
**Loss tangent**: $\frac{\sigma}{\omega\varepsilon}$
Recall: $\nabla \times \tilde{\mathbf{H}} = \sigma \tilde{\mathbf{E}} + \varepsilon j\omega \tilde{\mathbf{E}}$
Note that loss tangent means the ratio of $\lvert \text{Conduction current} \rvert$ to the $\lvert \text{Displacement current} \rvert$.
Loss tangent high $\to$ Conduction current is high.
**Phase velocity**: $v_{p} = \frac{\omega}{\beta} = \frac{\sqrt{ 2 }}{\sqrt{ \mu\varepsilon }}\left[ \sqrt{ 1+\left( \frac{\sigma}{\omega \varepsilon} \right)^{2} }+1 \right]^{-1/2}$
**Wave length**: $\lambda = \frac{2\pi}{\beta} = \frac{\sqrt{ 2 }}{f\sqrt{ \mu\varepsilon }}\left[ \sqrt{ 1+\left( \frac{\sigma}{\omega \varepsilon} \right)^{2} }+1 \right]^{-1/2}$
* $\gamma, \eta + \omega$ $\to$ $\sigma,\varepsilon, \mu$

$\mathrm{Re}\left( \frac{\gamma}{\eta} \right) = \sigma, \frac{1}{\omega}\mathrm{Im}\left( \frac{\gamma}{\eta} \right)=\varepsilon, \frac{\gamma \eta}{j\omega}=\mu$, Skin depth: $\delta=1/\alpha$.
###### Perfect, imperfect, good
**Perfect Dielectrics**: $\sigma=0$ (No attenuation, $\tau=0$)
$\gamma=j\omega \sqrt{ \mu\varepsilon }\to \alpha=0, \beta=\omega \sqrt{ \mu\varepsilon }=\omega \sqrt{ \mu_{0}\varepsilon_{0} }\sqrt{ \mu _{r}\varepsilon_{r} }=\beta_{0}\sqrt{ \mu _{r}\varepsilon_{r} }>\beta_{0}$
$v_{p}=\frac{\omega}{\beta}=\frac{1}{\sqrt{ \mu\varepsilon }}=\frac{c}{\sqrt{ \mu_{r}\varepsilon_{r} }}$
$\lambda=\frac{2\pi}{\beta}=\frac{1}{f\sqrt{ \mu\varepsilon }}=\frac{\lambda_{0}}{\sqrt{ \mu_{r}\varepsilon_{r} }}$
$\eta=\sqrt{ \frac{j\omega\mu}{j\omega\varepsilon} }=\sqrt{ \frac{\mu}{\varepsilon} }=\eta_{0}\sqrt{ \frac{\mu_{r}}{\varepsilon_{r}} }$
**Imperfect dielectrics**: $\sigma / \omega\varepsilon \ll 1$
$$
\begin{align}
\alpha &= \frac{\sigma}{2}\sqrt{ \frac{\mu}{\varepsilon} }\left( 1-\frac{\sigma^{2}}{8\omega^{2}\varepsilon^{2}} \right) \\
\beta &= \omega \sqrt{ \mu\varepsilon }\left( 1+\frac{\sigma^{2}}{8\omega^{2}\varepsilon^{2}} \right) \\
v_{p}&= \frac{\omega}{\beta} = \frac{1}{\sqrt{ \mu\varepsilon }}\left( 1-\frac{\sigma^{2}}{8\omega^{2}\varepsilon^{2}} \right) \\
\lambda&=\frac{2\pi}{\beta} = \frac{1}{f\sqrt{ \mu\varepsilon }}\left( 1-\frac{\sigma^{2}}{8\omega^{2}\varepsilon^{2}} \right)
\end{align}
$$
**Good conductor**: $\sigma / \omega\varepsilon \gg 1$(Conduction current is much larger than displacement current)
$$
\begin{align}
\gamma&=\sqrt{ j\omega \mu(\sigma+j\omega\varepsilon) }\approx \sqrt{ j\omega \mu \sigma }=\sqrt{ \omega \mu \sigma }\sqrt{ j } \\
&=\sqrt{ 2\pi f \mu \sigma } \frac{1}{\sqrt{ 2 }}(1+j)=\sqrt{ \pi f\mu \sigma }(1+j) \\
&\to \alpha=\beta=\sqrt{ \pi f\mu \sigma }
\end{align}
$$
$v_{p}=\frac{\omega}{\beta}=\frac{2\pi f}{\sqrt{ \pi f\mu \sigma }}=\sqrt{ \frac{4\pi f}{\mu \sigma} }$
$\lambda=\frac{2\pi}{\beta}=\frac{2\pi}{\sqrt{ \pi f\mu \sigma }}=\sqrt{ \frac{4\pi}{f\mu \sigma} }$
$\eta=\sqrt{ \frac{j\omega \mu}{\sigma+j\omega\varepsilon} }=\sqrt{ \frac{j\omega \mu}{\sigma} }=\sqrt{ \frac{\pi f\mu}{\sigma} }(1+j)$
In conductor, $\delta = 1 / \sqrt{ \pi f\mu \sigma }$
**Perfect electric conductor(PEC)**: $\alpha=\infty\to \delta=0$. No electric field intensity inside.
###### Boundary Condition
$$
\begin{align}
\mathbf{a}_{n}\times(\mathbf{E}_{1}-\mathbf{E}_{2})&=0 \\
\mathbf{a}_{n}\times(\mathbf{H}_{1}-\mathbf{H}_{2})&=\mathbf{J}_{s} \\
\mathbf{a}_{n}\cdot (\mathbf{D}_{1}-\mathbf{D}_{2}) &= \rho_{s} \\
\mathbf{a}_{n}\cdot (\mathbf{B}_{1}-\mathbf{B}_{2})&=0
\end{align}
$$
where $\mathbf{a}_{n}$ is the unit normal vector directed to medium 1.
In Perfect Dielectrics, there is no conduction current and surface charges.($\mathbf{J}_{s}, \rho_{s} =0$)
If medium 2 is PEC, there is no electric field intensity and the others inside.($\mathbf{E}_{2}, \mathbf{H}_{2},\mathbf{D}_{2},\mathbf{B}_{2} =0$)
