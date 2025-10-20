___

**THEOREM**)
Let $G$ be a simple plane graph. Then (the average 'vertex degree' of $G$) $< 6$.

___

**PROOF)**
![[Pasted image 20231010042920.png]]
If $|E| = 1$, the average degree of graph $G$ is $1$.

So, suppose that $|E| \geq 2$.
It is obvious that the smallest vertex degree $\delta$ of $G$ is smaller than the average vertex degree.
By [[Thm) Handshaking lemma]] and [[Thm) Relation of v, e, f in plane graph]],
$$\delta \leq \textrm{(average vertex degree)} =  \frac{\sum_{v \in V} deg(v)}{|V|} = \frac{2|E|}{|V|} \leq \frac{2(3|V|-6)}{|V|} = 6 -\frac{12}{|V|} < 6$$
___
