___

**THEOREM**)
Every finite [[Integral Domain|integral domain]] is a [[Field|field]].

___

**PROOF**)
Let $$0, 1, a_1, \cdots, a_n$$ be all the elements of a finite integral domain $D$.
We need to show that 2 things.
1. Commutative
Since integral domain is commutative ring, it is obvious.
2. Division ring
To show that $D$ is [[Division ring|division ring]], we need to show that every nonzero element has multiplicative inverse.
Pick any $a \in D$ where $a \neq 0$.
Consider $$a1, aa_1, \cdots, aa_n.$$
If $aa_i = aa_j$, then by [[Thm 19.5|cancelation law]], $a_i = a_j$ (they are all distinct).
Also, $D$ has no [[Divisors of 0|0 divisors]], none of them is 0.
Hence by counting, $a1 = 1$ or $aa_i = 1$ for some $i$.
Thus, $a$ has a multiplicative inverse.

___
