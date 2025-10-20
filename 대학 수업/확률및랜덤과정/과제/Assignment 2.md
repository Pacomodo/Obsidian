###### 1. There are 100 seats in a class room, but 110 students are registered for the class. Each student will show up for the class with the probability 0.9, independently. Find the probability that there will be enough seats for the students showing up for the class.

Sol)
Consider an experiment that if a student show up for the class we say "success" and if not, we say "failure". Then, $P(\text{``success''})=0.9$.
Let $X$ be the number of "successes" when 110 independent Bernoulli trials are performed. Then, $X \sim \text{Bin}(110, 0.9)$.
Therefore, PMF of $X$ is
$$
P(X=k) = {110\choose k}0.9^{k}0.1^{110-k}
$$
If $k > 100$, then there will not be enough seats for the student showing up for the class.
So, the answer is 
$$
1-P(k>100) = 1-\sum_{k=101}^{110}{110\choose k}0.9^{k}0.1^{110-k} = \sum_{k=0}^{100}{110\choose k}0.9^{k}0.1^{110-k}
$$
___
###### 2. Let $X$ be the number of Heads in 10 fair coin tosses.

(a) Find the conditional PMF of $X$, given that the first two tosses both land Heads.
(b) Find the conditional PMF of $X$, given that at least two tosses land Heads.

Sol)
(a)
We want to find $P(X=k \ | \ \text{First two tosses are Heads})$ for $k = 2, \dots, 10$.
Let $Y = X-2$ be the number of Heads in the remaining 8 tosses.
Since each of coin tosses is independent, $Y \sim \text{Bin}(8,0.5)$.
So,
$$
P(X=k \ | \ \text{First two tosses are Heads}) = P(Y=k-2) = {8\choose k-2} 0.5^{8}
$$
for $k = 2, \dots, 10$.

(b)
We want to find $P(X = k \ | \ X\geq 2)$ for $k = 2, \dots, 10$.
Note that $X\sim \text{Bin}(10, 0.5)$.
So,
$$
P(X=k) = {10 \choose k} 0.5^{10}
$$
Also,
$$
P(X\geq 2) = 1-P(X=1)-P(X=0) = 1-11\cdot 0.5^{10}=\frac{1013}{1024}
$$
Hence,
$$
P(X=k \ | \ X\geq 2) = {10 \choose k} \frac{1}{1024} \cdot \frac{1024}{1013} = {10 \choose k}\cdot \frac{1}{1013}
$$
for $k = 2, \dots, 10$.
___
###### 3. Consider $n$ i.i.d. r.v.s. $X_{1}, \dots, X_{n}$, where $X_{i}\sim \text{Bern}(p)$. Show that the conditional PMF of $(X_{1}, X_{2}, \dots, X_{n})$ given a number of successes, $$P\left( X_{1}=a_{1}, X_{2}=a_{2}, \dots, X_{n}=a_{n} \ | \ \sum_{i=1}^{n}X_{i} = k \right) \text{ where } a_{i} \in \{0, 1\}$$is uniform.

Sol)
Since $X_{1}, \dots, X_{n}$ are i.i.d and $X_{i}\sim \text{Bern}(p)$, $P(X_{1}=a_{1}, \dots, X_{n}=a_{n}) = \prod_{i=1}^{n}P(X_{i} = a_{i}) = p^{k}(1-p)^{n-k}$, where $k = \sum_{i=1}^n a_{i}$.
Let $S = \sum_{i=1}^{n}X_{i}$, then, $S \sim \text{Bin}(n, p)$.
So, $P(S = k) = {n \choose k}p^{k}(1-p)^{n-k}$.
Hence,
$$
P\left( X_{1}=a_{1}, X_{2}=a_{2}, \dots, X_{n}=a_{n} \ | \ \sum_{i=1}^{n}X_{i} = k \right)=\frac{p^{k}(1-p)^{n-k}}{{n \choose k}p^{k}(1-p)^{n-k}} = \frac{1}{{n \choose k}}
$$
___
###### 4. There are 100 prizes, with one worth $1, one worth $2, ..., and one worth $100. There are 100 boxes, each of which contains one of the prizes. You get 5 prizes by picking random boxes one at a time, without replacement. Find the PMF of how much your most valuable prize is worth.

