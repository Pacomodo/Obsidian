___

**BACKGROUNDS**)
Let $E$ be an [[Extension field|extension field]] of a field $F$. Let $\alpha \in E$.
Let $\phi_\alpha$ be the [[Evaluation homomorphism|evaluation homomorphism]] of $F[x]$ into $E$ with $\phi_\alpha(a) = a$ for $a \in F$ and $\phi_\alpha(x) = \alpha$ as in [[Thm 22.4]].

We consider two cases.

**Case I**) $\alpha$ is [[Algebraic, transcendental|algebraic]] over $F$.
Then, as [[Thm 29.13]], $Ker(\phi_\alpha) = \left<irr(\alpha, F)\right>$ and by [[Thm 27.25]], $\left<irr(\alpha, F)\right>$ is a [[Maximal ideal]] of $F[x]$. Therefore, $F[x]/\left<irr(\alpha, F)\right>$ is a [[Field]] by [[Thm 27.9]] and it is isomorphic to the image $\phi_\alpha [F[x]] \subset E$ by [[Thm 26.17|the fundemental homomorphism theorem]].
Then, this subfield $\phi_\alpha[F[x]] \subset E$ is the smallest subfield of $E$ containing $F$ and $\alpha$.
We shall denote this field by $F(\alpha)$.
**Case II**) $\alpha$ is [[Algebraic, transcendental|transcendental]] over $F$.
Then, by [[Thm 29.12]], $\phi_\alpha$ gives an ring isomorphism of $F[x]$ with a subdomain of $E$.
Thus, $\phi_\alpha[F[x]]$ is **not** a field but an [[Integral Domain]]. (Because, we cannot assure that it is [[Division ring|division ring]])
We shall denote this by $F[\alpha]$.
By [[Cor 21.8]], field $E$ contains a [[Field of quotients of integral domain|field of quotients]] of $F[\alpha]$.
This field of quotients is the smallest subfield of $E$ containing $F$ and $\alpha$.
As in Case I, we denote this field by $F(\alpha)$.
More precisely, $$F(\alpha) \cong \left\{ \frac{f(x)}{g(x)} | f(x), g(x) \in F[x] , g(x) \neq 0\right\}$$

___

**EXAMPLE**)

* $\pi$ is [[Algebraic, transcendental|transcendental]] over $\mathbb{Q}$.

The field $\mathbb{Q}(\pi)$ is isomorphic to the field $\mathbb{Q}(x)$ of rational functions over $\mathbb{Q}$ in the [[indeterminate]] $x$.
Thus, from a structural viewpoint, an element that is transcendental over a field $F$, behaves as though it were an indeterminate over $F$.

___

**DEF**)
An extension field of $E$ of a field $F$ is a **simple extension of $F$** if $E = F(\alpha)$ for some $\alpha \in E$.

___
