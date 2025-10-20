___
$$\beta(s) = \left(a \cos (\frac{s}{c}), a \sin(\frac{s}{c}), b(\frac{s}{c})\right)$$ where $a>0, b>0$ and $c = \sqrt{a^2 + b^2}$.
Compute $\kappa_{\gamma_\beta}(s)$ in two ways and compare them.
___
For convenience, let $\gamma_\beta(s) = \gamma(s)$.
$$
\beta'(s) = \mathbf{T}(s) = \gamma(s)
= \left(-\frac{a}{c}\sin(\frac{s}{c}), \frac{a}{c}\cos(\frac{s}{c}), \frac{b}{c}\right)
$$
$$||\gamma(s)|| = \frac{1}{c}\cdot \sqrt{a^2+b^2} = 1$$
So, $\gamma$ is spherical curve and $\beta$ is a unit speed curve.
$$
\gamma'(s)
= \left(-\frac{a}{c^2}\cos(\frac{s}{c}), -\frac{a}{c^2}\sin(\frac{s}{c}), 0\right)
$$
Since $||\gamma'|| = \frac{a}{c^2} = \frac{a}{a^2 + b^2} \leq 1$, so, $\gamma$ is not unit speed curve.
___
First, we want to compute curvature of $\gamma(s)$ using $\frac{||\gamma'(s) \times \gamma''(s)||}{||\gamma'(s)||^3}$.
$$\begin{align}
\gamma'(s)
&= \left(-\frac{a}{c^2}\cos(\frac{s}{c}), -\frac{a}{c^2}\sin(\frac{s}{c}), 0\right)\\
\gamma''(s)
&= \left(\frac{a}{c^3}\sin(\frac{s}{c}), -\frac{a}{c^3}\cos(\frac{s}{c}), 0\right)\\
\gamma' \times \gamma'' &= \left(0, 0, \frac{a^2}{c^5}\right)\\
||\gamma' \times \gamma''|| &= \frac{a^2}{c^5}\\
||\gamma'||^3 &= \frac{a^3}{c^6}\\
\textcolor{red}{\kappa_\gamma(s)}
&= \frac{||\gamma'\times\gamma''||}{||\gamma'||^3} =\frac{c}{a} = \textcolor{red}{\frac{\sqrt{a^2 + b^2}}{a}}
\end{align}$$
___
Second, recall that if $\beta(s)$ is unit speed curve and $\gamma(s) = \mathbf{T}(s)$, then $$\kappa_\gamma(s) = \sqrt{1+\left(\frac{\tau(s)}{\kappa(s)}\right)^2}$$
___
$$\kappa(s) = ||\mathbf{T}'(s)|| = ||\gamma'(s)|| = \frac{a}{c^2}$$
$$\begin{align}
\mathbf{T}(s) = \gamma(s)
&= \left(-\frac{a}{c}\sin(\frac{s}{c}), \frac{a}{c}\cos(\frac{s}{c}), \frac{b}{c}\right)\\
\mathbf{N}(s) = \frac{\mathbf{T}'(s)}{\kappa(s)}
&= \left(-\cos(\frac{s}{c}),-\sin(\frac{s}{c}), 0\right)\\
\mathbf{B}(s) = \mathbf{T}(s)\times\mathbf{N}(s)
&= \left(\frac{b}{c}\sin(\frac{s}{c}), -\frac{b}{c}\cos(\frac{s}{c}), \frac{a}{c}\right)\\
\mathbf{B}'(s)
&= \left(\frac{b}{c^2}\cos(\frac{s}{c}), \frac{b}{c^2}\sin(\frac{s}{c}), 0\right)\\
\tau(s) = -{<}\mathbf{B}'(s), \mathbf{N}(s){>} &= \frac{b}{c^2}
\end{align}$$
$$\begin{align}
\textcolor{red}{\kappa_\gamma(s)}
&= \sqrt{1+\left(\frac{\tau(s)}{\kappa(s)}\right)^2}\\
&= \sqrt{1+\frac{b^2}{a^2}} = \textcolor{red}{\frac{\sqrt{a^2+b^2}}{a}}
\end{align}$$
