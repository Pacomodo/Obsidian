___

**DEF**)
The vectors in a subset $S = \{\alpha_i | i \in I\}$ of a [[Vector space|vector space]] $V$ over a [[Field|field]] $F$ are **linearly independent over $F$** if, for any distinct vectors $\alpha_{i_j} \in S$, coefficients $a_j \in F$ and $n \in \mathbb{Z}^+$, $\sum_{j=1}^n a_j\alpha_{i_j} = 0 \in V$ $\implies a_j = 0$ for $j = 1, \cdots, n$.
If the vectors are not linearly independent over $F$, they are **linearly dependent over $F$**.

___

Thus the vectors in $\{\alpha_i | i \in I\}$ are linearly independent over $F$ if the only way the $0$-vector can be expressed as a linear combination of the vectors $\alpha_i$ is to have all scalar coefficients equal to 0.
If the vectors are linearly dependent over $F$, then there exists $a_j \in F$ for $j = 1, \cdots , n$ such that $\sum_{j=1}^n a_j\alpha_{i_j} = 0$, where not all $a_j = 0$.

**EXAMPLE**)

* The vectors spanning the space $\mathbb{R}^n$ that are given in [[Span, Linear combination#^bf80cc|Example 30.7]] are linearly independent over $\mathbb{R}$.

* The vectors in $\{x^m|m\geq 0\}$ are linearly independent vectors of $F[x]$ over $F$.

* (1, -1), (2, 1), (-3, 2) are linearly dependent in $\mathbb{R}^2$ over $\mathbb{R}$.

Since $7(1, -1) + (2, 1) + 3(-3,2) = (0, 0) = 0$.

* Let $E$ be an extension field of a field $F$. Let $\alpha \in E$ be algebraic over $F$. ^1e73df

If $\deg(\alpha, F) = n$, then by [[Thm 29.18]], every element of $F(\alpha)$ can be *uniquely* expressed in the form $$b_0 + b_1\alpha + \cdots + b_{n-1}\alpha^{n-1}$$for $b_i \in F$.
In particular, $0 = 0 + 0\alpha + \cdots + 0\alpha^{n-1}$ must be a *unique* expression for $0$.
Thus, the elements $1, \alpha, \cdots, \alpha^{n-1}$ are linearly independent vectors in $F(\alpha)$ over the field $F$.
They also span $F(\alpha)$.
So, $1, \alpha, \cdots, \alpha^{n-1}$ form a [[Basis|basis]] for $F(\alpha)$ over $F$.
**This is important example**.

___