___

**THEOREM**) (Fundamental Homomorphism Theorem; Analogue of [[Thm 14.11]])
Let $\phi : R \rightarrow R'$ is a [[Ring homomorphism|ring homomorphism]] with [[대학 수업/대수학/책 정리/Section 26/Definition/Kernel|kernel]] $N$.
Then, $\phi [R]$ is a [[Ring|ring]]. and the map $\mu : R/N \rightarrow \phi[R]$ where $(x+N) \mapsto \phi(x)$ is an isomorphism.
and $\gamma : R \rightarrow R/N$ where $x \mapsto (x+N)$ is the homomorphism and for all $x \in R$, $\phi(x) = \mu \gamma (x)$

___

**PROOF**)
Recall that [[Thm 26.7]] and [[Thm 26.16]].
![[Pasted image 20231011211658.png]]
See this figure.

___

**EXAMPLE**)

* See [[Ideal|ideal]] Examples. $n\mathbb{Z}$ is an ideal of $\mathbb{Z}$. so we can form a [[Factor ring|factor ring]] $\mathbb{Z}/n\mathbb{Z}$.
We see that $\phi : \mathbb{Z} \rightarrow \mathbb{Z}_n$ where $m \mapsto m\textrm{ mod }n$ is a [[Ring homomorphism|ring homomorphism]]. and we see that $Ker(\phi) = n\mathbb{Z}$.
[[Thm 26.17]] say that $\mu : \mathbb{Z}/n\mathbb{Z} \rightarrow \mathbb{Z}_n$ where $(m + n\mathbb{Z}) \mapsto m \textrm{ mod } n$ is an isomorphism.

___

In summary, every [[Ring homomorphism|ring homomorphism]] with domain $R$ with [[대학 수업/대수학/책 정리/Section 26/Definition/Kernel|kernel]] $N$, gives a [[Factor ring|factor ring]] $R/N$.
And every factor ring $R/N$ gives homomorphism $R \rightarrow R/N$.

We append more on this theorem.
Let $\phi : R \rightarrow R'$ be a homomorphism. let $N$ be an ideal of $R$. Then $\phi[N]$ is an ideal of $\phi[R]$.
Note that it need not to be an ideal of $R'$.
Also, if $N'$ is an ideal of either $\phi[R]$ or $R'$, then $\phi^{-1}[N']$ is an ideal of $R$.
Go to [[Exercise 22]].