___

**THEOREM**)
If $f(x) = x^n + a_{n-1}x^{n-1} + \cdots + a_0 \in \mathbb{Z}[x]$ with $a_0 \neq 0$ and $f(x)$ has a zero in $\mathbb{Q}$, then $f(x)$ has a zero $m \in \mathbb{Z}$ and $m | a_0$.

___

**PROOF**)
If $f(x)$ has a zero in $\mathbb{Q}$, by [[Cor 23.3]], $f(x)$ has a linear factor.
By [[Thm 23.11]], $f(x)$ has a factorization with a linear factor in $\mathbb{Z}[x]$.
So, for some $m \in \mathbb{Z}$, $$f(x) = (x-m)(x^{n-1}+\cdots - a_0/m)$$
Thus, $a_0/m \in \mathbb{Z}$, $m | a_0$.

___

**EXAMPLE**)

* $x^2 -2$ has a zero in $\mathbb{Q}$ $\iff$ $x^2 - 2$ has a zero in $\mathbb{Z}$.

Moreover, this zero $m$ divides $-2$, So, it is enough to check that the divisor of $-2$.

___

