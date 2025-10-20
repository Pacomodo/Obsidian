___

**THEOREM**)
If $F$ is a [[Field|field]], every [[Ideal|ideal]] in $F[x]$ is [[Principal ideal|principal]].

___

**PROOF**)
Let $N$ is an ideal of $F[x]$.

1. If $N$ is zero ideal, then $N = \left< 0 \right>$.
2. Suppose that $N \neq \{0\}$.
That is, $N$ contains at least one nonzero polynomial.
So, pick a nonzero polynomial $g(x) \in N$ of **minimal degree**.

If $deg(g(x)) = 0$, then $g(x)$ is constant polynomial, so, $g(x)$ is a unit. By [[Thm 27.5]], $N = F[x] = \left< 1 \right>$.

Let $deg(g(x)) \neq 0$. Pick any $f(x) \in N$.
By [[Thm 23.1|division algorithm]], $f(x)$ can be **uniquely** written as $f(x) = g(x)q(x) + r(x)$ for some $q(x), r(x) \in F[x]$ where $deg(r(x)) < deg(g(x))$.
Since $r(x) = f(x) - g(x)q(x) \in N$, so, $r(x)$ must be $0$, otherwise it contradicts to $g(x)$ is polynomial of minimal degree.
Hence, $f(x) \in \left< g(x) \right>$. It proves that $N = \left< g(x) \right>$.

___
