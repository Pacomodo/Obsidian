___

For a commutative ring $R$ with unity, show that the relation $a \sim b$ if $a$ is an [[associate]] of $b$ is an equivalence relation on $R$.

___

**SOL**)
(1) $a \sim a$ for all $a \in R$.
Since $1$ is [[Unit|unit]] in $R$, $a = a \cdot 1$.

(2) If $a \sim b$, then $b \sim a$ for all $a, b \in R$.
Since $a \sim b$, $\exists u \in R$ where $u$ is unit such that $a = bu$.
Since $u$ has inverse, $a(1/u) = b$, so, $b \sim a$.

(3) If $a \sim b$ and $b \sim c$, then $a \sim c$.
Since $a \sim b$, $\exists u$ such that $a = bu$.
$b \sim c$, $\exists v$ such that $b = cv$.
so, $a = (cv)u = c(uv)$. Since $uv$ has inverse $u^{-1}v^{-1}$, so, $a \sim c$.