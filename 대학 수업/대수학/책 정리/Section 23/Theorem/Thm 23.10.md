___

**THEOREM**)
Let $f(x) \in F[x]$ and let $deg(f(x)) = 2$ or $3$.
Then $f(x)$ is reducible over $F$ $\Leftrightarrow$ $f(x)$ has a zero in $F$.

___

**PROOF**)
$(\Rightarrow)$ Assume that $f(x)$ is reducible over $F$, so, we can express $f(x) = g(x)h(x)$ where $g(x), h(x) \in F[x]$, $0 < deg(g(x)) < deg(f(x))$ and $0 < deg(h(x)) < deg(f(x))$.
Since $deg(f(x)) = 2$ or $3$, either $g(x)$ or $h(x)$ is of degree $1$.
If $g(x)$ is of degree $1$, then except for possible factor in $F$, $g(x) = x - a$, so $g(a) = 0 \rightarrow f(a) = 0$.

$(\Leftarrow)$ By [[Cor 23.3]], $f(x)$ has a factor of the form $x - a$, so, $f(x)$ is reducible.

___