Sol)
Let $M$ be the value of most valuable prize among 5 prizes.
We want to find $P(M=x)$ where $x \in \{1, \dots, 100\}$.
If $x = 1, 2, 3, 4$, it is impossible for the value of most valueable prize, because we select 5 prizes one at a time without replacement.
So, $P(M=x) = 0$ when $x = 1, 2, 3, 4$.
Note that the total number of ways to choose any 5 prizes is $100 \choose 5$.
For $x = 5, \dots, 100$, we can think we picked the prize worth \$$x$ and remaining 4 prizes worth less than \$$x$. So,
$$
P(M=x) = \frac{{x-1 \choose 4}}{{100 \choose 5}}
$$
for $x = 5, \dots, 100$.
___
###### 5. Let $F_{1}$ and $F_{2}$ be CDFs, $0 < p < 1$, and $F(x) = pF_{1}(x) + (1-p)F_{2}(x)$ for all $x$.

(a) Show directly that $F$ has the properties of a valid CDF.
(b) Consider creating an r.v. in the following way. Flip a coin with probability $p$ of Heads. If the coin lands Heads, generate an r.v. according to $F_{1}$; if the coin lands Tails, generate an r.v. according to $F_{2}$. Show that the r.v. obtained in this way has CDF $F$.

Sol)
(a)
The properties of a valid CDF are
1. Nondecreasing,
2. Right continuous,
3. $\lim_{ x \to -\infty }F(x) = 0, \lim_{ x \to +\infty }F(x) = 1$.

Want to show that for any $x_{1} \leq x_{2}$, $F(x_{1})\leq F(x_{2})$.
Since $F_{1}$ and $F_{2}$ are CDF, $pF_{1}(x_{1})\leq pF_{1}(x_{2})$ and $(1-p)F_{2}(x_{1})\leq(1-p)F_{2}(x_{2})$.
Hence, $F(x_{1}) = pF_{1}(x_{1})+(1-p)F_{2}(x_{1})\leq pF_{1}(x_{2})+(1-p)F_{2}(x_{2}) = F(x_{2})$.
Want to show that $\lim_{ h \to 0+ }F(x+h) = F(x)$ for all $x$.
Since $F_{1}$ and $F_{2}$ are CDF, $\lim_{ h \to 0+ }F_{1}(x+h) = F_{1}(x)$ and $\lim_{ h \to 0+ }F_{2}(x+h) = F_{2}(x)$ for all $x$.
Hence,
$$
\begin{align}
\lim_{ h \to 0+ }F(x+h) &= \lim_{ h \to 0+ }(pF_{1}(x+h) + (1-p)F_{2}(x+h)) \\
&=p\lim_{ h \to 0+ } F_{1}(x+h)+(1-p)\lim_{ h \to 0+ } F_{2}(x+h) \\
&= pF_{1}(x) + (1-p)F_{2}(x) = F(x)
\end{align}
$$
Want to show that $\lim_{ x \to -\infty }F(x) = 0, \lim_{ x \to +\infty }F(x) = 1$.
Since $F_{1}$ and $F_{2}$ are CDF, $\lim_{ x \to -\infty }F_{1}(x) = 0, \lim_{ x \to \infty }F_{1}(x)=1$ and $\lim_{ x \to -\infty }F_{2}(x)=0, \lim_{ x \to \infty }F_{2}(x)=1$.
Hence,
$$
\begin{align}
\lim_{ x \to -\infty }F(x) = p\cdot 0 + (1-p)\cdot 0 = 0 \\
\lim_{ x \to \infty } F(x) = p\cdot 1 + (1-p)\cdot 1 = 1
\end{align}
$$

(b)
For random variable $X$, $F(x) = P(X \leq x)$ (By definition).
Let $H =$ Coin lands Heads and $T =$ Coin lands Tails.
By LOTP,
$$
F(x) = P(X\leq x) = P(X\leq x|H)P(H) + P(X\leq x|T)P(T)
$$
We know that if the coin lands Heads, we generate an r.v. according to $F_{1}$, So, $X$ follows the distribution $F_{1}$ when coin lands heads.
$$
P(X\leq x|H) = F_{1}(x)
$$
Similiarly,
$$
P(X\leq x|T) = F_{2}(x)
$$
Hence,
$$
F(x) = pF_{1}(x)+(1-p)F_{2}(x)
$$
___
###### 6. Let $X,Y,Z$ be discrete r.v.s such that $X$ and $Y$ have the same conditional distribution given $Z$, i.e., for all $a$ and $z$ we have $$P(X=a|Z=z)=P(Y=a|Z=z).$$ Show that $X$ and $Y$ have the same distribution.

Sol)
We want to show that $X$ and $Y$ have the same distribution. In other words, $$
P(X=a) = P(Y=a)
$$ for all $a$.
By LOTP,
$$
\begin{align}
P(X=a) = \sum_{z}P(X=a, Z=z) &= \sum_{z} P(X=a|Z=z)P(Z=z) \\
&= \sum_{z} P(Y=a|Z=z)P(Z=z)  \\
&= \sum_{z}P(Y=a, Z=z) = P(Y=a)
\end{align}
$$
___
###### 7. If $X\sim \text{HGeom}(w,b,n)$, what is the distribution of $n-X$?

