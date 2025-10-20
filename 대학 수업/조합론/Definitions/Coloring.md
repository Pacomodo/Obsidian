___

**DEF**) A graph coloring (or proper vertex coloring) of $G = (V, E)$ is a graph with $f : V \rightarrow \{ \textrm{colors} \}$ (Called "vertex labeling") such that for any two adjacent vertices $x$ and $y$, $f(x) \neq f(y)$.

___

![[Pasted image 20231010005341.png]]
If there is a loop in graph $G$, there is no proper coloring on $G$.

![[Pasted image 20231010005521.png]] 
Also, in case of multiple edges, this multiple edges does not concern with vertex coloring.

If two graph $G_1, G_2$ are not connected, there is no two adjacent vertices with $G_1, G_2$ .

![[Pasted image 20231010005958.png]]

Hence, it is enough to consider a simple connected graph.

---

**DEF**) A (proper) edge coloring of $G = (V, E)$ is a graph with $g : E \rightarrow \{ \textrm{colors} \}$ (Called "edge labeling") such that if $e_1