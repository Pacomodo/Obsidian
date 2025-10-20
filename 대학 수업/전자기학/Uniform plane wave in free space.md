
![[Pasted image 20241128103035.png|center|200]]
Surface current density $\mathbf{J}_{s} = -J_{s}(t)\mathbf{a}_{x}$. Want to find $\mathbf{E}$ due to the current sheet. We use Faraday's law and Ampere's law. Note that it is infinite sheet in the $xy$-plane, so, field do not vary with $x$ and $y$. Also, note that $J_{y} = 0, J_{z} = 0$.
$$
\begin{align}
\nabla \times \mathbf{E} &= -\frac{ \partial \mathbf{B} }{ \partial t } \\
& \left( \cancel{ \frac{ \partial E_{z} }{ \partial y  }} -\frac{ \partial E_{y} }{ \partial z } \right) \mathbf{a}_{x} + \underbrace{ \left( \frac{ \partial E_{x} }{ \partial z } \cancel{ -\frac{ \partial E_{z} }{ \partial x }  } \right) }_{  }\mathbf{a}_{y}+\left( \cancel{ \frac{ \partial E_{y} }{ \partial x } } -\cancel{ \frac{ \partial E_{x} }{ \partial y }  } \right)\mathbf{a}_{z} \\
&= -\frac{ \partial B_{x} }{ \partial t } \mathbf{a}_{x} \underbrace{ - \frac{ \partial B_{y} }{ \partial t } }_{  }\mathbf{a}_{y} - \frac{ \partial B_{z} }{ \partial t } \mathbf{a}_{z}   \\
\nabla \times \mathbf{H} &= \mathbf{J} +\frac{ \partial \mathbf{D} }{ \partial t } \\
& \underbrace{ \left( \cancel{ \frac{ \partial H_{z} }{ \partial y  }} -\frac{ \partial H_{y} }{ \partial z } \right) }_{  }\mathbf{a}_{x} + \left( \frac{ \partial H_{x} }{ \partial z } \cancel{ -\frac{ \partial H_{z} }{ \partial x }  } \right)\mathbf{a}_{y}+\left( \cancel{ \frac{ \partial H_{y} }{ \partial x } } -\cancel{ \frac{ \partial H_{x} }{ \partial y }  } \right)\mathbf{a}_{z} \\
&= \underbrace{ \left(J_{x}+\frac{ \partial D_{x} }{ \partial t }\right) }_{  }\mathbf{a}_{x} + \left(\cancel{ J_{y} }+\frac{ \partial D_{y} }{ \partial t }\right)\mathbf{a}_{y} + \left(\cancel{ J_{z} } + \frac{ \partial D_{z} }{ \partial t }\right) \mathbf{a}_{z}   \\
\end{align}
$$
Only two of 6 equations are related to $J_{x}$. (Note that $J_{x}$ is related with $D_{x}$ and $H_{y}$, so that $E_{x}$ and $B_{y}$)
$$
\begin{align}
\frac{ \partial E_{x} }{ \partial z } &= -\frac{ \partial B_{y} }{ \partial t } \\
\frac{ \partial H_{y} }{ \partial z } &= -J_{x}-\frac{ \partial D_{x} }{ \partial t }   
\end{align}
$$
In free space on either side of the sheet, $J_{x} = 0$.
$$
\begin{align}
\frac{ \partial E_{x} }{ \partial z } &= -\frac{ \partial B_{y} }{ \partial t } = -\mu_{0} \frac{ \partial H_{y} }{ \partial t }  \\
\frac{ \partial H_{y} }{ \partial z } &= -\frac{ \partial D_{x} }{ \partial t } = -\varepsilon_{0} \frac{ \partial E_{x} }{ \partial t } \\
\rightarrow \frac{ \partial^{2} E_{x} }{ \partial z^{2} } &= -\mu_{0}\frac{ \partial H_{y} }{ \partial t \partial z } = \mu_{0}\varepsilon_{0}\frac{ \partial E_{x} }{ \partial t^{2} } \\
&\rightarrow \boxed{ \frac{ \partial^{2} E_{x} }{ \partial z^{2} } = \mu_{0}\varepsilon_{0}\frac{ \partial E_{x} }{ \partial t^{2} } \text{ (wave equation)}}
\end{align}
$$
