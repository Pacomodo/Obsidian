___
위에서 구한 모양 연산자의 행렬표현에 대해, 다음 두 값을 구해봅시다. 
1. 행렬식 determinant
2. 대각합 trace
___
Note that the matrix representation of the shape operator $\mathcal{S}:T_{p}S \to T_{p}S$ is
$$
\mathcal{M} = \begin{pmatrix}
E & F \\
F & G
\end{pmatrix}^{-1}\begin{pmatrix}
L & M \\
M & N
\end{pmatrix}
$$

> [!Recall] Property of Determinant
> 1. $\det(AB) = \det(A)\det(B)$
> 2. $\det(A^{-1}) = \frac{1}{\det(A)}$

So, $\det(\mathcal{M}) = \frac{LN-M^{2}}{EG-F^{2}}$.
Note that $\det(\mathcal{M}) = \prod\lambda$.
$$
\begin{align}
\mathrm{Tr}(\mathcal{M}) &= \mathrm{Tr}(\begin{pmatrix}
E & F \\
F & G
\end{pmatrix}^{-1}\begin{pmatrix}
L & M \\
M & N
\end{pmatrix}) \\
&=\frac{1}{EG - F^{2}}\mathrm{Tr}(\begin{pmatrix}
G & -F \\
-F & E
\end{pmatrix}\begin{pmatrix}
L & M \\
M & N
\end{pmatrix}) \\
&= \frac{GL - FM - FM + EN}{EG-F^{2}} \\
&= \frac{GL+EN-2FM}{EG-F^{2}}
\end{align}
$$
Note that $\mathrm{Tr}(\mathcal{M}) = \sum\lambda$.
___
