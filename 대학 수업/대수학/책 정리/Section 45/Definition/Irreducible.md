___

**DEF**)
A nonzero non-[[Unit|unit]] $p \in D$ is an **irreducible of $D$** if in every factorization $p = ab$ in $D$ has the property that either $a$ or $b$ is a unit.

___

**EXAMPLES**)

* A positive integer $p$ is an irreducible of $\mathbb{Z}$ $\Leftrightarrow$ $p$ is a prime.

* Consider the [[Integral Domain|integral domain]] $D = \{a+b\sqrt{-3} | a, b \in \mathbb{Z} \}$.

Why $D$ is integral domain?
1. $D$ is commutative ring with unity.
It is enough to show that $D$ is closed in multiplication.
All the other conditions are so obvious.
Pick $a + b\sqrt{-3}, c + d\sqrt{-3} \in D$.
Then $(a+b\sqrt{-3})(c+d\sqrt{-3}) = (ac-3bd) + (ad + bc)\sqrt{-3} \in D$.
So, $D$ is commutative ring with unity.
2. $D$ contains no [[Divisors of 0|0 divisor]].
Suppose not. $a + b\sqrt{-3}$ and $c + d\sqrt{-3}$ in $D$ are nonzero element and they are $0$ divisors.
then, $(a+b\sqrt{-3})(c+d\sqrt{-3}) = (ac - 3bd) + (ad + bc)\sqrt{-3} = 0$
So, $ac=3bd$ and $ad+bc=0$.
Then, $(a-b\sqrt{-3})(c-d\sqrt{-3}) = (ac -3bd) - (ad + bc)\sqrt{-3} = 0$
So, $(a+b\sqrt{-3})(c+d\sqrt{-3})(a-b\sqrt{-3})(c-d\sqrt{-3}) = (a^2 + 3b^2)(c^2 + 3d^2) = 0$.
So, $a = b = 0$ and $c = d = 0$ which contradicts to they are nonzero element.

1. The only unit in $D$ are $1$ and $-1$.
Obviously, $1$ and $-1$ are units.
Suppose $a + b\sqrt{-3}$ are unit. then, for some $c, d \in \mathbb{Z}$, $(a+b\sqrt{-3})(c+d\sqrt{-3}) = 1$.
So, $ac-3bd = 1$ and $ad + bc = 0$.
So, $(a-b\sqrt{-3})(c-d\sqrt{-3}) = 1$.
Hence, $(a + 3b^2)(c+3d^2) = 1$. Hence, $(a, b) = \pm (1, 0)$.

 2. $\sqrt{-3}, 1+\sqrt{-3}, 2, 2+\sqrt{-3}$ are irreducibles in $D$.
We want to show that $1 + \sqrt{-3}$ is an irreducible of $D$.
$1 + \sqrt{-3} = (a+b\sqrt{-3})(c+d\sqrt{-3})$ and $1-\sqrt{-3} = (a-b\sqrt{-3})(c-d\sqrt{-3})$.
So, $4 = (a^2 + 3b^2)(c^2 + 3d^2)$.
So, $(a^2 + 3b^2, c^2 + 3d^2) = (4, 1), (2,2), (1, 4)$.
The second case is impossible. Also, the first case and last case, either $(c,d) = \pm (1,0)$ or $(a,b) = \pm(1, 0)$, which means one of them are unit.

___
