___

**THEOREM**) (Generalization of [[Thm 27.25]])
An [[Ideal|ideal]] $\left< p \right>$ in a [[Principal ideal domain|PID]] is [[Maximal ideal|maximal]] $\Leftrightarrow$ $p$ is [[Irreducible|irreducible]].

___

**PROOF**)
$(\Rightarrow)$ Suppose that $D$ is principal ideal domain and $p \in D$, and $\left< p \right>$ is an ideal in $D$.
We want to show that $p$ is irreducible in $D$.
So, consider $p = ab$ where $a, b \in D$.
What we want to show is either $a$ or $b$ is a [[Unit|unit]] in $D$.
Since $p = ab$, $\left< p \right> \subseteq \left< a \right>$.
If $\left< p \right> = \left< a \right>$, then $a$ and $p$ [[associate|associates]] each other, so, $b$ is a unit.
If $\left< p \right> \subset \left< a \right>$, because $\left< p \right>$ is maximal, so, $\left< a \right> = \left< 1 \right> = D$, so, $a$ associates with $1$, so, $a$ is a unit.

$(\Leftarrow)$ Suppose that $D$ is PID and $p \in D$ is irreducible.
We want to show that an ideal $\left< p \right>$ is a maximal ideal.
Let $N$ is an ideal in D such that $\left< p \right> \subseteq N \subseteq D$.
We want to show that $N$ is either $\left< p \right>$ or $D$.
Since $N$ is principal ideal, there exist $a \in D$ such that $\left< a \right> = N$.
Since $\left< p \right> \subseteq \left< a \right>$, $p = ab$ where $b \in D$.
We know that $p$ is irreducible, either $a$ or $b$ is a unit in $D$.
If $a$ is a unit, then, $\left< a \right> = \left< 1 \right> = D$.
If b is a unit, then, there exist $b^{-1} \in D$ such that $bb^{-1} = 1$. So, $pb^{-1} = abb^{-1} = a$, so, $\left< a \right> \subseteq \left< p \right>$.
Hence, $\left< p \right> = \left< a \right>$.

___

