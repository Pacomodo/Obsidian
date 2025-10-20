___

**LEMMA**) **(Ascending Chain Condition for a PID)**
Let $D$ be a [[Principal ideal domain|PID]].
If $N_1 \subseteq N_2 \subseteq \cdots$ is an ascending chain of [[Ideal|ideal]]s $N_i$, then there exists a positive integer $r$ such that $N_r = N_s$ for all $s \geq r$.

___

**PROOF**)
Consider $N = \bigcup _i N_i$. By [[Lem 45.9]], $N$ is an ideal. Since $D$ is PID, $N = \left< a \right>$ for some $a \in D$.
Since $a \in N$, there exists $r \in \mathbb{Z}^+$ such that $a \in N_r$.
So, $\left< a \right> \subseteq N_r \subseteq N_s \subseteq N = \left< a \right>$. Thus $N_r = N_s$ for all $s \geq r$.

___

Note that for every ring $R$, the conditions **ACC, MC, and FBC** are equivalent.
Go to [[Exercise 32|Exercise 32]].

Remember that for element $a, b \in D$, $$ \left< a \right> \subseteq \left< b \right> \Leftrightarrow b|a$$ and $$\left< a \right> = \left< b \right> \Leftrightarrow a \sim b$$
where $\sim$ are [[associate|associate]] relation.

Because, $\left< a \right> \subseteq \left< b \right> \Leftrightarrow a \in \left< b \right> \Leftrightarrow a = bd \Leftrightarrow b|a$ for some $d \in D$.

___
