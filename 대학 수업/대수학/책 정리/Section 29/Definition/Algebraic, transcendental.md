___

**DEF**)
An element $\alpha$ of an [[Extension field]] $E$ of a field $F$ is **algebraic over** $F$
if $f(\alpha) = 0$ for some nonzero $f(x) \in F[x]$.
If $\alpha$ is not algebraic over $F$, then $\alpha$ is **transcendental over** $F$.

___

**EXAMPLE**)

* $\mathbb{C}$ is an [[Extension field]] of $\mathbb{Q}$. Since $\sqrt{2}$ is a zero of $x^2 - 2$, we see that $\sqrt{2}$ is an algebraic element over $\mathbb{Q}$.

* It is well-known that the real numbers $\pi$ and $e$ are transcendental over $\mathbb{Q}$.

We do not speak simply of an *irreducible polynomial*, but rather of an *irreducible polynomial over $F$*.
Similarly, we **do not** speak simply of an *algebraic element*, but rather of an *element algebraic over $F$*.

* $\pi$ is transcendental over $\mathbb{Q}$.

However, $\pi$ is algebraic over $\mathbb{R}$, because it is a zero of $(x - \pi) \in \mathbb{R}[x]$.

* $\sqrt{1+\sqrt{3}}$ is algebraic over $\mathbb{Q}$. ^916880

$\alpha = \sqrt{1+\sqrt{3}}$ $\Rightarrow$ $\alpha ^2 = 1 + \sqrt{3}$ $\Rightarrow$ $\alpha ^2 - 1 = \sqrt{3}$ $\Rightarrow$ $(\alpha^2 - 1)^2 = 3$ $\Rightarrow$ $\alpha^4 - 2\alpha^2 - 2 = 0$.
so, $\alpha$ is a zero of $x^4 - 2x^2 - 2 \in \mathbb{Q}[x]$.
Moreover, we can prove this polynomial is [[Irreducible polynomial|irreducible]] by using [[Thm 23.15|Eisenstein Criterion]].  ^e69196
Take $p = 2$.

To connect these ideas with those of number theory, we give the following definition.

___

**DEF**)
An element of $\mathbb{C}$ that is algebraic over $\mathbb{Q}$ is an **algebraic number**.
A **transcendental number** is an element of $\mathbb{C}$ that is transcendental over $\mathbb{Q}$.

___

The next theorem gives a useful characterization of algebraic and transcendental elements over $F$ in an extension field $E$ of $F$.
It also illustrates the importance of our evaluation homomorphisms $\phi_\alpha$.
**Note that once more we are describing our concepts in terms of mappings.**
Go to [[Thm 29.12]].
