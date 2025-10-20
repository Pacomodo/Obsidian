___

**THEOREM**)
Let $D$ be a [[Euclidean domain|Euclidean domain]] with Euclidean norm $\nu$.
Then $D$ is [[Principal ideal domain|PID]].

___

**PROOF**)
Let $N$ be a nonzero ideal in $D$.
We want to show that there exists $b \in D$ such that $N = \left< b \right>$.

Consider $B = \{\nu(t) | t \in N - \{0\}\} \subset \mathbb{Z}_{\geq 0}$. Since $B$ is nonempty, by Well-Ordering Principle, $B$ has a least element $m$.
Now, choose $b \in N - \{0\}$ such that $\nu(b) = m$.

* Claim: $N = \left< b \right>$.
1. $\left< b \right> \subseteq N$
It is obvious.
2. $\left< b \right> \supseteq N$
Let $a \in N$. Then $a = bq + r$ for some $q, r \in D$ such that either $r = 0$ or $\nu(r) < \nu(b)$.
$r = a - bq$ and $a, b \in N$ and $N$ is ideal, $r \in N$.
So, $\nu(r) < \nu(b)$ is impossible, so, $r = 0$.
So, $a = bq$. This shows that $a \in \left< b \right>$.

___

