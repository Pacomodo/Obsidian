___

**THEOREM**) (Analogue of  [[Thm 14.4]])
Let $H \leq R$ where $R$ is a ring.
Then, Multiplication of additive [[Coset|coset]]s of $H$ is well-defined $\iff$ $ah \in H$ and $hb \in H$ for all $a, b \in R$ and $h \in H$.

___

**PROOF**)
$(\Rightarrow )$ Consider the coset multiplication $(a+H)H$. Choosing representative $a \in (a+H)$ and $0 \in H$.(We can choose $0$ because $H$ is subring of $R$.)
Then, $a0 = 0 \in H$, so, $(a + H)H = H$. Because the coset multiplication is well-defined, $ah \in H$ for all $h \in H$. Similarly, we can argue that $hb \in H$ for all $h \in H$.

($\Leftarrow$) Let $h_1, h_2 \in H$. Choose the representative $a+h_1$ of the coset $a + H$ and $a + h_2$ of the coset $b+h_2$.
Then, $(a+h_1)(b+h_2) = ab + ah_2 + h_1b + h_1h_2$.
Because $ah_2, h_1b, h_1h_2 \in H$ and $H$ is subring, $(a+h_1)(b+h_2) \in (ab + H)$.

___

From now on, we will call this structure as "[[Ideal]]".