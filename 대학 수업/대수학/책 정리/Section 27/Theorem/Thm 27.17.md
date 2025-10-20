___

**THEOREM**)
Let $R$ be a [[Ring|ring]] with unity $1_R$.
The map $\phi : \mathbb{Z} \rightarrow R$ where $n \mapsto n\cdot 1_R$ is a [[Ring homomorphism|homomorphism]] of $\mathbb{Z}$ into $R$.

___

**PROOF**)

**RECALL**: $n \cdot 1$ means $1 + 1 + \cdots 1$ for $n$ summands if $n > 0$ and $(-1) + \cdots + (-1)$ for $|n|$ summands if $n < 0$, $n \cdot 1 = 0$ when $n = 0$.

1. $\phi(n + m) = (n+m) \cdot 1_R = (n \cdot 1_R) + (m \cdot 1_R) = \phi(n) + \phi(m)$
2. If $n, m > 0$, by distribute law in $R$, $(n \cdot 1_R)(m \cdot 1_R) = (nm) \cdot 1_R$.
We can argue that similarly for all $n, m \in \mathbb{Z}$ by distribute law.
Thus, $\phi (nm) = (nm) \cdot 1_R = (n \cdot 1_R)(m \cdot 1_R) = \phi(n) \phi(m)$.

___
