___

**THEOREM**) **(Existence of factorization in PID)**
Let $D$ be a [[Principal ideal domain|PID]].
Every nonzero non-[[Unit|unit]] element $a \in D$ is a product of [[Irreducible|irreducible]]s.

___

**PROOF**)
Let $a \in D$ be nonzero non-unit element.
	Claim : There exists an irreducible element $p \in D$ which divides $a$.
	Suppose not. Then $a$ itself is not irreducible.
	Thus, $a = a_1b_1$ where $a_1$ and $b_1$ both are not unit.
	Then, $\left< a \right> \subseteq \left< a_1 \right>$. If $\left< a \right> = \left< a_1 \right>$, then $a$ and $a_1$ are [[associate|associate]]s, so, $b_1$ is unit, which contradicts to $b_1$ is not unit. So, $\left< a \right> \subset \left< a_1 \right>$.
	We can continuing this process, so, we can construct a strictly ascending chain of [[Ideal|ideal]]s in $D$.
	$$ \left< a \right> \subset \left< a_1 \right> \subset \left< a_2 \right> \subset \cdots $$
	Since $D$ is PID, it contradicts with [[Lem 45.10]].

By the above claim, $a = p_1c_1$ for some irreducible element $p_1$.
If $c_1$ is a unit, then $a$ is irreducible, so we are done.
If $c_1$ is not a unit, then, $c_1 = p_2c_2$, hence, $a = p_1p_2c_2$ for some irreducible element $p_2$.
In this case, $\left< a \right> \subset \left< c_1 \right>$.
If $c_2$ is a unit, then $c_1$ is irreducible, so we are done. If not, then we can do this process again,
so, $\left< a \right> \subset \left< c_1 \right> \subset \left< c_2 \right>$.
This procedure must terminate. If not, then we have strictly ascending chain of ideals, so, it contradicts with [[Lem 45.10]].
Hence, $a = p_1p_2\cdots p_n$.

___
