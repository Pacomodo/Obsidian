###### 1. Let $X$ have PMF $$P(X=k) = \frac{cp^{k}}{k}, \text{  for } k=1, 2, \dots$$ where $p$ is a parameter with $0 < p < 1$ and $c$ is a normalizing constant $c = -\frac{1}{\log(1-p)}$, as seen from the Taylor series $$-\log(1-p)=p+\frac{p^{2}}{2}+\frac{p^{3}}{3}+\cdots$$ This distribution is called the Logarithmic distribution and has often been used in ecology. Find the mean and variance of $X$.

Sol)
Note that the expectation of a discrete r.v. $X$ with PMF $P$ is defined by
$$\begin{align}
E(X) &= \sum_{k=1}^{\infty}k\cdot P(X=k) \\
&= \sum_{k=1}^{\infty}-\frac{p^{k}}{\log(1-p)} \\
&= -\frac{1}{\log (1-p)}\sum_{k=1}^{\infty}p^{k} \\
\xrightarrow{\text{Since }0<p<1}&=-\frac{1}{\log(1-p)}\cdot \frac{p}{1-p} \\
&=\frac{p}{(1-p)\cdot \log\left( \frac{1}{1-p} \right)}
\end{align}
$$
The variance of a discrete r.v. $X$ with PMF $P$ is
$$
\text{Var}(X) = E(X^{2})-(EX)^{2}.
$$
By LOTUS,
$$
\begin{align}
E(X^{2}) &= \sum_{k=1}^{\infty}k^{2}P(X=k) \\
&= \sum_{k=1}^{\infty}-\frac{kp^{k}}{\log(1-p)} \\
\xrightarrow{\text{Since }0<p<1} &= -\frac{1}{\log(1-p)}\cdot \frac{p}{(1-p)^{2}} \\
&= \frac{p}{(1-p)^{2}\cdot \log\left( \frac{1}{1-p} \right)}  \\
(EX)^{2} &= \frac{p^{2}}{(1-p)^{2}\cdot\left( \log\left( \frac{1}{1-p} \right) \right)^{2}}
\end{align}
$$
$$
\begin{align}
V(X) &= E(X^{2}) - (EX)^{2} \\
&= \frac{p\left( \log\left( \frac{1}{1-p} \right)-p \right)}{(1-p)^{2}\cdot\left( \log\left( \frac{1}{1-p} \right) \right)^{2}}
\end{align}
$$
___
###### 2. A couple decides to keep having children until they have at least one boy and at least one girl, and then stop. Assume they never have twins, every birth is independent and with probability $1 / 2$ of a boy. What is the expected number of children?

Sol)
Consider two cases.
1. First child is a boy.

Let $Y$ be the number of children after first child to have the first girl.
PMF of $Y$: $Y(k) = \left( \frac{1}{2} \right)^{k}$

2. First child is a girl.

Let $Z$ be the number of children after first child to have the first boy.
PMF of $Z$: $Z(k) = \left( \frac{1}{2} \right)^{k}$

Let $X$ be the number of children after first child.
Then, PMF of $X$ is
$$
X(k) = \frac{1}{2}Y(k) + \frac{1}{2}Z(k) = \left( \frac{1}{2} \right)^{k}
$$
$$
\begin{align}
E(X) &= \sum_{k=1}^{\infty}k\left( \frac{1}{2} \right)^{k} = 2 \\
\end{align}
$$
Therefore, the expected number of total children is $2+1 = 3$.
___
###### 3. Raindrops are falling at an average rate of 20 drops per square inch per minute. Compute the probability that a 5 inches$^{2}$ region has no rain drops in a given 3-second time interval.

Sol)
Raindrops are falling at an average rate of 5 drops per 5 square inches per 3 second.
Let $X$ be the number of drops per 5 square inches per 3 second. $X\sim \text{Pois}\left( 5 \right)$.
So,
$$
P(X=k) = e^{-5} \frac{5^{k}}{k!}
$$
Hence, $P(X=0) = 1 / e^{5}$.
___
###### 4. Alice and Bob have just met, and wonder whether they have a mutual friend. Each has 50 friends, out of 1000 other people who live in their town. Assume that Alice's 50 friends are random sample of the 1000 people (equally likely to be any 50 of the 1000), and similarly for Bob. Also assume that knowing who Alice's friends are gives no information about who Bob's friends are.

