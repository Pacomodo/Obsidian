___

Let $\phi : R \rightarrow R'$ be a [[Ring homomorphism|ring homomorphism]] and let $N$ be an [[Ideal|ideal]] of $R$.

(a) Show that $\phi[N]$ is an ideal of $\phi[R]$.
(b) Give an example to show that $\phi[N]$ need not to be an ideal of $R'$.
(c) Let $N'$ be an ideal either of $\phi[R]$ or of $R'$. Show that $\phi^{-1}[N']$ is an ideal of $R$.

___

**PROOF**)
(a) Pick $a \in N$ and $r \in R$. then, $\phi(a) \in \phi[N]$ and $\phi(r) \in \phi[R]$.
$\phi(a)\phi(r) = \phi(ar)$ since $\phi$ is homomorphism.
Also, $ar \in N$ since $N$ is ideal of $R$. Therefore, $\phi(a)\phi(r) \in \phi[N]$.
Similarly, we can do this on $\phi(r)\phi(a)$. Therefore, $\phi[N]$ is an ideal of $\phi[R]$.

(b) 

(c) Pick $a \in \phi^{-1}[N']$ and $r \in R$. We want to show that $ar \in \phi^{-1}[N']$. i.e. $\phi(ar) \in N'$.
$\phi(ar) = \phi(a)\phi(r)$ since $\phi$ is homomorphism.
We know that $N'$ is an ideal of $\phi[R]$ or R' and $\phi(a) \in N', \phi(r) \in \phi[R] \subset R'$, so, $\phi(a)\phi(r) \in N'$. Hence, $\phi(ar) \in N'$.
We can do this on $\phi(r)\phi(a)$ in the same manner.