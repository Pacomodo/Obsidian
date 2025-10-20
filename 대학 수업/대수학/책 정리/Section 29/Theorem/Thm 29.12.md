___

**THEOREM**)
Let $E$ be an [[Extension field]] of a field $F$. Let $\alpha \in E$.
Let $\phi_\alpha : F[x] \rightarrow E$ be the [[Evaluation homomorphism]] of $F[x]$ into $E$ such that $\phi_\alpha(a) = a$ for $a \in F$ and $\phi_\alpha(x) = \alpha$.
Then, $\alpha$ is [[Algebraic, transcendental|transcendental]] over $F$ $\iff$ $\phi_\alpha$ gives an isomorphism of $F[x]$ with a subdomain of $E$ $\iff$ $\phi_\alpha$ is 1-1.

___

**PROOF**)
The element $\alpha$ is [[Algebraic, transcendental|transcendental]] over $F$
$\iff$ $f(\alpha) \neq 0$ for all nonzero $f(x) \in F[x]$.
$\iff$ $\phi_\alpha(f(x)) \neq 0$ for all nonzero $f(x) \in F[x]$.
$\iff$ $Ker(\phi_\alpha) = \{0\}$.
$\iff$ $\phi_\alpha$ is 1-1.

___

Consider the extension field $\mathbb{R}$ of $\mathbb{Q}$.
We know that $\sqrt{2}$ is algebraic over $\mathbb{Q}$, being a zero of $x^2 - 2$.
Of course, $\sqrt{2}$ is also a zero of $x^3 - 2x$ and of $x^4 - 3x^2 + 2 = (x^2-2)(x^2-1)$.
Both these other polynomials having $\sqrt{2}$ as a zero were multiples of $x^2 - 2$.
The next theorem shows that this is an illustration of a general situation.
This theorem plays a centeral role in our later work.
Go to [[Thm 29.13]].