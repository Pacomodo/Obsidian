___

**THEOREM**) **(The Evaluation Homomorphism for Field Theory)**
Let $F$ be a subfield of a field $E$. Let $\alpha \in E$. Let $x$ be an indeterminate.
The map $\phi_\alpha : F[x] \rightarrow E$ defined by $$\phi_\alpha (a_0 + a_1x + \cdots + a_n x^n) = a_0 + a_1 \alpha + \cdots + a_n \alpha ^n$$
for $(a_0 + a_1x + \cdots + a_n x^n) \in F[x]$ is a homomorphism of $F[x]$ into $E$.
Also, $\phi _\alpha (x) = \alpha$, and $\phi _\alpha$ maps $F$ isomorphically by the identity map, that is, $\phi _\alpha (a) = a$ for $a \in F$.
We call $\phi_\alpha$ is evaluation at $\alpha$.

___

**PROOF**)

![[Pasted image 20231109002603.png]]

Figure 22.5 visualize this situation.
1. The map $\phi_\alpha$ is well-defined map.
It means, it does not matter how we represent $f(x) \in F[x]$.
$f(x)$ can be represented as a finite sum of the form $$a_0 + a_1x + \cdots + a_n x^n$$
and $f(x)$ can be represented differently by insert or delete of terms $0x^i$.
However, it does not affect the value of $\phi_\alpha (f(x))$.
2. $\phi_\alpha$ has homomorphism property.
Let $f(x) = a_0 + a_1x + \cdots + a_n x^n$, $g(x) = b_0 + b_1 x + \cdots + b_m x^m$, and $h(x) = f(x) + g(x) = c_0 + c_1x + \cdots + c_r x^r$.
Then, $$\phi_\alpha(f(x) + g(x)) = \phi_\alpha(h(x)) = c_0 + c_1\alpha + \cdots + c_r \alpha ^r$$
$$\phi_\alpha(f(x)) + \phi_\alpha(g(x)) = (a_0 + a_1\alpha + \cdots + a_n\alpha^n) + (b_0 + b_1\alpha + \cdots + b_m\alpha^m)$$

By definition of polynomial addition, we know that $c_i = a_i + b_i$, So, $$\phi_\alpha(f(x) + g(x)) = \phi_\alpha(f(x)) + \phi_\alpha(g(x))$$
Similarly, we can do this on polynomial multiplication.
Using the definition of polynomial multiplication $d_j = \sum_{i=0}^{j}a_ib_{j-i}$, we can see that $$\phi_\alpha(f(x)g(x)) = [\phi_\alpha(f(x))][\phi_\alpha(g(x))]$$.

By (1) and (2), $\phi_\alpha$ is a homomorphism.
Think about $\phi_\alpha$ applied to a constant polynomial $a \in F[x]$.
It gives $\phi_\alpha(a) = a$, so, $\phi_\alpha$ maps $F$ isomorphically by the identity map.
Again, $\phi_\alpha (x) = \phi_\alpha(1x) = 1\alpha = \alpha$.

___

Note that this theorem is also valid with if $F$ and $E$ are merely commutative rings with unity.
This theorem is very very very **IMPORTANT**.

**EXAMPLE**)

* Let $F = \mathbb{Q}$ and $E = \mathbb{R}$.

Consider the evaluation homomorphism $\phi_0 : \mathbb{Q}[x] \rightarrow \mathbb{R}$.
Here, $$\phi_0(a_0 + a_1 x + \cdots + a_nx^n) = a_0 + a_10 + \cdots + a_n0^n = a_0$$
Thus, every polynomial is mapped onto its constant term.

* Let $F = \mathbb{Q}$ and $E = \mathbb{R}$.

Consider the evaluation homomorphism $\phi_2 : \mathbb{Q}[x] \rightarrow \mathbb{R}$.
Here, $$\phi_2 (a_0 + a_1x + \cdots + a_n x^n) = a_0 + a_1 2 + \cdots + a_n 2^n$$
Note that $\phi_2(x^2 + x - 6) = 2^2 + 2 - 6 = 0$.
Thus $x^2 + x - 6$ is in the kernel $N$ of $\phi_2$.
$x^2 + x - 6 = (x-2)(x+3)$, So, the reason that $\phi_2(x^2+x-6) = 0$ is that $\phi_2(x-2) = 2-2 = 0$.

* Let $F = \mathbb{Q}$ and $E = \mathbb{C}$.

Consider the evaluation homomorphism $\phi_i : \mathbb{Q}[x] \rightarrow \mathbb{C}$.
Here, $$\phi_i(a_0 + a_1x + \cdots + a_nx^n) = a_0 + a_1i + \cdots + a_ni^n$$
and $\phi_i(x) = i$.
Note that $\phi_i (x^2 + 1) = i^2 + 1 = 0$, so, $x^2 + 1$ is in the kernel $N$ of $\phi_i$.

* Let $F = \mathbb{Q}$ and $E = \mathbb{R}$.

Consider the evaluation homomorphism $\phi_\pi : \mathbb{Q}[x] \rightarrow \mathbb{R}$.
Here, $$\phi_\pi(a_0 + a_1x + \cdots + a_nx^n) = a_0 + a_1\pi + \cdots + a_n\pi^n$$
It can be proved that $a_0 + a_1\pi + \cdots + a_n\pi^n = 0$ $\iff$ $a_i = 0$ for $i = 0, 1, \cdots, n$.
Thus the kernel of $\phi_\pi = \{0\}$ and $\phi_\pi$ is 1-1 map.
This shows that all *formal polynomials in $\pi$ with rational coefficients* form a ring that is isomorphic to $\mathbb{Q}[x]$ in a natural way with $\phi_\pi(x) = \pi$. (Because kernel is zero)

___

