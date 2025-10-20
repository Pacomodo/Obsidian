___

Prove that if $p$ is an [[Irreducible|irreducible]] in a [[Unique factorization domain|UFD]], then $p$ is a [[Prime|prime]].

___

**PROOF**)
Let $D$ is an UFD. What we want to show is that if $p$ divides $ab$ where $a,b \in D$, then $p$ divides $a$ or $p$ divides $b$.
Let $pc = ab$ for some $c \in D$.
Since $a, b, c$ in UFD, we can factorize $a, b$ and $c$ into product of irreducibles.
So, $pc_1c_2 \cdots c_l = a_1a_2\cdots a_m b_1 b_2 \cdots b_n$ where $c_i, a_j, b_k \in D$ are all irreducibles.
Since $D$ is UFD, $p$ must associate with $a_j$ for some $j$ or $b_k$ for some $k$.
Therefore, $p$ must divide $a_1\cdots a_m = a$ or $b_1 \cdots b_n = b$.

___
