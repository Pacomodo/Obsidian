___

**a**. Show that an intersection of subrings of a [[Ring]] $R$ is again a subring of $R$.

___

**SOL**)
Let $C_i$ be a subring of a ring $R$.
What we want to show that $\bigcap_{i \in I} C_i$ is a subring of $R$.
If multiplication is closed in $\bigcap_{i\in I}C_i$, then associativity and distribute law directly comes from $R$.
So, it is enough to show that multiplication is closed in this set.
Pick $a, b \in \bigcap_{i\in I}C_i$. Then, $a, b \in C_j$ for all $j \in I$.
Since $C_j$ is a subring of $R$, $ab \in C_j$ for all $j \in I$. So, $ab \in \bigcap_{i \in I} C_i$.

___

**b**. Show that an intersection of subfields of a [[Field]] $F$ is again a subfield of $F$.

___

**SOL**)
We already showed that an intersection of subrings is subring of $R$.
Commutativity comes from $F$ and $F$ has no nonunit element, so, an intersection of subfields are again subfield of $F$.