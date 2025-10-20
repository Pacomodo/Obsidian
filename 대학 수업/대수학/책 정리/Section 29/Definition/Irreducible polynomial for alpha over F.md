 ___

**DEF**)
Let $E$ be an extension field of a field $F$. Let $\alpha \in E$ be [[Algebraic, transcendental|algebraic]] over $F$.
The **unique [[Monic polynomial|monic polynomial]]** $p(x)$ having the property in [[Thm 29.13]] is the **irreducible polynomial for $\alpha$ over $F$**.
We will denote it by $irr(\alpha, F)$.
The degree of $irr(\alpha, F)$ is the **degree of $\alpha$ over $F$**.
We will denote it by $deg(\alpha, F)$.

___

**EXAMPLE**)

* We know that $\textrm{irr}(\sqrt{2}, \mathbb{Q}) = x^2 - 2$.

Refering to [[Algebraic, transcendental#^e69196|Example 29.10]], We see that for $\alpha = \sqrt{1+\sqrt{3}} \in \mathbb{R}$, $\alpha$ is a zero of $x^4 -2x^2 -2 \in \mathbb{Q}[x]$. $x^4 - 2x^2 - 2$ is irreducible over $\mathbb{Q}$.
So, $irr(\sqrt{1+\sqrt{3}}, \mathbb{Q}) = x^4 - 2x^2 - 2$ and $deg(\sqrt{1+\sqrt{3}}. \mathbb{Q}) = 4$.

Just as we must speak of an element $\alpha$ as *algebraic over $F$* rather than simply as *algebraic*, we **must speak** of the *degree of $\alpha$ of $F$* rather than *degree of $\alpha$*.

* $\sqrt{2} \in \mathbb{R}$ is algebraic of degree $2$ over $\mathbb{Q}$, but algebraic of degree $1$ over $\mathbb{R}$.
For $irr(\sqrt{2}, \mathbb{R}) = x - \sqrt{2}$.

**PROBLEM**)

* $\alpha = \sqrt{2} + \sqrt{3}$

Prove that $\alpha$ is algebraic over $\mathbb{Q}$. What are $irr(\alpha, \mathbb{Q})$ and $deg(\alpha, \mathbb{Q})$?
Sol)
$\alpha^2 = 2+3 + 2\sqrt{6} = 5+2\sqrt{6}$ $\Rightarrow$ $(\alpha^2 - 5)^2 = 24$ $\Rightarrow$ $\alpha^4 - 10\alpha^2 +1 = 0$.
So, $\alpha$ is the zero of $f(x) = x^4 -10x + 1$.
$f(x)$ is irreducible over $\mathbb{Q}$, So, $deg(\alpha, \mathbb{Q}) = 4$.

* $\beta = \sqrt{2} + \sqrt{3} + \sqrt{5}$

Prove that $\beta$ is algebraic over $\mathbb{Q}$. What are $irr(\beta, \mathbb{Q})$ and $deg(\beta, \mathbb{Q})$?
Sol)

* Let $p$ be a prime number and consider the complex number $$w = e^{\frac{2\pi i}{p}} = \mathrm{cos}\left(\frac{2\pi}{p}\right) + i\mathrm{sin}\left(\frac{2\pi}{p}\right) \in \mathbb{C}$$

Prove that $w$ is algebraic over $\mathbb{Q}$. What are $irr(w, \mathbb{Q})$ and $deg(w, \mathbb{Q})$?
Sol)

___

#incomplete 
