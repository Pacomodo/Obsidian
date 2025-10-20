___

**THEOREM**)
Let $F$ be a [[Field|field]] and let $p(x) \in F[x]$ be a nonzero polynomial.
$\left< p(x) \right>$ is a [[Maximal ideal|maximal ideal]] $\Leftrightarrow$ $p(x)$ is [[Irreducible polynomial|irreducible]] over $F$.

___

**PROOF**)
$(\Rightarrow)$ Suppose $\left< p(x) \right>$ is a maximal ideal. Then, $\left< p(x) \right> \neq F[x]$, $p(x)$ is nonconstant polynomial.
Let $p(x) = f(x)g(x)$ be a factorization of $p(x) \in F[x]$.
Since $\left< p(x) \right>$ is [[Maximal ideal|maximal]], so, it is [[Prime ideal|prime ideal]] by [[Cor 27.16]], so, $f(x)g(x) \in \left< p(x) \right>$ $\rightarrow$ $f(x) \in \left< p(x) \right>$ or $g(x) \in \left< p(x) \right>$. So, we can't have the degrees of both $f(x)$ and $g(x)$ less than the degree of $p(x)$. Therefore, $p(x)$ is irreducible over $F$.

$(\Leftarrow)$ Suppose $p(x)$ is irreducible over $F$.
Suppose that $N$ is an ideal such that $\left< p(x) \right> \subseteq N \subseteq F[x]$.
By [[Thm 27.24]], $N$ is [[Principal ideal|principal ideal]], so, $N = \left< g(x) \right>$ for some $g(x) \in F[x]$.
Since $p(x) \in \left< p(x) \right>$, $p(x) = g(x)q(x)$ for some $q(x) \in F[x]$.
Because $p(x)$ is irreducible, either $g(x)$ or $q(x)$ has degree $0$.
If $deg(g(x)) = 0$, $N = F[x]$. If $deg(g(x)) \neq 0$, then, $q(x)$ is constant, so, $N = \left< g(x) \right> = \left< p(x) \right>$.
Therefore, $\left< p(x) \right>$ is a maximal ideal.

___

**EXAMPLE**)

* Consider $x^3 + 3x + 2 \in \mathbb{Z}_5 [x]$. 
By [[Thm 23.10]], since this polynomial has no zero in $\mathbb{Z}_5$, this polynomial is irreducible over $\mathbb{Z}_5$.
Hence, $\left< x^3 + 3x + 2 \right> \in \mathbb{Z}_5 [x]$ is maximal ideal in $\mathbb{Z}_5 [x]$. By [[Thm 27.9]], $\mathbb{Z}_5 [x] / \left< x^3 + 3x +2 \right>$ is a [[Field|field]].

* Consider $x^2 - 2 \in \mathbb{Q}[x]$.
Similarly, $\mathbb{Q}[x] / \left< x^2 - 2 \right>$ is a field.

___
