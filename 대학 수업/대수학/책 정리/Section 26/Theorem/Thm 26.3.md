___

**THEOREM**) (Analogue of [[Thm 13.12]])
Let $\phi : R \rightarrow R'$ is a [[Ring homomorphism|ring homomorphism]].
1. If $0$ is the additive identity in $R$, then $\phi (0)$ is the additive identity in $R'$.
2. If $a \in R$, then $\phi (-a) = - \phi(a)$.
3. If $S \leq R$, then $\phi [S] \leq R'$.
4. If $S' \leq R'$, then $\phi ^{-1} [S']\leq R$.
5. If $R$ has unity $1$, then $\phi (1)$ is unity in $\phi[R]$.

___

**PROOF**)

(1 and 2)
We can view $\phi$ as a [[Group homomorphism|group homomorphism]] of $\left< R, + \right> \rightarrow \left< R', + \right>$.
By [[Thm 13.12]], it is true.

(3)
Since we can view $\phi$ as a [[Group homomorphism]] of $\left< R, + \right> \rightarrow \left< R', + \right>$, consider only multiplication.
If $\phi(s_1), \phi (s_2) \in \phi [S]$, then, $\phi (s_1) \phi (s_2) = \phi (s_1 s_2) \in \phi[S]$ because $\phi$ is [[Ring homomorphism]].
Therefore, $\phi [S]$ is closed under multiplication.
Associativity and left/right distribute law comes from immediately $R'$ is [[Ring]].

(4)
Since we can view $\phi$ as a [[Group homomorphism]] of $\left< R, + \right> \rightarrow \left< R', + \right>$, consider only multiplication.
If $a, b \in \phi ^{-1}[S']$, then $\phi (a), \phi (b) \in S'$. Because $S'$ is closed under multiplication and $\phi$ is [[Ring homomorphism]], $\phi (a) \phi (b) = \phi (ab) \in S'$, so, $ab \in \phi ^{-1} [S']$. Therefore, $\phi ^{-1} [S']$ is closed under multiplication.
Associativity and left/right distribute law comes from immediately $R$ is [[Ring]].

(5)
$\phi(1)\phi(a) = \phi(1a) = \phi(a) = \phi(a1) = \phi(a)\phi(1)$, so, $\phi(1)$ is unity for $\phi[R]$.

==Note that $\phi(1)$ is not unity for $R'$==.
Go to [[대학 수업/대수학/책 정리/Section 26/Exercise/Exercise 9|Exercise 9]].