(a) Compute the expected number of mutual friends Alice and Bob have.
(b) Let $X$ be the number of mutual friends they have. Find the PMF of $X$.

Sol)
(a)
Let $X_{i}$ be an indicator r.v. for each $i$th person in the town such that
$$
X_{i}=\begin{cases}
1 \text{ if }i\text{th person is friend of Bob and Alice} \\
0 \text{ else}
\end{cases}
$$
$P(X_{i}=1)=50 / 1000 \times 50 / 1000 = 0.0025$, So, $E(X_{i}) = 0.0025$.
By, linearity of expectation, $E(X) = \sum E(X_{i}) = 2.5$.

(b)
Assume that Alice have 50 friends already.
Then, it is enough to check that Bob's friends are in Alice's friends set. So, $X\sim \text{HGeom}(50, 950, 50)$.
Hence,
$$
P(X=x) = \frac{{50\choose x}{950 \choose 50-x}}{{1000\choose 50}} \text{   for  }x= 0, \dots 50
$$
___
###### 5. Randomly, $k$ distinguishable balls are placed into $n$ distinguishable boxes, with all possibilites equally likely. Find the expected number of empty boxes.

Sol)
Let $X_{i}$ be an indicator r.v. that if a ball in $i$th box $0$, else $1$.
Then, $P(X_{i} = 1) = (\frac{n-1}{n})^{k}$ and $P(X_{i} = 0) = 1-(\frac{n-1}{n})^{k}$
Let $X$ be the number of empty boxes.
By linearity of expectation, $E(X) = \sum E(X_{i})$.
So, $E(X) = \frac{(n-1)^{k}}{n^{k-1}}$.
___
###### 6. Nick and Penny are independently performing independent Bernoulli trials. Nick is flipping a nickel with probability $p_{1}$ of Heads and Penny is flipping a penny with probability $p_{2}$ of Heads. Let $X_{1}, X_{2}, \dots$ be Nick's results and $Y_{1}, Y_{2}, \dots$ be Penny's results, with $X_{i}\sim \text{Bern}(p_{1})$ and $Y_{i}\sim \text{Bern}(p_{2})$.

(a) Find the distribution and expected value of the first time at which they are simultaneously successful, i.e., the smallest $n$ such that $X_{n} = Y_{n} = 1$.
(b) Find the expected time until at least one has a success (including the success).
(c) For $p_{1}=p_{2}$, find the probability that their first successes are simultaneous, and use this to find the probability that Nick's first success precedes Penny's.

Sol)
(a)
Let $Z_{i}$ be an indicator r.v. that if $X_{i}$ and $Y_{i}$ are successful $1$, else $0$.
Then, $Z_{i}\sim \text{Bern}(p_{1}p_{2})$
Let $Z$ be the first time that they are simultaneously successful. 
The PMF of $Z$ is below.
$$
P(Z = n) = (1-p_{1}p_{2})^{n-1}p_{1}p_{2} \text{ for }n=1,2,\dots
$$
So, $Z\sim \text{FS}(p_{1}p_{2})$ and $E(Z) = 1 / p_{1}p_{2}$.

(b)
Let $Q_{i}$ be an indicator r.v. that if $X_{i}$ and $Y_{i}$ are fail $1$, else $0$.
Then, $Q_{i}\sim \text{Bern}((1-p_{1})(1-p_{2}))$.
Let $Q$ be the first time until at least one has a success.
Then, $Q\sim \text{FS}((1-p_{1})(1-p_{2}))$.
So, $E(Q) = \frac{1}{(1-p_{1})(1-p_{2})}$.

