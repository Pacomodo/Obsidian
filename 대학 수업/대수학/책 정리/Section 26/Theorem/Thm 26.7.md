___

**THEOREM**) (Analogue of  [[Thm 14.1]])
Let $\phi : R \rightarrow R'$ be a [[Ring homomorphism]] with [[대학 수업/대수학/책 정리/Section 26/Definition/Kernel|Kernel]] $H$.
Then, the additive [[Coset]]s of $H$ form a [[Ring]] $R/H$ whose binary operations are defined by choosing representatives.
* $(a + H) + (b + H) = (a+b) + H$
* $(a + H)(b + H) = (ab) + H$
Also, the map $\mu : R/H \rightarrow \phi[R]$ where $(a + H) \mapsto \phi(a)$ is an [[Isomorphism]].

___

**PROOF**)
By [[Thm 14.1]], it is enough to show that the multicative part.

1. We want to show that this [[Coset]] multiplication is well-defined.
Let $h_1, h_2 \in H$ and consider the representatives $a + h_1$ of $a + H$ and $b + h_2$ of $b + H$.
Let $c = (a + h_1)(b + h_2) = ab + ah_2 + bh_1 + h_1h_2$.
We want to show that $c \in (ab + H)$,
By [[Thm 26.5]], $\phi^{-1}[\phi(ab)] = (ab + H)$, so, enough to show that $\phi (c) = \phi (ab)$.
$\phi (c) = \phi(ab + ah_2 + bh_1 + h_1h_2) = \phi(ab) + 0' + 0' + 0' = \phi(ab)$

2. $R/H$ is a [[Ring]].
Since addition and multiplication of cosets are computed by choosing representatives, associative property of multiplication and the distribute law comes from the properties of $R$.

3. $\mu ((a+H)(b+H)) = \mu ((ab + H)) = \phi(ab) = \phi(a)\phi(b) = \mu(a+H)\mu(b+H)$
We already know that $\mu$ is [[Isomorphism]] on the additive part. We proved the homomorphism property of multiplicative part.

___

**EXAMPLE**)

* $\phi : \mathbb{Z} \rightarrow \mathbb{Z}_n$, $m \mapsto r$ where $r$ is the remainder of $m$ when divided by $n$.
$Ker(\phi) = n\mathbb{Z}$, so, $\mathbb{Z}/n\mathbb{Z}$ is a [[Ring]], where isomorphic to $\mathbb{Z}_n$.
