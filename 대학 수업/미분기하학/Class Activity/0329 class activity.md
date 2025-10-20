___

**EXERCISE 1**)
$$\mathbf{\beta}(s) = \left( \frac{4}{5} \cos s, 1- \sin s , -\frac{3}{5} \cos s\right)$$
Show that the following curve is a circle.

___

**Sol**)
Recall that If $\beta(s)$ is a unit speed curve, $\kappa (s) > 0$ be constant and $\tau(s) = 0$, then $\beta(s)$ is a circle.
We want to show that $\beta(s)$ is a circle using this theorem.

First, we need to check that $\beta(s)$ is a unit speed curve.
So, compute $\beta'(s)$.
$$\beta'(s) = \left(-\frac{4}{5}\sin s, -\cos s, \frac{3}{5}\sin s\right)$$

$$\begin{align}||\beta'(s)|| = \sqrt{\frac{16}{25}\sin^2s + \cos^2 s + \frac{9}{25}\sin^2s }\\=\sqrt{\cos^2s + \sin^2s} = 1 \end{align}$$
Therefore, $\beta(s)$ has unit speed, So, $\beta'(s) = \mathbf{T}(s)$.

Second, we need to check that $\kappa(s)$ is larger than $0$ and constant.
Recall that $\kappa(s) = ||\mathbf{T}'(s)||$.
$$\mathbf{T}'(s) = \left(-\frac{4}{5}\cos s, \sin s, \frac{3}{5}\cos s\right)$$$$||\mathbf{T}'(s)|| = \sqrt{\frac{16}{25}\cos ^2 s + \sin^2s + \frac{9}{25}\cos^2s} =\sqrt{\cos^2s + \sin^2s} = 1(\textrm{constant}) > 0$$

Third, we need to check $\tau(s) = 0$.
Recall that $\tau(s) = -{<}\mathbf{B}'(s), \mathbf{N}(s){>}$, $\mathbf{N}(s) = \frac{\mathbf{T}'(s)}{\kappa(s)}$, $\mathbf{B}(s) = \mathbf{T}(s) \times \mathbf{N}(s)$.
So, $$\mathbf{N}(s) = \frac{\mathbf{T}'(s)}{1} = \left(-\frac{4}{5}\cos s, \sin s, \frac{3}{5}\cos s\right)$$
$$\begin{align} \mathbf{B}(s) = \left(-\frac{4}{5}\sin s, -\cos s, \frac{3}{5}\sin s\right)\times\left(-\frac{4}{5}\cos s, \sin s, \frac{3}{5}\cos s\right) \\ =\left(-\frac{3}{5}\cos^2 s -\frac{3}{5}\sin^2 s, \frac{12}{25}\sin s \cos s - \frac{12}{25}\sin s \cos s, -\frac{4}{5}\sin^2s -\frac{4}{5}\cos^2s\right) \\ =\left(-\frac{3}{5}, 0, -\frac{4}{5}\right)\end{align}$$
$$\mathbf{B}'(s) = (0, 0, 0)$$
Therefore, $\tau(s) = 0$.

___

**EXERCISE 2**)
$$\mathbf{\gamma}(s) = \left( \frac{\cos^{-1}s - s\sqrt{1-s^2}}{2}, \frac{1-s^2}{2} , 0 \right)$$
Find the $\mathbf{T}, \mathbf{N}, \mathbf{B}, \kappa$ and $\tau$.

___

**Sol**)
First, we need to check $\gamma(s)$ is a unit speed curve.
$$\gamma'(s) = \left(-\frac{1}{2\sqrt{1-s^2}}-\frac{\sqrt{1-s^2}}{2}+\frac{s^2}{2\sqrt{1-s^2}},-s,0\right)$$
$$= \left(\frac{-2+2s^2}{2\sqrt{1-s^2}},-s,0\right) = \left(-\sqrt{1-s^2},-s,0\right)$$
$$||\gamma'(s)|| = \sqrt{1-s^2 + s^2} = 1$$
Therefore, $\gamma(s)$ is a unit speed curve, so, $\mathbf{T}(s) = \gamma'(s)$.
$$\mathbf{T}(s) = \gamma'(s) = \left(-\sqrt{1-s^2},-s,0\right)$$
$$\mathbf{T}'(s) = \left(\frac{s}{\sqrt{1-s^2}}, -1, 0\right)$$
$$\kappa(s) = ||\mathbf{T}'(s)|| = \sqrt{\frac{s^2}{1-s^2}+1} = \frac{1}{\sqrt{1-s^2}}$$
$$\mathbf{N}(s) = \frac{\mathbf{T}'(s)}{||\mathbf{T}'(s)||} = \left(s, -\sqrt{1-s^2}, 0\right)$$
$$\begin{align}\mathbf{B}(s) = \mathbf{T}(s) \times \mathbf{N}(s) = \left(-\sqrt{1-s^2},-s,0\right) \times \left(s, -\sqrt{1-s^2}, 0\right)\\=\left(0, 0, 1-s^2+s^2\right)=(0, 0, 1)\end{align}$$
$$\mathbf{B}'(s) = (0, 0, 0) ; \tau(s) = -{<}\mathbf{B}'(s), \mathbf{N}(s){>} = 0$$

___