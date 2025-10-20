___

**DEF**)
A field $E$ is extension field of a field $F$ if $F \leq E$.

___

![[Pasted image 20231106161247.png]]

Consider this diagram.
It will often be convinient to use subfield diagram to picture extension fields, the larger field being on top.
The left-hand side figure called a **tower of fields**.

___

For a given field $F$, its extension field $E$ has **more elements** than $F$.
Thus, an extension field is closed related to the problem of solving polynomial equations.
For example,
1. $f(x) = x^2 - 2 \in \mathbb{Q}[x]$ has no zeros in $\mathbb{Q}$ but it has two zeros $\pm \sqrt{2} \in \mathbb{R}$.
2. $f(x) = x^2 + 1 \in \mathbb{Q}[x]$ has no zeros in $\mathbb{Q}$ but it has two zeros $\pm i \in \mathbb{C}$.
Thus, a non-zero polynomial $f(x) \in \mathbb{Q}[x]$ which has no zeros in $\mathbb{Q}$, may have zeros in an extension field of $\mathbb{Q}$, such as $\mathbb{R}$ or $\mathbb{C}$.

___

**EXAMPLE**)

* Let $F = \mathbb{Q}$ and $f(x) = x^4 + x^3 + x^2 + x + 1 \in \mathbb{Q}[x]$.

Since $(x-1) \times f(x) = x^5 - 1$, we know that $$\zeta = \mathrm{cos}(\frac{2\pi}{5}) + i\mathrm{sin}(\frac{2\pi}{5}), \zeta ^2 , \zeta ^3, \zeta ^ 4$$
are zeros of $x^5 - 1$.
We know that $\zeta , \zeta ^2, \zeta ^3, \zeta ^4$ are not equal to $1$.
So, $f(\zeta) = f(\zeta ^2) = f(\zeta ^3) = f(\zeta ^4) = 0$, so, they are zeros of $f(x)$.
Since $f(x)$ is of degree $4$ and they are distinct, they are all zeros of $f(x)$ in $\mathbb{C}$.
and $$f(x) = (x-\zeta)(x-\zeta ^2)(x-\zeta ^3)(x-\zeta ^4) \in \mathbb{C}[x].$$
In particular, the extension field $\mathbb{C}$ of $\mathbb{Q}$ contains zeros of $f(x)$.

* Let $F = \mathbb{Z} _2$ and $f(x) = x^2 + x + 1 \in \mathbb{Z}_2[x]$.

$f(x)$ has no zeros in $\mathbb{Z}_2$. Consider $f(0) = f(1) = 1$. ([[Thm 23.10]])
To find a zero of $f(x)$, we need an extension field of $\mathbb{Z}_2$.
$\Rightarrow$ (Kronecker's Idea)
Since $f(x)$ is of degree $2$ and has no zeros in $\mathbb{Z}_2$, it is an irreducible polynomial in $\mathbb{Z}_2[x]$. (By [[Thm 23.10]])
Then, $\left< f(x) \right>$ is a [[Maximal ideal|maximal ideal]] of $\mathbb{Z}_2[x]$ and hence $E = \mathbb{Z} [x] / \left< f(x) \right>$ is a [[Field|field]]. (By [[Thm 27.25]] and [[Thm 27.9]])
Moreover, the subset $\{0_E = 0+\left< f(x) \right> , 1_E = 1+\left< f(x) \right> \}$ of $E$ is isomorphic to $\mathbb{Z}_2$.
Also, $\alpha = x + \left< f(x) \right>$ is a zero of $f(x)$.
Because, $f(\alpha)$ $=$ $(x + \left< f(x) \right>)^2$ $+$ $(x + \left< f(x) \right> )$ $+$ $(1 + \left< f(x) \right>)$ $=$ $(x^2 + x + 1) + \left< f(x) \right>$ $=$ $0 + \left< f(x) \right>$ $=$ $0_E$.
In particular, there exists an extension field $E$ of $F$ which contains a zero of $f(x) = x^2 + x + 1$.
Go to [[Thm 29.3]].