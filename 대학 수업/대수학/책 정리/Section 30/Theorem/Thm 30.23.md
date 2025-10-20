___

**THEOREM**)
Let $E$ be an [[Extension field|extension field]] of $F$. Let $\alpha \in E$ be [[Algebraic, transcendental|algebraic]] over $F$.
Let $\deg(\alpha, F) = n$.
Then, $F(\alpha)$ is an $n$-[[Finite dimensional|dimensional]] [[Vector space|vector space]] over $F$ with [[Basis|basis]] $\{1, \alpha, \cdots, \alpha^{n-1}\}$.
Furthermore, every element $\beta \in F(\alpha)$ is algebraic over $F$ and $\deg(\beta, F) \leq \deg(\alpha, F)$.

___

**PROOF**)

1. $F(\alpha)$ is an $n$-dimensional vector space over $F$.

We already showed that in [[Dimension#^5b7497|Example 30.22]].

2. Every element $\beta \in F(\alpha)$ is algebraic over $F$ and $\deg(\beta, F) \leq \deg(\alpha, F)$.

Consider the elements $1, \beta, \beta^2, \cdots, \beta^n$.
These cannot be $n+1$ distinct elements of $F(\alpha)$ that are [[Linearly dependent, independent|linearly independent]] over $F$ by [[Thm 30.19]]. i.e. they are linearly dependent over $F$.
If $\beta^i = \beta^j$, then $\beta^i - \beta^j = 0$, so, in any case, there exist $b_i \in F$ such that $$b_0 + b_1\beta + b_2\beta^2 + \cdots + b_n\beta^n = 0$$where not all $b_i = 0$.
Then $f(x) = b_nx^n + \cdots + b_1x + b_0$ is a nonzero element of $F[x]$ such that $f(\beta) = 0$.
Therefore, $\beta$ is algebraic over $F$ and $\deg(\beta, F) \leq n$.

___

**EXAMPLE**)

* Consider the case where $F = \mathbb{Q}$, $E = \mathbb{C}$ and $\alpha = \sqrt[3]{2}$.

(1) $\alpha = \sqrt[3]{2}$ is algebraic over $\mathbb{Q}$ and $irr(\alpha, \mathbb{Q}) = x^3 - 2$.

(2) $\mathbb{Q}(\sqrt[3]{2}) = \{a + b\sqrt[3]{2} + c\sqrt[3]{4}|a,b,c \in \mathbb{Q}\}$ and $\dim_\mathbb{Q} \mathbb{Q}(\sqrt[3]{2}) = 3$.

(3) Every $\beta \in \mathbb{Q}(\sqrt[3]{2})$ is algebraic over $\mathbb{Q}$. Furthermore, $\deg(\beta, \mathbb{Q}) \leq 3$.
For example, $\beta = \sqrt[3]{2} + \sqrt[3]{4}$ is algebraic over $\mathbb{Q}$.
Then, **HOW CAN WE FIND THE POLYNOMIAL $irr(\beta, \mathbb{Q})$**?

**(Step 1)**
We know that the set $\{1, \beta, \beta^2, \beta^3\}$ is linearly dependent over $\mathbb{Q}$.
That is, there exists $a, b, c, d \in \mathbb{Q}$ such that $(a,b,c,d) \neq (0,0,0,0)$ and $a + b\beta + c\beta^2 + d\beta^3 = 0$.

**(Step 2)**
Since $\{1, \beta, \beta^2, \beta^3\} = \{1, \sqrt[3]{2} + \sqrt[3]{4}, 4 + 2\sqrt[3]{2} + \sqrt[3]{4}, 6 + 6\sqrt[3]{2} + 6\sqrt[3]{4}\}$, we have $$a+b(\sqrt[3]{2} + \sqrt[3]{4}) + c(4 + 2\sqrt[3]{2} + \sqrt[3]{4})+d(6 + 6\sqrt[3]{2} + 6\sqrt[3]{4}) = 0$$and hence $$(a+4c+6d) + (b+2c+6d)\sqrt[3]{2} + (b+c+6d)\sqrt[3]{4} = 0$$

**(Step 3)**
Since $\{1, \sqrt[3]{2}, \sqrt[3]{4}\}$ is linearly independent, it follows that $$\left\{\begin{matrix}
a+4c+6d = 0 \\ b+2c+6d = 0 \\ b+c+6d = 0\end{matrix}\right.$$

**(Step 4)**
We get $c = 0$, $a = b = -6d$ and so $$(a,b,c,d) = (-6d,-6d,0,d) = -d\times(6,6,0,-1).$$
Therefore, $6\beta^3 + 6\beta^2 - 1 = 0$.
One can prove directly that $6x^3 + 6x^2 - 1$ is irreducible over $\mathbb{Q}$.

In consequence, we have $irr(\beta, \mathbb{Q}) = x^3 + x^2 - 1/6$.

___

