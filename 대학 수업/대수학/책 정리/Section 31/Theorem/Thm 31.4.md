___

**THEOREM**) (Analogue to Lagrange Theorem) **VERY IMPORTANT**
If $E$ is a [[Finite extension|finite extension]] field of a [[Field|field]] $F$, and $K$ is a finite extension field of $E$, Then $K$ is finite extension field of $F$ such that $$[K:F] = [K:E][E:F]$$
![[Pasted image 20231127112619.png]]
____

**PROOF**)
Let $\{\alpha_1, \alpha_2, \cdots, \alpha_n\}$ be a basis for $E$ as a vector space over $F$.
Let $\{\beta_1, \beta_2, \cdots, \beta_m\}$ be a basis for $K$ as a vector space over $E$.
We want to show that $mn$ elements of $\alpha_i \beta_j$ form a basis for $K$ over $F$.
1. $\alpha_i\beta_j$ spans $K$ over $F$.

Let $\gamma \in K$. Since $\beta_j$ form a basis for $K$ over $E$, $$\gamma = \sum_{j=1}^{m}b_j\beta_j$$for $b_j \in E$.
Since $\alpha_i$ form a basis for $E$ over $F$,
$$\beta_j = \sum_{i=1}^{n}a_i\alpha_i$$where $a_i \in F$.
Therefore, $$\gamma = \sum_{j=1}^{m}\left(\sum_{i=1}^{n}a_i\alpha_i\right)\beta_j = \sum_{i, j}a_{ij}(\alpha_i\beta_j)$$, So, $mn$ vectors of $\alpha_i\beta_j$ span $K$ over $F$.

2. $\alpha_i\beta_j$ are [[Linearly dependent, independent|linearly independent]] over $F$.

Suppose $\sum_{i, j} a_{ij}(\alpha_i\beta_j) = 0$ with $a_{ij} \in F$. It is enough to show that all $a_{ij} = 0$.
$$\sum_{i,j}a_{ij}(\alpha_i\beta_j) = \sum_{j=1}^m \left( \sum_{i=1}^n a_i\alpha_i\right)\beta_j = 0$$and $\beta_j$ is linearly independent over $E$, so, all $\sum_{i=1}^na_i\alpha_i = 0$.
Also, $\alpha_i$ is linearly indepent over $F$, so, all $a_{ij}$ have to be $0$.

By (1) and (2), $\alpha_i \beta_j$ form a basis $K$ over $F$.

___

