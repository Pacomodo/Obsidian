___

**THEOREM**) (**Eisenstein Criterion**)
Let $p \in \mathbb{Z}$ be a prime.
Suppose that $f(x) = a_n x^n + \cdots + a_0$ is in $\mathbb{Z}[x]$.
If $a_n \not\equiv 0 \ ( \mathrm{mod} \ p)$, $a_i \equiv 0 \ ( \mathrm{mod} \ p)$ for all $0 \leq i < n$ and $a_0 \not\equiv 0 \ ( \mathrm{mod} \ p^2)$, then $f(x)$ is irreducible over $\mathbb{Q}$.

___

**PROOF**)
By [[Thm 23.11]], we only need to show that $f(x)$ does not factor into polynomials in $\mathbb{Z}[x]$ of lower degree.
Suppose not. Then, $$f(x) = (b_rx^r + \cdots + b_0)(c_sx^s + \cdots + c_0)$$ is a factorization of $f(x)$ in $\mathbb{Z}[x]$ with $b_r \neq 0, c_s \neq 0$ and $r, s < n$.
Then, $a_n \not\equiv 0 \ (\textrm{mod } p) \implies b_r \not\equiv 0 (\textrm{mod } p) \wedge c_s \not\equiv 0 \ (\textrm{mod } p)$.
Also, $a_0 \not\equiv 0 \ (\textrm{mod } p^2) \implies \neg(b_0 \equiv 0 \ (\textrm{mod } p)\wedge c_0 \equiv 0 \ (\textrm{mod } p))$.
We know that $a_0 \equiv 0 \ (\textrm{mod }p)$, so, $b_0 \not\equiv 0 \ (\textrm{mod }p) \wedge c_0 \not\equiv 0 \ (\textrm{mod }p)$ is impossible.
So, suppose that $b_0 \not\equiv 0 \ (\textrm{mod } p)$ and $c_0 \equiv 0 \ (\textrm{mod } p)$.

Let $m$ be the **smallest** positive integer such that $c_m \not\equiv 0 \ (\textrm{mod }p)$.
Then, $$a_m = b_0c_m + b_1c_{m-1} + \cdots + \left\{\begin{matrix}
b_mc_0 \textrm{ if }r \geq m\\ b_rc_{m-r} \textrm{ if }r < m
\end{matrix}\right.$$
By assumption, $b_0 \not\equiv 0 \ (\textrm{mod } p)$ and $c_m \not\equiv 0 \ (\textrm{mod }p)$.
However, we know that $c_{m-1}, \cdots, c_0 \equiv 0 \ (\textrm{mod }p)$. It means $a_m \not\equiv 0 \ (\textrm{mod }p) \implies m = n$.
So, $s \geq m = n$, which contradicts to $s < n$.

___

**EXAMPLE**)

* $x^2 - 2 \in \mathbb{Q}[x]$. We can take $p = 2$.

* $25x^5 -9x^4 -3x^2 -12 \in \mathbb{Q}[x]$. We can take $p = 3$.

___
