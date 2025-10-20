___

**THEOREM**)
Let $E$ be an [[Extension field|extension field]] of $F$. Then $$\overline{F}_E = \{\alpha \in E \ | \ \alpha \textrm{ is algebraic over }F \}$$ is a subfield of $E$, the **algebraic closure of $F$ in $E$**.

___

**PROOF**)
Let $\alpha, \beta \in \overline{F}_E$.
Then [[Thm 31.11]] shows that $F(\alpha, \beta)$ is a finite extension of $F$, (why? thm 31.11의 증명과정을 봐라, 굳이 $E$와 같지 않아도 됨) and by [[Thm 31.3]] every element of $F(\alpha, \beta)$ is algebraic over $F$, that is, $F(\alpha, \beta) \subseteq \overline{F}_E$.
Thus $\overline{F}_E$ contains $\alpha + \beta, \alpha\beta, \alpha - \beta$ and also contains $\alpha / \beta$ for $\beta \neq 0$, so $\overline{F}_E$ is a subfield of $E$.

___
