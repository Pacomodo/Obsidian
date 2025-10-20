___

**THEOREM**)
A [[Finite extension|finite extension]] field $E$ of a field $F$ is an [[Algebraic extension|algebraic extension]] of $F$.

___

**PROOF**)
We want to show that if $\alpha \in E$ then, $\alpha$ is [[Algebraic, transcendental|algebraic]] over $F$.
By [[Thm 30.19]], if $[E:F] = n$, then $1, \alpha, \alpha^2, \cdots, \alpha^n$ cannot be [[Linearly dependent, independent|linearly independent]] elements.
So there exists $a_i \in F$ such that $a_n\alpha^n + a_{n-1}\alpha^{n-1}+\cdots+a_0 = 0$ and not all $a_i = 0$.
Let $f(x) = a_nx^n + a_{n-1}x^{n-1} + \cdots + a_0$. Then, $f(x) \in F[x]$ and $f(x)$ is nonzero polynomial and $f(\alpha) = 0$.
Therefore, $\alpha$ is [[Algebraic, transcendental|algebraic]] over $F$.

___
