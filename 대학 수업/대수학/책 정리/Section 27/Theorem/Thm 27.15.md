___

**THEOREM**)
Let $R$ be a commutative [[Ring|ring]] with unity. Let $N \neq R$ be an ideal in $R$.
Then $R/N$ is [[Integral Domain|integral domain]] $\Leftrightarrow$ $N$ is a [[Prime ideal|prime ideal]] in $R$.

___

$(\Rightarrow)$ We want to show that $N$ is a prime ideal in $R$.
Consider $(ab + N) \in R/N$ and assume that $ab \in N$. Then, $(ab + N) = (a+N)(b+N) = (0+N)$. Since $R/N$ is integral domain, either $(a+N)$ or $(b+N)$ must be $(0+N)$, so, either $a \in N$ or $b \in N$.

$(\Leftarrow)$ We want to show that $R/N$ is integral domain.
Consider $(a+N) \in R/N$ and $(b+N) \in R/N$ such that $(a+N)(b+N) = (0+N) = (ab + N)$. Since $N$ is prime ideal in R, either $a \in N$ or $b \in N$.
Therefore, either $(a+N) = (0+N)$ or $(b+N) = (0+N)$. So, there is no [[Divisors of 0|zero divisor]] in $R/N$.

___
