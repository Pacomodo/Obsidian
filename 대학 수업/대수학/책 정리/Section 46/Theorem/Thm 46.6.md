___

**THEOREM**)
Let $D$ be a [[Euclidean domain]] with the Euclidean norm $\nu$.

1. $\nu (1)$ is a minimal member of the set $\{\nu (t) | t \in D - \{ 0\}\}$.
2. Let $u \in D - \{0\}$. Then $u$ is a unit $\Leftrightarrow$ $\nu (u) = \nu (1)$.

___

**PROOF**)

(1) For any $a \in D - \{0\}$, $\nu(a) = \nu(a\cdot 1) = \nu(a)\nu(1) \geq \nu(1)$.

(2)
$(\Rightarrow)$ If $uv = 1$, then $\nu(1) = \nu(uv) \geq \nu(u)\nu(v) \geq \nu(1)$ and by (1), $\nu(u) = \nu(1)$.
$(\Leftarrow)$ Let $1 = uv + r$ where $v, r \in D$ and $r = 0$ or $\nu(u) > \nu(r)$.
Since $\nu(u) = \nu(1)$ and by (1), $r = 0$. So, $u$ is a unit.

___
