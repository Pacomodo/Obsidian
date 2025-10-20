___

**THEOREM**)
$p$th cyclotomic polynomial $$\Phi_p(x) = \frac{x^p - 1}{x-1} = x^{p-1} + x^{p-2} + \cdots+x+1$$is [[Irreducible polynomial|irreducible]] over $\mathbb{Q}$ for any **prime** $p$.

___

**PROOF**)
By [[Thm 23.11]], It is enough to consider the factorizations in $\mathbb{Z}[x]$.
Here, we want to use the [[Evaluation homomorphism|evaluation homomorphism]] and [[Thm 23.15|eisenstein criterion]] so that $\Phi_p(x)$ is irreducible over $\mathbb{Q}$ for any prime $p$.
Consider the evaluation homomorphism $\phi_{x+1} : \mathbb{Q}[x] \rightarrow \mathbb{Q}[x]$.
Let $$g(x) = \Phi_p(x+1) = \frac{(x+1)^p - 1}{(x+1)-1} = x^{p-1} + \binom{p}{1}x^{p-2}+\cdots+p$$Then, $p$ divides the coefficients of $x^{n}$ where $0 \leq n \leq p-2$ and $p^2$ does not divides the coefficient of $x^0$.
Thus, $g(x)$ is irreducible over $\mathbb{Q}$ by eisenstein criterion.
We know that if $\Phi_p(x) = h(x)r(x)$ were a nontrivial factorization of $\Phi_p(x) \in \mathbb{Z}[x]$, then, $\Phi_p(x+1) = g(x) = h(x+1)r(x+1)$ would give a nontrivial factorization of $g(x) \in \mathbb{Z}[x]$.
Hence, $\Phi_p(x)$ must also be irreducible over $\mathbb{Q}$.

___