Sol)
Let $A\sim \text{Bin}(w, p), B\sim \text{Bin}(b, p)$ and $A$ and $B$ are independent.
We defined $P(A = x|A+B=n)$ as $\text{HGeom}(w, b, n)$.
Note that
$$
P(X = x) = \text{HGeom}(w, b, n)= \frac{{w \choose x}{b \choose n-x}}{{w+b \choose n}}.
$$
Let $Y = n-X$.
Then,
$$
P(Y=x) = P(n-X=x)=P(X = n-x) = \frac{{w \choose n-x}{b \choose x}}{{w+b \choose n}} = \text{HGeom}(b, w, n)
$$
___
###### 8. For $x$ and $y$ binary digits ($0$ or $1$), let $$x \oplus y = \begin{cases}0 \text{ if }x=y \\1 \text{ if }x\neq y\end{cases}$$ (this operation is called exclusive or (often abbreviated to XOR), or addition mod 2).

(a) Let $X\sim \text{Bern}(p)$ and $Y\sim \text{Bern}(1/2)$, independently. What is the distribution of $X\oplus Y$?
(b) Is $X \oplus Y$ independent of $X$? Is $X\oplus Y$ independent of $Y$? Be sure to consider both the case $p=1/2$ and the case $p\neq 1/2$.

Sol)
(a)
We want to find $P(X\oplus Y = 0)$ and $P(X\oplus Y = 1)$.
Note that $P(X=0) = 1-p, P(X=1) = p$ and $P(Y=0) = P(Y=1) = 1 / 2$, $X$ and $Y$ are independent.
$$
\begin{align}
P(X\oplus Y = 0) &= P(X=0, Y=0) + P(X=1, Y=1) \\
&= P(X=0)P(Y=0) + P(X=1)P(Y=1) \\
&= \frac{1-p}{2} + \frac{p}{2} \\
&= \frac{1}{2}
\end{align}
$$
$$
\begin{align}
P(X\oplus Y = 1) &= P(X=0, Y=1) + P(X=1, Y=0) \\
&= P(X=0)P(Y=1) + P(X=1)P(Y=0) \\
&= \frac{1-p}{2} + \frac{p}{2} \\
&= \frac{1}{2}
\end{align}
$$
So, $X\oplus Y\sim \text{Bern}(1/2)$.

(b)
Remind the definition of independence of two random variables.
For $X = 0$,
$$
\begin{align}
P(X\oplus Y = 0, X = 0) &= P(X=0, Y=0) = \frac{1-p}{2}  \\
P(X=0)\cdot P(X\oplus Y = 0) &= \frac{1-p}{2} \\
P(X\oplus Y = 1, X = 0) &= P(X=0, Y=1) = \frac{1-p}{2} \\
P(X=0)\cdot P(X\oplus Y=1)&=\frac{1-p}{2}
\end{align}
$$
For $X = 1$,
$$
\begin{align}
P(X\oplus Y = 0, X=1) &= P(X=1, Y=1) = \frac{p}{2} \\
P(X=1)\cdot P(X\oplus Y = 0) &= \frac{p}{2} \\
P(X\oplus Y = 1, X=1) &= P(X=1, Y=0) = \frac{p}{2} \\
P(X=1)\cdot P(X\oplus Y=1)&=\frac{p}{2}
\end{align}
$$
So, $X\oplus Y$ and $X$ are independent regardless of $p$.

For $Y = 0$,
$$
\begin{align}
P(X\oplus Y = 0, Y = 0) &= P(X=0, Y=0) = \frac{1-p}{2}  \\
P(Y=0)\cdot P(X\oplus Y = 0) &= \frac{1}{4} \\
P(X\oplus Y = 1, Y = 0) &= P(X=1, Y=0) = \frac{p}{2} \\
P(Y=0)\cdot P(X\oplus Y=1)&=\frac{1}{4}
\end{align}
$$
For $Y = 1$,
$$
\begin{align}
P(X\oplus Y = 0, Y = 1) &= P(X=1, Y=1) = \frac{p}{2}  \\
P(Y=1)\cdot P(X\oplus Y = 0) &= \frac{1}{4} \\
P(X\oplus Y = 1, Y = 1) &= P(X=0, Y=1) = \frac{1-p}{2} \\
P(Y=1)\cdot P(X\oplus Y=1)&=\frac{1}{4}
\end{align}
$$

So, $X\oplus Y$ and $Y$ are not independent when $p \neq 1 / 2$.
If $p = 1 / 2$, $X \oplus Y$ and $Y$ are independent.
___
