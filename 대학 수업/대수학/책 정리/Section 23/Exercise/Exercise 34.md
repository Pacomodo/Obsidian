___

Show that for $p$ a prime, the polynomial $x^p+a \in \mathbb{Z}_p[x]$ is not irreducible for any $a \in \mathbb{Z}_p$.

___

**SOL**)

If $a = 0$, it is obvious that $x^p \in \mathbb{Z}_p[x]$ is reducible over $\mathbb{Z}_p$.
Suppose $a \neq 0$.
We already know that $\mathbb{Z}_p$ is a field, so, there exist the multiplicative inverse of $a$ for any $a \in \mathbb{Z}_p - \{0\}$. Call it $b$.
Consider the evaluation homomorphism $\phi_b : \mathbb{Z}_p[x] \rightarrow \mathbb{Z}_p$.
Consider $\phi_b(x^p + a)$.
If $p = 2$, $a = 1$ and $b = 1$. Thus, $1^2 + 1 = 0$, so, reducible.
If $p \neq 2$, then $p$ is odd. Thus, $b^p + a = b*b^{p-1} + a = b + a = 0$. so, reducible.

___
