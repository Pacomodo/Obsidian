___

**DEF**)
An [[Integral Domain|integral domain]] $D$ is a **unique factorization domain (UFD)** if the followings hold.
Let $a \in D$ be a nonzero non-[[Unit|unit]] element.
1. $a$ can be written as the product of finitely many [[Irreducible|irreducible]] elements in $D$.
2. If $a = p_1 \cdots p_r = q_1 \cdots q_s$ for some irreducible elements $p_1, \cdots, p_r, q_1, \cdots , q_s$, then, $$r = s$$ and the $q_j$ can be renumbered so that $p_i$ and $q_i$ are associates.

___

**EXAMPLES**)

* Consider integral domain $D = \{a+b\sqrt{-3}|a, b \in \mathbb{Z}\}$.
The element $4$ admits the following two [[Irreducible|irreducible]] factorization.
$$ 4 = 2 \times 2 = (1+\sqrt{-3})(1-\sqrt{-3})$$
Here, $2$ and $1+\sqrt{-3}$ are not [[associate]]s each other in $D$ since $2 \neq ( \pm 1) \times (1+\sqrt{-3})$.
Thus, $D$ fails to satiesfy "the unique factorization property".

* The [[Ring|ring]] of integers $\mathbb{Z}$ is a UFD.

* [[Thm 23.20]] says that if $F$ is a field, then $F[x]$ is a UFD.

___
