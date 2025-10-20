___

**THEOREM**) (Analogue of [[Thm 15.18]])
Let $R$ be a commutative [[Ring|ring]] with unity.
Then, $M$ is a [[Maximal ideal|maximal ideal]] of $R$ $\Leftrightarrow$ $R/M$ is a [[Field|field]].

___

**PROOF**)
$(\Rightarrow)$ We want to show that $R/M$ is a field. i.e. for arbitrary element of $R/M$, there is multiplicative inverse in $R/M$.
Take $(a + M) \in R/M$ where $a \notin M$ so that $(a+M)$ is not the additive identity.
We want to show that for $(a+M) \in R/M$, there is $(r+M) \in R/M$ such that $(a+M)(r+M) = (1 + M)$.
Consider $N = \{ar + m | r \in R, m \in M\} \subset R$.
We want to show that $N$ is [[Ideal|ideal]] of $R$ such that strictly larger than $M$.
It is obvious that $a+m \notin M$ since $a \notin M$. so, $M \subsetneq N$.
Pick $s \in R$. $s(ar+m) = sar+sm = asr + sm$ and $sm \in M$ and $sr \in R$, so, this element in $N$.
Therefore, $N$ is ideal of $R$, but $M$ is a maximal ideal of $R$, so, $N = R$.
Hence $1 \in N$, so, $1 = ar + m$ for some $r \in R$ and $m \in M$.
Then, $(1+M) = (ar + m) + M = (ar) + M = (a+M)(r+M)$, so, $(a+M)$ is a unit.

$(\Leftarrow )$ It is enough to show that if $N$ is an [[Ideal|ideal]] of $R$ such that $M \subsetneq N \subseteq R$, then, $N = R$.
Pick $a \in N - M$. Then, $a \notin M$, so, $(a+M) \neq M$. so, $(a+M) \in R/M$ is nonzero element, so, $(a+M)$ has inverse.
Let this inverse $(b+M) \in R/M$. then, $(a+M)(b+M) = 1+M = ab+M$.
So, $ab - 1 \in M \subset N$. $N$ contains $a$ and $N$ is [[Ideal|ideal]], $ab \in N$. 
Therefore, $ab - (ab - 1) = 1 \in N$ (because $N$ is additive subgroup), so, by [[Thm 27.5]], $N = R$.

___

**EXAMPLE**)

* Since $\mathbb{Z}/n\mathbb{Z} \cong \mathbb{Z}_n$ and $\mathbb{Z}_n$ is a field if and only if $n$ is a prime by [[Cor 19.12]], we see that the [[Maximal ideal|maximal ideal]]s of $\mathbb{Z}$ are precisely the [[Ideal|ideal]]s $p\mathbb{Z}$ for $p$ is prime.