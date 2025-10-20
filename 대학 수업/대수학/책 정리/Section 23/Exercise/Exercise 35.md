___

If $F$ is a [[Field|field]] and $a \neq 0$ is a zero of $f(x) = a_0 + a_1x + \cdots + a_nx^n \in F[x]$, show that $1/a$ is a zero of $a_n + a_{n-1}x + \cdots + a_0x^n$.

___

**SOL**)
Consider the evaluation homomorphism $\phi_a : F[x] \rightarrow F$.
We know that $a$ is a zero of $f(x)$, so, $a_0 + a_1a + \cdots + a_na^n = 0 \in F$.
Multiplying $(1/a)^n$ on both side.
Then, $a_n + a_{n-1}(1/a) + \cdots + a_0(1/a)^n = 0$.
So, Consider the evaluation homomorphism $\psi_{1/a} : F[x] \rightarrow F$.
Since $a_n + a_{n-1}(1/a) + \cdots + a_0(1/a)^n = 0$, we can show that $a_n + a_{n-1}x + \cdots + a_0x^n \in Ker(\psi _{1/a})$.

___
