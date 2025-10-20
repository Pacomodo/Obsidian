___

**THEOREM**)
Every [[Principal ideal domain|PID]] is [[Unique factorization domain|UFD]].

___

**PROOF**)

Let $D$ is PID and $a \in D$ is nonzero nonunit element.
We need to show that 2 things.
1. Existence of factorization ([[Thm 45.11]])
2. Uniqueness of factorization.

We want to show that the uniqueness of factorization.
Let $a = p_1p_2 \cdots p_n = q_1q_2 \cdots q_m$ where $p_i, q_j \in D$ and they are all irreducibles.
Since $p_1$ divides $q_1 \cdots q_m$ and we know that in PID, irreducibles and primes are same([[Thm 45.11]]), so, $p_1 | q_j$ for some $j \in \mathbb{Z}^+$.
So, $p_1u_1 = q_j$ and we know that $q_j$ and $p_1$ is irreducible, so, $u$ is an unit.
By cancelation law in $D$, we can cancel out $p_1$ on both sides.
By induction, $1 = u_1\cdots u_n q_{n+1} \cdots q_m$ and $q_j$ are all irreducibles, $n = m$.

___

* Remark : If an integral domain $D$ is not a UFD, then it is not a PID.
It means, there exists an ideal $I$ of $D$ which can never be a [[Principal ideal|principal ideal]].

For example, we know that $D = \{a+b\sqrt{-3} | a, b \in \mathbb{Z} \}$ is not a UFD since $$ 4 = 2 \times 2 = (1 + \sqrt{-3})(1 - \sqrt{-3})$$
Hence, there is an ideal $I$ in $D$ which is not a principal ideal.

* Problem 1 : Prove that $I = \left< 1+\sqrt{-3}, 2 \right>$ is a proper ideal of $D$.
Let $d \in D$ and $d = a+b\sqrt{-3}$. Then, $d(n(1+\sqrt{-3}) + 2m) = (a+b\sqrt{-3})(n+\$  