___

**DEF**)
Let $F$ be a [[Field|field]].
A **vector space over $F$** (or **$F$-vector space**) consists of an [[Abelian group]] $V$ under addition, together with an operation of scalar multiplication of each element of $V$ by each element of $F$ on the left, such that for all $a, b \in F$ and $\alpha, \beta \in V$ the following conditions are satisfied:

* $\mathscr{V}_1. a\alpha \in V$
* $\mathscr{V}_2. a(b\alpha) = (ab)\alpha$
* $\mathscr{V}_3. (a+b)\alpha = (a\alpha) + (b\alpha)$
* $\mathscr{V}_4. a(\alpha + \beta) = (a\alpha) + (a\beta)$
* $\mathscr{V}_5. 1\alpha = \alpha$

The elements of $V$ are **vectors** and the elements of $F$ are **scalars**.
When only one field $F$ is under discussion, we ddrop the reference to $F$ and refer to a *vector space*.

___

Note that scalar multiplication for a vector space is not a binary operation on one set in the sense we defined it in Section 2.
It associates an element $a\alpha \in V$ with each ordered pair $(a, \alpha)$, consisting of an element $a \in F$ and $\alpha \in V$.
Thus, scalar multiplication is a *function* mapping $F \times V \mapsto V$.
Both the additive identity for $V$($0$-vector) and the additive identity for $F$ ($0$-scalar) will be denoted by $0$.

**EXAMPLE**)

* Consider the abelian group $\left< \mathbb{R}^n,  + \right> = \mathbb{R} \times \mathbb{R} \times \cdots \times \mathbb{R}$. ^550329

Define scalar multiplication for scalars in $\mathbb{R}$ by $$r\alpha = (ra_1, \cdots, ra_n)$$for $r \in \mathbb{R}$ and $\alpha = (a_1, \cdots, a_n) \in \mathbb{R}^n$.
With these operations, $\mathbb{R}^n$ becomes a vector space over $\mathbb{R}$.
In particular, $\mathbb{R}^2 = \mathbb{R} \times \mathbb{R}$ as a vector space over $\mathbb{R}$ can be viewed as all "vectors whose starting points are the origin of the Eucliedan plane" in the sense familiar with.

* For any field $F$, $F[x]$ can be viewed as a vector space over $F$. ^f4586d

Addition of vectors is ordinary addition of polynomials in $F[x]$.
Scalar multiplication $a\alpha$ of an element of $F[x]$ by an element of $F$ is ordinary multiplication in $F[x]$.
The axioms follow immeddiately from the fact that $F[x]$ is a ring with unity.

* Let $E$ be an extension field of a field $F$.

Then $E$ can be regarded as a vector space over $F$.
Addition of vectors is the usual addition in $E$.
Scalar multiplication $a\alpha$ is the usual field multiplication in $E$ with $a \in F$ and $\alpha \in E$.
The axioms follow at once from the field axioms for $E$.
Here, our field of scalars is actually a subset of our space of vectors.
**It is important example**.

___

