___

**THEOREM**) **(Fundamental Theorem of Algebra)**
The field $\mathbb{C}$ of complex numbers is an algebraically closed field.

___

**PROOF**)
Let the polynomial $f(z) \in \mathbb{C}[z]$ have no zero in $\mathbb{C}$.
Then $\frac{1}{f(z)}$ gives an entire function, that is, $1/f$ is analytic everywhere.
Also if $f \notin \mathbb{C}$, $\lim_{|z| \rightarrow \infty} |f(z)| = \infty$, so $\lim_{|z| \rightarrow \infty} |1/f(z)| = 0$.
Thus, $1/f$ must be bounded in the plane.
Hence by Liouville's theorem of complex function theory, $1/f$ is constant, and thus $f$ is constant.
Therefore, a nonconstant polynomial in $\mathbb{C}[z]$ must have a zero in $\mathbb{C}$, so, $\mathbb{C}$ is algebraically closed.

___
