___

**THEOREM**)
Let $E$ be an [[Algebraic extension|algebraic extension]] of a field $F$.
There exist a finite number of elements $\alpha_1, \cdots, \alpha_n \in E$ such that $E = F(\alpha_1, \cdots, \alpha_n)$.
$\iff$ $E$ is a [[Finite dimensional|finite dimensional]] [[Vector space|vector space]] over $F$. ($E$ is [[Finite extension|finite extension]] over $F$)

___

**PROOF**)

$(\Rightarrow)$ Suppose that $E = F(\alpha_1, \cdots, \alpha_n)$.
Since $E$ is an algebraic extension of $F$, each $\alpha_i$ is algebraic over $F$, so each $\alpha_i$ is algebraic over every extension field of $F$ in $E$.
Thus $F(\alpha_1)$ is algebraic over $F$, and in general, $F(\alpha_1, \cdots, \alpha_j)$ is algebraic over $F(\alpha_1, \cdots, \alpha_{j-1})$ for $j = 2, \cdots, n$.
[[Cor 31.6]] applied to the sequence of finite extensions $$F, F(\alpha_1), F(\alpha_1, \alpha_2), \cdots, F(\alpha_1, \cdots, \alpha_n) = E$$ then shows that $E$ is a finite extension of $F$.

$(\Leftarrow)$ Suppose that $E$ is a finite algebraic extension of $F$.
If $[E:F] = 1$, then $E = F(1) = F$,  and we are done.
If $E \neq F$, let $\alpha_1 \in E - F$. Then $[F(\alpha_1):F] > 1$.
If $F(\alpha_1) = E$, we are done.
If not, let $\alpha_2 \in E - F(\alpha_1)$. Continuing this process, we see from [[Thm 31.4]] that since $[E:F]$ is finite, we must arrive at $\alpha_n$ such that $F(\alpha_1, \alpha_2, \cdots, \alpha_n) = E$.

___
