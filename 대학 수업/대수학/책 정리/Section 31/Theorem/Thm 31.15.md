___

**THEOREM**)
A field $F$ is [[Algebraically closed]] $\iff$
Every nonconstant polynomial in $F[x]$ factors in $F[x]$ into linear factors.

___

**PROOF**)
$(\Rightarrow)$ Let $F$ be algebraically closed, and let $f(x)$ be a nonconstant polynomial in $F[x]$.
Then $f(x)$ has a zero $a \in F$.
By, [[Cor 23.3]], $(x-a)$ is a factor of $f(x)$, so, $f(x) = (x-a)g(x)$.
Then if $g(x)$ is nonconstant, it has a zero $b \in F$, and we have $f(x) = (x-a)(x-b)h(x)$.
Continuing, we get a factorization of $f(x)$ in $F[x]$ into linear factors.

$(\Leftarrow)$ Suppose that every nonconstant polynomial of $F[x]$ has a factorization into linear factors.
If $ax-b$ is a linear factor of $f(x)$, then $b/a$ is a zero of $f(x)$. Thus $F$ is algebraically closed.

___
