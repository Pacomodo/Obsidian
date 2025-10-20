The Lindström–Gessel–Viennot lemma provides a way to count the number of tuples of non-intersecting lattice paths, or more generally, paths on a directed graph.
It was proved by Gessel–Viennot in 1985, based on previous work of Lindström published in 1973.

* Statement

Let $G$ be a locally finite directed acyclic graph.
This means that each vertex has finite degree, and that $G$ contains no directed cycles.
Consider base vertices $A = \{a_1, \cdots, a_n\}$ and destination vertices $B = \{b_1, \cdots, b_n\}$, and also assign a weight $w_e$ to each directed edge $e$.
These edge weights are assumed to belong to some commutative ring.
For each directed path $P$ between two vertices, let $w(P)$ be the product of the weights of the edges of the path.
For any two vertices $a$ and $b$, write $e(a,b)$ for the sum $$e(a, b) = \sum_{P:a\rightarrow b}w(P)$$ over all paths from $a$ to $b$.

This is well-defined if between any two points there are only finitely many paths.
But even in the general case, this can be well-defined under some circumstances.
(Such as all edge weights being pairwise distinct formal indeterminates, and $e(a,b)$ being regarded as a fomal power series.)
If one assigns the weight $1$ to each edge, then $e(a,b)$ counts the number of paths from $a$ to $b$.

With this setup, write $$M = \begin{pmatrix}e(a_1,b_1)&e(a_1,b_2)&\cdots&e(a_1, b_n)\\e(a_2, b_1)&e(a_2,b_2)&\cdots&e(a_2,b_n)\\
\vdots&\vdots&\ddots&\vdots\\e(a_n,b_1)&e(a_n,b_2)&\cdots&e(a_n,b_n)\end{pmatrix}$$
An $n$-tuple of non-intersecting paths from $A$ to $B$ means an $n$-tuple $(P_1, \cdots, P_n)$ of paths in $G$ with the following properties:
* There exists a permutation $\sigma$ of $\{1, 2, \cdots, n\}$ such that, for every $i$, the path $P_i$ is a path from $a_i$ to $b_{\sigma(i)}$.
* Whenever $i \neq j$, the paths $P_i$ and $P_j$ have no two vertices in common (not even endpoints).

Given such an $n$-tuple $(P_1, \cdots, P_n)$, we denote by $\sigma(P)$ the permutation of $\sigma$ from the first condition.

The **Lindström–Gessel–Viennot lemma** then states that the determinants of $M$ is the signed sum over all $n$-tuples $P = (P_1, \cdots, P_n)$ of non-intersecting paths from $A$ to $B$.
$$\det(M) = \sum_{P:A\rightarrow B}\mathrm{sgn}(P)w(P)$$
