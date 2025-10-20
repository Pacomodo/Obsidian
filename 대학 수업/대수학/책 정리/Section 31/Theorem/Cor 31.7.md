___

**THEOREM**)
Let $E$ is an [[Extension field|extension field]] of $F$ and $\alpha \in E$ is [[Algebraic, transcendental|algebraic]] over $F$ and $\beta \in F(\alpha)$.
Then, $\deg(\beta, F) | \deg(\alpha, F)$. (Recall [[Simple extension]])

___

**PROOF**)
By [[Thm 30.23]], $\deg(\alpha, F) = [F(\alpha):F]$ and $\deg(\beta, F) = [F(\beta):F]$.
We know that $F \leq F(\beta) \leq F(\alpha)$,(why? $F$를 원이라고 생각하고, 원 밖에 막대는 $\alpha$ 라고 한다면 그걸 둘러싸는 원을 생각해보자.) so, $\deg(\beta, F)$ must divide $\deg(\alpha, F)$.

___

**EXAMPLE**)

* There is no element of $\mathbb{Q}(\sqrt{2})$ that is a zero of $x^3 - 2$.

Note that $\deg(\sqrt{2}, \mathbb{Q}) = 2$, while a zero of $x^3 - 2$ is of degree 3 over $\mathbb{Q}$ and $2 \nmid 3$.

Let $F \leq E$ and $\alpha_1, \alpha_2 \in E$.(not necessarily algebraic over $F$)
By definition, $F(\alpha_1)$ is the smallest extension field of $F$ in $E$ that contains $\alpha_1$.
Similarly, $(F(\alpha_1))(\alpha_2)$ is the smallest extension field of $F$ in $E$ that contains both $\alpha_1, \alpha_2$.
We can start equally with $\alpha_2$, so, $(F(\alpha_1))(\alpha_2) = (F(\alpha_2))(\alpha_1)$.
We denote this field by $F(\alpha_1, \alpha_2)$.
Similarly, for $\alpha_1, \alpha_2, \cdots, \alpha_n \in E$, $F(\alpha_1, \alpha_2, \cdots, \alpha_n)$ is the smallest extension field of $F$ in $E$ containing all $a_i$.
[[Exercise 49]] of Section 18 shows that, analogous to an intersection of subgroups of a group, an intersection of subfields of a field $E$ is a subfield of $E$.
Thus $F(\alpha_1, \alpha_2,\cdots, \alpha_n)$ can be characterized as the intersection of all subfields of $E$ containing $F$ and all the $a_i$.

* Consider $\mathbb{Q}(\sqrt{2})$.

[[Thm 30.23]] shows that $\{1, \sqrt{2}\}$ is a basis for $\mathbb{Q}(\sqrt{2})$ over $\mathbb{Q}$.
Using the technique in [[Algebraic, transcendental#^916880|Example 29.10]], we can easily show that $\sqrt{2} + \sqrt{3}$ is a zero of $x^4 -10x^2 + 1$.
It is irreducible in $\mathbb{Q}[x]$.(We can show it by using the technique in [[Thm 23.11#^2ba97b|Example 23.14]])
Thus, $\mathrm{irr}(\sqrt{2}+\sqrt{3}, \mathbb{Q}) = x^4-10x^2+1$.
So, $[\mathbb{Q}(\sqrt{2}+\sqrt{3}):\mathbb{Q}] = 4$. Since $\sqrt{2}+\sqrt{3} \notin \mathbb{Q}(\sqrt{2})$, $\sqrt{3}\notin\mathbb{Q}(\sqrt{2})$.
Thus, $\{1, \sqrt{3}\}$ is a basis for $\mathbb{Q}(\sqrt{2},\sqrt{3}) = (\mathbb{Q}(\sqrt{2}))(\sqrt{3})$ over $\mathbb{Q}(\sqrt{2})$.
The proof of [[Thm 31.4]] shows that $\{1, \sqrt{2}, \sqrt{3}, \sqrt{6}\}$ is a basis for $\mathbb{Q}(\sqrt{2}, \sqrt{3})$ over $\mathbb{Q}$.

* It is possible for an extension $F(\alpha_1, \alpha_2, \cdots, \alpha_n)$ of a field $F$ to be actually [[Simple extension|simple extension]] even though $n > 1$.

Let $2^{1/3}$ be the cube root of $2$ and $2^{1/2}$ be the positive square root of $2$.
Since $\deg(2^{1/2}, \mathbb{Q}) = 2$ and $2 \nmid 3 = \deg(2^{1/3}, \mathbb{Q})$, $2^{1/2} \notin \mathbb{Q}(2^{1/3})$.
Thus, $[\mathbb{Q}(2^{1/3},2^{1/2}),\mathbb{Q}(2^{1/3})] = 2$.
Hence, $\{1, 2^{1/3}, 2^{2/3}\}$ is a basis for $\mathbb{Q}(2^{1/3})$ over $\mathbb{Q}$ and $\{1, 2^{1/2}\}$ is a basis for $\mathbb{Q}(2^{1/3},2^{1/2})$ over $\mathbb{Q}(2^{1/3})$.
By the proof of [[Thm 31.4]], $\{1, 2^{1/2}, 2^{1/3},2^{5/6}, 2^{2/3},2^{7/6}\}$ is a basis for $\mathbb{Q}(2^{1/3},2^{1/2})$ over $\mathbb{Q}$.
Since $2^{7/6} = 2(2^{1/6})$, $2^{1/6} \in \mathbb{Q}(2^{1/3}, 2^{1/2})$.
$x^6 - 2$ is irreducible over $\mathbb{Q}$ and has a zero $2^{1/6}$. (By [[Thm 23.15|eisenstein criterion]] with $p = 2$)
Thus $\mathbb{Q} \leq \mathbb{Q}(2^{1/6}) \leq \mathbb{Q}(2^{1/3},2^{1/2})$.
By [[Thm 31.4]], $6 = [\mathbb{Q}(2^{1/3},2^{1/2}), \mathbb{Q}] = [\mathbb{Q}(2^{1/3},2^{1/2}), \mathbb{Q}(2^{1/6})][\mathbb{Q}(2^{1/6}):\mathbb{Q}] = [\mathbb{Q}(2^{1/3},2^{1/2}), \mathbb{Q}(2^{1/6})]\cdot 6$,
So, $[\mathbb{Q}(2^{1/3},2^{1/2}), \mathbb{Q}(2^{1/6})] = 1$, $\mathbb{Q}(2^{1/3},2^{1/2}) = \mathbb{Q}(2^{1/6})$. (Go to [[Finite extension#^1c87a8|recall]]).

___
