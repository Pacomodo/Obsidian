___

Give an example of a [[Ring homomorphism|ring homomorphism]] $\phi : R \rightarrow R'$ where $R$ has unity $1$ and $\phi (1) \neq 0'$, but $\phi (1)$ is not unity for $R'$.

___

**SOL**)
Consider $\phi : R_1 \rightarrow R_1 \times R_2$ where $a \mapsto (a, 0_{R_2})$.
1. $\phi(a+b) = (a + b, 0_{R_2}) = (a, 0_{R_2}) + (b, 0_{R_2}) = \phi(a) + \phi(b)$
2. $\phi(ab) = (ab, 0_{R_2}) = (a, 0_{R_2})(b, 0_{R_2}) = \phi(a) \phi(b)$
However, $\phi (1_{R_1}) = (1_{R_1}, 0_{R_2}) \neq (1_{R_1}, 1_{R_2})$. $\blacksquare$
