___

**THEOREM**) (Euclid Lemma in $F[x]$)
Let $p(x)$ be an [[Irreducible polynomial|irreducible polynomial]] in $F[x]$.
If $p(x)$ divides $r(x)s(x)$ for $r(x), s(x) \in F[x]$, then either $p(x)|r(x)$ or $p(x)|s(x)$.

___

**PROOF**)
Suppose $p(x)|r(x)s(x)$. Then, $r(x)s(x) \in \left< p(x) \right>$. Since $p(x)$ is irreducible over $F$, $\left< p(x) \right>$ is maximal ideal by [[Thm 27.25]], then, by [[Cor 27.16]], prime ideal.
So, either $r(x) \in \left< p(x) \right>$ or $s(x) \in \left< p(x) \right>$.
Hence, either $p(x)|r(x)$ or $p(x) | s(x)$.

___

This theorem fills the gap in [[Thm 23.20]].