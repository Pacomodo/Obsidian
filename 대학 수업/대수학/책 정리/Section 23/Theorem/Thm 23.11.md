___

**THEOREM**)
Let $f(x) \in \mathbb{Z}[x]$.
$f(x) = p(x)q(x)$ where $\deg (p(x)) = r, \deg(q(x)) = s$ ; $r, s < \deg(f(x))$ and $p(x), q(x) \in \mathbb{Q}[x]$ $\iff$ $f(x)$ has factorization with polynomials of the same degree $r, s$ in $\mathbb{Z}[x]$.

___

**PROOF**)
PROOF IS OMITTED.

___

**EXAMPLE**)

* Let us use Thm 23.11 to show that $f(x) = x^4 - 2x^2 + 8x + 1$ is irreducible over $\mathbb{Q}$. ^2ba97b

By [[Cor 23.12]], If $f(x)$ has a linear factor in $\mathbb{Q}[x]$, then it has a zero in $\mathbb{Z}$.
This zero have to be a divisor in $\mathbb{Z}$ of $1$.
But, $f(1) = 8, f(-1) = -8$, so, such factorization is impossible.

If $f(x)$ factors into two quadratic factors in $\mathbb{Q}[x]$, $f(x)$ has factorization $$f(x) = (x^2 +ax+b)(x^2+cx+d)$$in $\mathbb{Z}[x]$.
So, $bd = 1$, $ad + bc = 8$, $ac + b + d = -2$, $a+c = 0$ where $a,b,c,d \in \mathbb{Z}$.
By $bd = 1$, $b = d = 1$ or $b = d = -1$.
$ad + bc = d(a+c) = 8$ but, it is impossible since $a+c = 0$.
Hence, $f(x)$ is irreducible over $\mathbb{Q}$.

___
