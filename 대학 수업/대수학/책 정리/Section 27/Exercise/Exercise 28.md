___

Prove directly from the definitions of [[Maximal ideal|maximal]] and [[Prime ideal|prime]] ideals that every maximal ideal of a commutative ring $R$ with unity is a prime ideal.

___

**PROOF**)
Let $M$ is maximal ideal in commutative ring $R$ with unity.
We want to show that if $ab \in M$ then either $a \in M$ or $b \in M$.
Suppose $ab \in M$ and $a \notin M$. We want to show that $b \in M$.
Consider $N = \{ ra+m | r\in R, m \in M\}$.

* Claim : $N$ is an ideal that contains $a$ and strictly larger than $M$.
1. $M \subseteq N$ and $a \in N$, so, $M \subsetneq N$.
If we take $r = 0$ then $M \subseteq N$. Also, if we take $r = 1, m = 0$, then, $a \in N$.
2. $N$ is an ideal.
Take $s \in R$. $sra + sm = r(sa) + (sm) \in N$. So, $N$ is an ideal.

By claim and $M$ is maximal, $N = R$. So, $1 \in N$.
So, there exists $r \in R$ and $m \in M$, such that $ra + m = 1$.
So, $rab + mb = b$. Since $ab \in M$, so, $rab \in M$. Also, $mb \in M$. so, $b \in M$.

____
