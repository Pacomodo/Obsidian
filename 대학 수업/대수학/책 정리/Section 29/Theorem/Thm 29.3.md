___

**THEOREM**) (Kronecker's Theorem)
Let $F$ be a field and let $f(x) \in F[x]$ and $f(x)$ be non-constant.
Then, there exists an extension field $E$ of $F$ and an $\alpha \in E$ such that $f(\alpha) = 0$.

___

**PROOF**)

1. Make extension field $E$ of $F$.

By [[Thm 23.20]], $f(x)$ has a fatorization in $F[x]$ into polynomials that are irreducible over $F$.
Let $p(x)$ be an irreducible polynomial in such a factorization.
Then, it is sufficient to find an extension field $E$ of $F$ containing an element $\alpha$ such that $p(\alpha) = 0$.
By [[Thm 27.25]], $\left< p(x) \right>$ is a maximal ideal in $F[x]$, so $F[x] / \left< p(x) \right>$ is a field.
We claim that $F$ can be identified with a subfield of $F[x] / \left< p(x) \right>$ in a natural way by use of the map $\psi : F \rightarrow F[x] / \left< p(x) \right>$ given by $$\psi (a) = a + \left< p(x) \right>$$
for $a \in F$.

* Claim : $\psi$ is 1-1 map.

If $\psi (a) = \psi (b)$, then, $a + \left< p(x) \right> = b + \left< p(x) \right>$ for some $a, b \in F$.
Then, $(a-b) \in \left< p(x) \right>$, so, $a - b$ must be a multiple of $p(x)$, which is degree $\geq 1$.
Since $a, b \in F$, $a - b \in F$. Thus, $a - b$ must be $0$. So, $a = b$.
We defined addition and multiplication in $F[x] / \left< p(x) \right>$ by choosing any representatives.
So, we can choose $a \in (a + \left< p(x) \right> )$.
Thus $\psi$ is a homomorphism that maps $F$ 1-1 and onto a subfield of $F[x] / \left< p(x) \right>$.
We can identify $F$ with $\{a + \left< p(x) \right> | a \in F\}$ by means of this map $\psi$.
Thus we shall view $E = F[x] / \left< p(x) \right>$ as an extension field of $F$.

2. Show that $E$ contains a zero of $p(x)$.

Let us set $$\alpha = x + \left< p(x) \right>$$
so, $\alpha \in E$.
Consider the [[Evaluation homomorphism|evaluation homomorphism]] $\phi_\alpha : F[x] \rightarrow E$, given by [[Thm 22.4]].
If $p(x) = a_0 + a_1x + \cdots + a_nx^n$, where $a_i \in F$, then we have $$\phi_\alpha(p(x)) = a_0 + a_1(x+\left< p(x)\right>) + \cdots + a_n(x + \left<p(x)\right>)^n \in E = F[x]/\left< p(x) \right>$$
Thus, $\phi_\alpha(p(x)) = (a_0 + a_1x + \cdots + a_nx^n) + \left<p(x)\right>$ $=$ $p(x) + \left<p(x)\right>$ $=$ $0_E$.
We found an element $\alpha \in E = F[x] / \left<p(x)\right>$ such that $p(\alpha) = 0$.
Therefore, $f(\alpha) = 0$.

___

**EXAMPLE**)

* Let $F = \mathbb{R}$ and $f(x) = x^2 + 1$. ^07fc3e

$f(x)$ has no zeros in $\mathbb{R}$, thus is irreducible over $\mathbb{R}$ by [[Thm 23.10]].
Then, $\left<x^2 + 1\right>$ is a [[Maximal ideal|maximal ideal]] in $\mathbb{R}[x]$, So, $\mathbb{R}[x] / \left< x^2 + 1 \right>$ is a field by [[Thm 27.25]].
Identifying $r \in \mathbb{R}$ with $r + \left< x^2 + 1 \right> \in \mathbb{R}[x] / \left< x^2 + 1\right>$.
Then, we can view $\mathbb{R}$ as a subfield of $E = \mathbb{R}[x] / \left< x^2 + 1 \right>$.
Let $\alpha = x + \left< x^2 + 1 \right>$.
Then, $\alpha ^2 + 1 = (x + \left< x^2 + 1 \right>)^2 + (1 + \left< x^2 + 1 \right>)$ $=$ $(x^2 + 1) + \left< x^2 + 1 \right>$ $=$ $0_E$.
Thus $\alpha$ is a zero of $x^2 + 1$.
We shall identify $E$ with $\mathbb{C}$. For more information, go to [[Thm 29.18]].

* Let $F = \mathbb{Q}$ and $f(x) = x^4 - 5x^2 + 6$.

$f(x)$ factors into $(x^2 - 2)(x^2 - 3)$. both factors are irreducible over $\mathbb{Q}$.
We can start with $x^2 - 2$ and construct an extension field $E$ of $\mathbb{Q}$ containing $\alpha$ such that $\alpha ^2 -2 = 0$, or, we can construct an extension field $K$ of $\mathbb{Q}$ containing an element $\beta$ such that $\beta ^2 - 3 = 0$.

___

As we said before, most of the rest of this text is devoted to the study of zeros of polynomials.
We commence this study by putting an element of an extension field $E$ of a field $F$ into one of two categories.
Go to [[Algebraic, transcendental]].