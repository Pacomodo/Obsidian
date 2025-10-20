___

Let $\sigma_m : \mathbb{Z} \rightarrow \mathbb{Z}_m$ be the natural homomorphism given by $\sigma_m(a) =$ (the remainder of $a$ when divided by $m$) for $a \in \mathbb{Z}$.

___

**a**. Show that $\overline{\sigma_m} : \mathbb{Z}[x] \rightarrow \mathbb{Z}_m[x]$ given by $$\overline{\sigma_m}(a_0 + a_1x + \cdots + a_nx^n) = \sigma_m(a_0) + \sigma_m(a_1)x + \cdots +\sigma_m(a_n)x^n$$is a homomorphism of $\mathbb{Z}[x]$ onto $\mathbb{Z}_m[x]$.

___

**SOL**)
Onto : Consider $c_0 + c_1x + \cdots + c_nx^n \in \mathbb{Z}_m[x]$, We know that $\overline{\sigma_m}(c_0 + c_1x + \cdots + c_nx^n) = c_0 + c_1x + \cdots + c_nx^n$.

Homomorphism property :
Consider $f(x) = a_0 + a_1x + \cdots + a_nx^n$, $g(x) = b_0 + b_1x + \cdots + b_mx^m \in \mathbb{Z}[x]$.
$\overline{\sigma_m}(f(x) + g(x)) = \sigma_m(a_0 + b_0) + \sigma_m(a_1 + b_1)x + \cdots +\sigma_m(a_m + b_m)x^m$
$= \sigma_m(a_0) + \sigma_m(b_0) + \sigma_m(a_1)x + \sigma_m(b_1)x + \cdots +\sigma_m(a_m)x^m + \sigma_m(b_m)x^m$
$= \overline{\sigma_m}(f(x)) + \overline{\sigma_m}(g(x))$
Similiarly, $\overline{\sigma_m}(f(x)g(x)) = \overline{\sigma_m}(f(x))\overline{\sigma_m}(g(x))$.

___

**b**. Show that if $f(x) \in \mathbb{Z}[x]$ and $\overline{\sigma_m}(f(x))$ both have degree $n$ and $\overline{\sigma_m}(f(x))$ does not factor in $\mathbb{Z}_m[x]$ into two polynomials of degree less than $n$, then $f(x)$ is irreducible in $\mathbb{Q}[x]$.

___

**SOL**)
We already know that by [[Thm 23.11]], it is enough to show that $f(x)$ is irreducible in $\mathbb{Z}[x]$.
Let $f(x) = a_nx^n + \cdots + a_0 \in \mathbb{Z}[x]$ where $a_n \neq 0$.
Since $\overline{\sigma_m}(f(x))$ has degree $n$, $\sigma_m(a_n) \neq 0 \implies m \nmid a_n$.
Suppose that $f(x)$ is reducible in $\mathbb{Z}[x]$ but $\overline{\sigma_m}(f(x))$ is irreducible.
Since $f(x)$ is reducible, we can factor $f(x)$ into two polynomials of degree less than $n$ in $\mathbb{Z}[x]$.
Let $f(x) = g(x)h(x)$ where $\deg(g(x)), \deg(h(x)) = r, s > 0$ and $r + s = n$.
Let $g(x) = b_rx^r + \cdots + b_0$, $h(x) = c_sx^s + \cdots + c_0$.
Since $m \nmid a_n = b_rc_s$, $m \nmid b_r$ and $m \nmid c_s$.
Since $\overline{\sigma_m}$ is homomorphism of $\mathbb{Z}[x]$ onto $\mathbb{Z}_m[x]$, $\overline{\sigma_m}(f(x)) = \overline{\sigma_m}(g(x)h(x)) = \overline{\sigma_m}(g(x))\overline{\sigma_m}(h(x))$.
Since $m$ does not divide $b_r$ and $c_s$, $\deg(\overline{\sigma_m}(g(x))) = r$ and $\deg(\overline{\sigma_m}(h(x)))=s$, which is contradiction to $\overline{\sigma_m}(f(x))$ does not factor in $\mathbb{Z}_m[x]$ into two polynomials of degree less than $n$.

___

**c**. Use part (b) to show that $x^3 +17x +36$ is irreducible in $\mathbb{Q}[x]$.

___

**SOL**)
Consider $\overline{\sigma_5}:\mathbb{Z}[x] \rightarrow \mathbb{Z}_5[x]$.
Then, $\overline{\sigma_5}(x^3 + 17x + 36) = x^3 + 2x + 1 \in \mathbb{Z}_5[x]$.
Let this polynomial $g(x)$. To $g(x)$ be reducible, $g(x)$ must have a linear factor.
However, $g(0) = 1$, $g(1) = 4$, $g(2) = 3$, $g(3) = 4$, $g(4) = 3$.
So, $g(x)$ does not have a linear factor. So, $g(x)$ is irreducible in $\mathbb{Z}_5[x]$, so it proved.


___
