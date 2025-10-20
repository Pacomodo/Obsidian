___

**DEF**)
We say that $D$ is a **Euclidean domain** if there is a function $$\nu : D - \{0\} \rightarrow \mathbb{Z}_{\geq 0}$$
satiesfying the following two conditions:

1. If $a , b \in D - \{0\}$, then, $\nu(a) \leq \nu(ab)$.
2. If $a \in D$ and $b \in D - \{0\}$, $\exists q, r \in D$ such that $a = bq + r$ where either $r = 0$ or $\nu(r) < \nu(b)$.

The function $\nu$ is called **the Euclidean norm**.

___

**EXAMPLES**)

* $\mathbb{Z}$ is a Euclidean domain with the Euclidean norm $\nu : \mathbb{Z}-\{0\} \rightarrow \mathbb{Z}_{\geq 0}, n \mapsto |n|$.

* $F[x]$ over a field $F$ is a Euclidean domain with the Euclidean norm $\nu : F[x] - \{0\} \rightarrow \mathbb{Z}_{\geq 0}, f(x) \mapsto deg f(x)$.

___
