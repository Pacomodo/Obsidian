___

**THEOREM**)
Let $F$ be a [[Field|field]] and let $f(x) \in F[x]$ be a nonconstant polynomial.
Then $f(x)$ can be factored in $F[x]$ into a product of irreducible polynomials.
Furthermore, such irreducible polynomials are unique except for order and for units (that is, nonzero constant) factors in $F$.

___

**PROOF**)

1. **Existence of irreducible factorization of $f(x)$**
We use induction on $n = deg(f(x))$.
Note that if $f(x)$ is not irreducible over $F$, then $f(x) = g(x)h(x)$ where $g(x), h(x) \in F[x] - F$.
are such that $deg(g(x)) + deg(h(x)) = n$.
If $n = 1$, then $f(x)$ itself is irreducible over $F$.
Suppose that $n \geq 1$.
If $f(x)$ is not irreducible over $F$, then $f(x) = g(x)h(x)$ for some $g(x), h(x) \in F[x] - F$.
Since $deg(g(x)), deg(h(x)) < n$, it follows that $g(x)$ and $h(x)$ are respectively product of irreducible polynomials by induction hypothesis.

2. **Uniqueness of an irreducible factorization of $f(x)$**
Suppose that a nonconstant polynomial $f(x) \in F[x]$ is decomposed into $$p_1(x) \cdots p_s(x) = q_1(x) \cdots q_t(x)$$ where $p_i(x), q_j(x)$ are all irreducible polynomials.
Then, we have to show that $s = t$ and $p_1(x) \cdots p_s(x)$ is obtained by rearranging $q_1(x) \cdots q_t(x)$ and multiplying constants.

To this aim, we need a generalization of the following well-known fact:
	Corollary of Euclid's Lemma: If a prime number $p$ divides $ab$, then either $p|a$ or $p|b$.
Go to [[Thm 27.27]].

We suppose that there is the equality $p_1(x) \cdots p_s(x) = q_1(x) \cdots q_t(x)$ for irreducible polynomials.

Since $p_1(x)$ divides $q_1(x) \cdots q_t(x)$, by [[Thm 27.27]], $p_1(x)$ must divide $q_i(x)$ for some $1 \leq i \leq t$.
We may assume that $i=1$. Since $p_1(x)|q_1(x)$, $\left< q_1(x) \right> \subseteq \left< p_1(x) \right>$. Also, $q_1(x)$ and $p_1(x)$ are irreducible polynomial, so, $\left< q_1(x) \right>, \left< p_1(x) \right>$ are maximal ideals. Hence, $\left< q_1(x) \right> = \left< p_1(x) \right>$.
Therefore, $q_1(x) = c_1p_1(x)$ for some $c_1 \in F -\{0\}$.
By using induction, we can prove it.

___
