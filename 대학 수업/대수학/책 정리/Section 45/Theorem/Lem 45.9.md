___

**LEMMA**)
Let $R$ be a commutative [[Ring]] and let $N_1 \subseteq N_2 \subseteq \cdots$ be an ascending chain of [[Ideal|ideal]]s $N_i$ in $R$.
Then, $N = \bigcup _i N_i$ is an ideal of $R$.

___

**PROOF**)
First, we want to show that $N$ is an additive subgroup of $R$.
Let $a, b \in N$. then $a \in N_i$ and $b \in N_j$ for some $i, j$.
Then either $N_i \subseteq N_j$ or $N_j \subseteq N_i$, so, WLOG, let $N_i \subseteq N_j$.
So, $a, b \in N_j$, which is ideal. Hence, $a+b, -b, 0 \in N_j \subseteq N$.
Pick any $a \in N$ and $r \in R$. Since $a \in N$, there must be $i$ such that $a \in N_i$. Since $N_i$ is an ideal, $ar \in N_i \subseteq N$. Similiarly, $ra \in N_i \subseteq N$.
Hence, $N$ is an ideal of $R$.

___