(c)
Let $R_{n}$ be the probability of their first successes are simultaneous occurs at $n$th time.
Then,
$$
R_{n} = (1-p_{1})^{2n-2}p_{1}^{2}
$$
Let $R$ be the probability of their first successes are simultaneous. Then,
$$
\begin{align}
R &= \sum_{n=1}^{\infty}R_{n} \\
&= \sum_{n=1}^{\infty}(1-p_{1})^{2n-2}p_{1}^{2} \\
&= \frac{p_{1}^{2}}{(1-p_{1})^{2}}\sum_{n=1}^{\infty}(1-p_{1})^{2n} \\
&= \frac{p_{1}^{2}}{(1-p_{1})^{2}}\cdot \frac{(1-p_{1})^{2}}{1-(1-p_{1})^{2}} \\
&= \frac{p_{1}^{2}}{1-(1-2p_{1}+p_{1}^{2})} = \frac{p_{1}}{2-p_{1}}
\end{align}
$$
So, $1-R$ be the probability that their first successes are not simultaneous.
Since the probability of Nick's first success precedes Penny's is same as the probability of Penny's first success precedes Nick's, the answer is
$$
\frac{1}{2}(1-R) = \frac{1}{2} \frac{2-2p_{1}}{2-p_{1}} = \frac{1-p_{1}}{2-p_{1}}
$$
___
###### 7.
(a) Use LOTUS to show that for $X\sim \text{Pois}(\lambda)$ and any function $g$,
$$
E(Xg(X)) = \lambda E(g(X+1))
$$
This is called the _Stein-Chen identity_ for the Poisson.
(b) Find the third moment $E(X^{3})$ by using the identity from (a).

Sol)
(a)
LOTUS is following statement:
>If $X$ is a discrete r.v. and $g:\mathbb{R}\to \mathbb{R}$, then for $Y = g(X)$ $$E(Y) = E(g(X)) = \sum_{x}g(x)P(X = x),$$where the sum is taken over all possible values of $X$.

Let $Y = Xg(X) = f(X)$.
Then,
$$
\begin{align}
E(Y) = E(f(X)) &= \sum_{k=0}^{\infty}f(k)P(X=k) \\
&=\sum_{k=0}^{\infty} kg(k) \frac{e^{-\lambda}\lambda^{k}}{k!} \\
&= \lambda e^{-\lambda} \sum_{k=1}^{\infty}g(k) \frac{\lambda^{k-1}}{(k-1)!} \\
&= \lambda e^{-\lambda} \sum_{k=0}^{\infty}g(k+1) \frac{\lambda^{k}}{k!} 
\end{align}
$$
Let $Z = g(X+1) = g(h(X))$.
Then,
$$
\begin{align}
\lambda E(Z) = \lambda E(g(X+1)) &= \lambda \sum_{k=0}^{\infty}g(h(k))P(X=k) \\
&=\lambda\sum_{k=0}^{\infty}g(k+1) \frac{e^{-\lambda}\lambda^{k}}{k!} \\
&= E(Y)
\end{align}
$$

(b)
Note that $E(X^{2}) = \lambda(1+\lambda)$ and $E(X) = \lambda$ for $\text{Pois}(\lambda)$.
Let $g(x) = x^{2}$.
$$
\begin{align}
E(X^{3}) = E(Xg(X)) &= \lambda E(g(X+1)) \\
&= \lambda E(X^{2}+2X+1) \\
&=\lambda(E(X^{2})+2E(X) + 1) \\
&=\lambda(\lambda(1+\lambda)+2\lambda+1) \\
&=\lambda(\lambda^{2}+3\lambda+1) \\
&=\lambda^{3}+3\lambda^{2}+\lambda
\end{align}
$$
___
###### 8.
(a) For $X\sim \text{Pois}(\lambda)$, find $E(e^{tX})$, for a constant $t$.
(b) For $X\sim \text{Geom}(p)$, find $E(e^{tX})$, for a constant $t$.

Sol)
(a)
By LOTUS,
$$
\begin{align}
E(e^{tX}) = \sum_{k=0}^{\infty}e^{tk} P(X=k) &= \sum_{k=0}^{\infty}e^{tk} \frac{e^{-\lambda}\lambda^{k}}{k!} \\
&= e^{-\lambda}\sum_{k=0}^{\infty} \frac{(\lambda e^{t})^{k}}{k!} \\
&=e^{-\lambda}e^{\lambda e^{t}} = e^{\lambda(e^{t}-1)}
\end{align}
$$

(b)
By LOTUS,
$$
\begin{align}
E(e^{tX}) = \sum_{k=0}^{\infty}e^{tk}P(X=k) &= \sum_{k=0}^{\infty}e^{tk}(1-p)^{k}p \\
&=p\sum_{k=0}^{\infty} (e^{t}-pe^{t})^{k} \\
&= \frac{p}{1-(e^{t}-pe^{t})}
\end{align}
$$
This works for $(e^{t}-pe^{t}) = (1-p)e^{t} < 1$. In other words, $t < \ln\left( \frac{1}{1-p} \right)$.