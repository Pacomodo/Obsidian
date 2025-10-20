___

**DEF**)
A **partial ordering of a set $S$** is given by a relation $\leq$ defined for certain ordered pairs of elements of $S$ such that the following conditions are satiesfied:
1. $a \leq a$ for all $a \in S$ (Reflexive law)
2. If $a \leq b$ and $b \leq a$, then $a = b$ (Antisymmetric law)
3. If $a \leq b$ and $b \leq c$, then $a \leq c$ (Transitive law)

In a partially ordered set, not every two elements need to be **comparable**.
That is, for $a, b \in S$, we need not have either $a \leq b$ or $b \leq a$.
As usual, $a < b$ denotes $a \leq b$ but $a \neq b$.

A subset $T$ of a partially ordered set $S$ is a **chain** if every two elements $a, b \in T$ are comparable, that is, either $a \leq b$ or $b \leq a$. (or both).
An element $u \in S$ is an **upper bound for a subset $A$** of partially ordered set $S$ if $a \leq u$ for all $a \in A$.
Finally, an element $m$ of a partially ordered set $S$ is **maximal** if there is no $s \in S$ such that $m < s$.

___

**EXAMPLE**)

* The collection of all subsets of a set forms a partially ordered set under the relation $\leq$ given by $\subseteq$.

For example, if the whole set is $\mathbb{R}$, we have $\mathbb{Z} \subseteq \mathbb{Q}$. However, for $\mathbb{Z}$ and $\mathbb{Q}^+$, neither $\mathbb{Z} \subseteq \mathbb{Q}^+$ nor $\mathbb{Q}^+ \subseteq \mathbb{Z}$.

