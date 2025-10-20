___

**THEOREM**)
Let $E$ be a [[Simple extension|simple extension]] $F(\alpha)$ of a field $F$. Let $\alpha$ be [[Algebraic, transcendental|algebraic]] over $F$.
Let $\deg(\alpha, F)  = n \geq 1$.
Then every element $\beta$ of $E = F(\alpha)$ can be uniquely expressed in the form $$\beta = b_0 + b_1\alpha + \cdots + b_{n-1}\alpha^{n-1},$$
where the $b_i \in F$.

___

**PROOF**)

Note that for usual evaluation homomorphism $\phi_\alpha$,
$$F(\alpha) = \phi_\alpha[F[x]] = \{f(\alpha) | f(x) \in F[x]\}$$
Let $$\textrm{irr}(\alpha, F) = p(x) = x^n + a_{n-1}x^{n-1} + \cdots + a_0.$$
then, $p(\alpha) = 0$.
For $f(x) \in F[x]$, there exist $q(x), r(x) \in F[x]$ such that $f(x) = q(x) \times p(x) + r(x)$ and either $r(x) = 0$ or else $\deg(r(x))<n$.
Then $f(\alpha) = r(\alpha)$ and hence $f(\alpha) = b_0 + b_1\alpha + \cdots + b_{n-1}\alpha^{n-1}$ for some $b_0, b_1, \cdots, b_{n-1} \in F$.

For the uniqueness, Suppose that $$b_0+b_1\alpha+\cdots+b_{n-1}\alpha^{n-1} = c_0+c_1\alpha+\cdots+c_{n-1}\alpha^{n-1}$$
for some $b_0, \cdots, b_{n-1}, c_0, \cdots, c_{n-1} \in F$.
Let $h(x) = (b_{n-1} - c_{n-1})x^{n-1} + \cdots + (b_0 - c_0) \in F[x]$.
Then, $h(\alpha) = 0$. Since $\deg(h(x)) < \deg(\textrm{irr}(\alpha, F)) = n$ and $\textrm{irr}(\alpha, F)$ must be nonzero minimal polynomial in $F[x]$ having $\alpha$ as zero, $h(x)$ must be zero polynomial.
Therefore, $b_i - c_i = 0 \implies b_i = c_i$.

___

**EXAMPLE**)

* Let $p(x) = x^2 + x + 1 \in \mathbb{Z}_2 [x]$.

Since $p(0) = p(1) = 1$, $p(x)$ is irreducible over $\mathbb{Z}_2$.
Let $\alpha := x + \left< p(x) \right> \in \mathbb{Z}_2[x] /\left< p(x) \right>$. Then, $p(\alpha) = 0$.
$\mathbb{Z}_2(\alpha) = \mathbb{Z}_2 [x] / \left< p(x) \right> = \{a+b\alpha | a, b \in \mathbb{Z}_2\}$ is a field of four elements.
$\mathbb{Z}_2(\alpha) = \{0, 1, \alpha, 1+\alpha\}$.
Since $\alpha^2 + \alpha + 1 = 0$, We know that $\alpha ^2 = -\alpha - 1 = \alpha+1$.
Using this, we can make a table like this.
![[Pasted image 20231111205904.png]]
Note that $1 + \alpha = \alpha^2$, So, $\mathbb{Z}_2(\alpha) - \{0\} = \{1, \alpha, \alpha ^2\}$, which is the cyclic group of order $3$.

* We want to show that $\mathbb{R}[x]/\left<x^2 + 1\right>$ is isomorphic to the field $\mathbb{C}$.

We saw in [[Thm 29.3#^07fc3e|Example 29.4]] that we can view $\mathbb{R}[x] / \left< x^2 + 1 \right>$ as an [[Extension field|extension field]] of $\mathbb{R}$.
Let $\alpha = x + \left< x^2 + 1 \right>$.
Then, $\mathbb{R}(\alpha) = \mathbb{R}[x] / \left< x^2 + 1 \right> = \{a + b\alpha | a, b \in \mathbb{R} \}$ by [[Thm 29.18]].
We know that $\alpha^2 + 1 = 0$, so, $\alpha$ plays the role of $i \in \mathbb{C}$ and $a + b\alpha$ plays the role of $(a + bi) \in \mathbb{C}$.
Thus $\mathbb{R}(\alpha) \cong \mathbb{C}$.

___
