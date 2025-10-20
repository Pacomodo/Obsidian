___

**DEF**)
A nonzero nonunit element $p \in D$ is a **prime** if for all $a, b \in D$, $p|ab \implies$ either $p|a$ or $p|b$.

___

* [[Lem 45.13]] says that if $D$ is [[Principal ideal domain|PID]], then if $p$ is [[Irreducible|irreducible]] then $p$ is prime.

* Recall that if $D$ is [[Integral Domain|integral domain]] and $p \in D$ is [[Prime|prime]], then $p$ is [[Irreducible|irreducible]].
Proof) Let $p = ab$. Since $p | ab$, either $p | a$ or $p|b$. If $p|a$, then $pc = a$ where $c \in D$. So, $p = pcb \implies 1 = cb$, so, $b$ is unit.
Go to [[Exercise 25]].

* If $D$ is UFD, then $p$ is irreducible $\Leftrightarrow$ $p$ is prime.
Go to [[Exercise 26]].

* Hence, [[Lem 45.13]] says that if $D$ is [[Principal ideal domain|PID]], then $p$ is irreducible $\Leftrightarrow$ $p$ is prime.

* So, if $D$ is UFD or PID, then the concept of the prime and irreducibles are same.

* However, the concept of the prime and irreducibles are **do not coincide** for every integral domain $D$.
Let $F$ be a field and let $D$ be the subdomain $F[x^3, xy, y^3]$ of $F[x, y]$.

___
