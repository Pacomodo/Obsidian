___
## Finite Extensions

In [[Thm 30.23]], we saw that if $E$ is an [[Extension field|extension field]] of a field $F$ and $\alpha \in E$ is [[Algebraic, transcendental|algebraic]] over $F$, then every element of $F(\alpha)$ is algebraic over $F$.
In studying zeros of polynomials in $F[x]$, we shall be interested almost exclusively in extensions of $F$ containing **only elements algebraic over $F$**.

Go to [[Algebraic extension]].
Go to [[Finite extension]].

Let us repeat the argument of [[Thm 30.23]] to show that a finite extension $E$ of a field $F$ must be an algebraic extension of $F$.

Go to [[Thm 31.3]].

We cannot overemphasize the importance of our next theorem.
It plays a role in field theory analogous to the role of the theorem of Lagrange in group theory.
While its proof follows easily from our brief work with vector spaces, it is a tool of incredible power.
An elegant application of it in the section that follows shows the impossibility of performing certain geometric constructions with a straightedge and a compass.
*Never underestimate a theorem that counts something*.

Go to [[Thm 31.4]].

Note that we proved this theorem by actually exhibiting a basis.
Thus, it is worth remembering that if $\{\alpha_i\}$ is a basis for $E$ over $F$ and $\{\beta_j\}$ is a basis for $K$ over $E$, then, $\{\alpha_i\beta_j\}$ is a basis for $K$ over $F$.
Figure 31.5 shows this situation. We shall illustrate this further in a moment.

Go to [[Cor 31.6]].
Go to [[Cor 31.7]].

Last example in [[Cor 31.7]] shows that it is possible for an extension $F(\alpha_1, \cdots, \alpha_n)$ of a field $F$ to be actually a simple extension, even though $n>1$.
Let us characterize extensions of $F$ of the form $F(\alpha_1, \cdots, \alpha_n)$ in the case that all the $\alpha_i$ are algebraic over $F$.

Go to [[Thm 31.11]].

## Algebraically Closed Fields and Algebraic Closures

We have not yet observed that if $E$ is an extension of a field $F$ and $\alpha , \beta \in E$ are algebraic over $F$, then so are $\alpha + \beta , \alpha\beta , \alpha - \beta$, and $\alpha / \beta$, if $\beta \neq 0$.
This follows from [[Thm 31.3]] and is also included in the following theorem.

Go to [[Thm 31.12]].
Go to [[Cor 31.13]].

It is well known that the complex numbers have the property that every nonconstant polynomial in $\mathbb{C}[x]$ has a zero in $\mathbb{C}$. This is known as the *Fundemental Theorem of Algebra*.
An analytic proof of this theorem is given in [[Thm 31.18]].
We now give a definition generalizing this important concepts to other fields.

Go to [[Algebraically closed]].

Note that a field $F$ can be the algebraic closure of $F$ in an extension field $E$ without $F$ being algebraically closed.
For example, $\mathbb{Q}$ is the algebraic closure of $\mathbb{Q}$ in $\mathbb{Q}$, but $\mathbb{Q}$ is not albraically closed because $x^2 + 1$ has no zero in $\mathbb{Q}$.
The next theorem shows that the concept of a field being algebraically closed can also be defined in terms of factorization of polynomials over the field.

Go to [[Thm 31.15]].
Go to [[Cor 31.16]].

In a moment, we shall show that just as there exists an algebraically closed extension $\mathbb{C}$ of the real numbers $\mathbb{R}$, for any field $F$ there exists similarly an algebraic extension $\overline{F}$ of $F$, with the property that $\overline{F}$ is algebraically closed.
Naively, to find $\overline{F}$ we proceed as follows.
If a polynomial $f(x) \in F[x]$ has a no zero in $F$, then adjoin a zero $\alpha$ of such an $f(x)$ to $F$, thus obtaining $F(\alpha)$.
[[Thm 29.3]], Kroneker's thm is strongly used here.
If $F(\alpha)$ is still not algebraically closed, then continue the process further.
The trouble is that, contrary to the situation for the algebraic closure $\mathbb{C}$ of $\mathbb{R}$, we may have to do this a infinite number of times.
It can be shown (see [[Exercise 33]] and [[대학 수업/대수학/책 정리/Section 31/Exercise/Exercise 36|Exercise 36]]) that $\overline{\mathbb{Q}}$ is isomorphic to the field of all algebraic numbers, and that we cannot obtain $\overline{\mathbb{Q}}$ from $\mathbb{Q}$ by adjoining a finite number of algebraic numbers.
We shall have to first discuss some set-theoretic machinery, *Zorn's lemma*, in order to be able to handle such situation.
This machinery is a bit complex, so we are putting the proof under a seperate heading.
The existence theorem for $\overline{F}$ is very important, and we state it here so that we will know this fact, even if we do not study the proof.

Go to [[Thm 31.17]].

It is well known that $\mathbb{C}$ is an algebraically closed field.
We recall an analytic proof.

Go to [[Thm 31.18]].

## Proof of the Existence of an Algebraic Closure

We shall prove that every field has an algebraic extension that is algebraically closed.
Mathematics students should have the opportunity to see some proof involving the Axiom
of Choice by the time they finish college.
This is a natural place for such a proof.
We shall use an equivalent form, Zorn’s lemma, of the Axiom of Choice.
To state Zorn’s lemma, we have to give a set-theoretic definition.

Go to [[Def 31.19]].
Go to [[Zorn's Lemma]]

There is no question of proving Zorn’s lemma. The lemma is equivalent to the Axiom of Choice. Thus we are really taking Zorn’s lemma here as an axiom for our set theory.
Zorn’s lemma is often useful **when we want to show the existence of a largest or maximal structure of some kind.**
If a field $F$ has an [[Algebraic extension]] $\overline{F}$ that is [[Algebraically closed]], then $\overline{F}$ will certainly be a maximal algebraic extension of $F$, for since $\overline{F}$ is algebraically closed, it can have no proper algebraic extensions.

The idea of our proof of [[Thm 31.17]] is very simple.
Given a field $F$, we shall first describe a class of algebraic extensions of $F$ that is so large that it must contain (up to isomorphism) any conceivable algebraic extension of $F$.
We then define a partial ordering, the ordinary subfield ordering, and show that the hypothesis of Zorn's lemma are satiesfied.
By Zorn's lemma, there will exist a maximal algebraic extension $\overline{F}$ of $F$ in this class.
We shall then argue that, as a maximal elements, this extension $\overline{F}$ can have no proper algebraic extensions, so it must be algebraically closed.
