___

**DEF**)
Let $V$ be a [[Vector space|vector space]] over $F$.
The vectors in a subset $S = \{\alpha_i | i \in I \} \subset V$ **span** (or **generate**) $V$ if for every $\beta \in V$, we have $$\beta = a_1\alpha_{i_1} + a_2\alpha_{i_2} + \cdots + a_n\alpha_{i_n}$$for some $a_j \in F$ and $\alpha_{i_j} \in S$,$j = 1, \cdots, n$.
A vector $\sum_{j=1}^{n} a_j\alpha_{i_j}$ is a **linear combination of the $\alpha_{i_j}$**.

___

**EXAMPLE**)

* The vector space $\mathbb{R}^n$ over $\mathbb{R}$ of [[Vector space#^550329|Example 30.2]] ^bf80cc

The vectors, $$(1, 0, \cdots, 0),(0, 1, \cdots, 0), (0, 0, \cdots, 1)$$ clearly span $\mathbb{R}^n$, for $$(a_1, a_2, \cdots, a_n) = a_1(1,0,\cdots,0) + \cdots + a_n(0, 0, \cdots, 1).$$
* The vector space of [[Vector space#^f4586d|Example 30.3]].

The monomials $x^m$ for $m \geq 0$ span $F[x]$ over $F$.

* Let $F$ be a field and $E$ an [[Extension field|extension field]] of $F$. ^947a6d

Let $\alpha \in E$ be [[Algebraic, transcendental|algebraic]] over $F$.
Then $F(\alpha)$ is a vector space over $F$.
By [[Thm 29.18]], it is spanned by the vectors in $\{1, \alpha, \cdots, \alpha^{n-1}\}$.
**This is the important example**.

___
