###### 1. A fair 6-sided die is rolled once. Find the expected number of additional rolls needed to obtain a value at least as large as that of the first roll.

Sol)
Let $X_{i}$ be the additional rolls that needed to obtain a value at least as large as that of the first roll when first roll has value $i$.
By linearlity of expectation, $E(X) = (E(X_{1}) + E(X_{2}) + \cdots + E(X_{6})) / 6$.
Note that $X_{i} \sim \text{Geom}\left( \frac{7-i}{6} \right)$.
So,
$$
\begin{align}
E(X) &= \frac{1}{6}\sum_{i=1}^{6}E(X_{i})  \\
&= \frac{1}{6}\sum_{i=1}^{6} \frac{1-\frac{7-i}{6}}{\frac{7-i}{6}} \\
&= \frac{1}{6}\sum_{i=1}^{6} \frac{i-1}{7-i} = \boxed{ \frac{29}{20} }
\end{align}
$$
###### 2. Let $X_{1}, X_{2}$ be i.i.d., and let $\bar{X} = \frac{1}{2}(X_{1}+X_{2})$ be the sample mean. In many statistics problems, it is useful or important to obtain a conditional expectation given $\bar{X}$. As an example of this, find $E(w_{1}X_{1}+w_{2}X_{2}|\bar{X})$, where $w_{1}, w_{2}$ are constants with $w_{1}+w_{2} = 1$.

Sol)
Let $\bar{X} =\frac{1}{2}(X_{1}+X_{2}) = x$.
Then,
$$
\begin{align}
E(w_{1}X_{1}+w_{2}X_{2}|\bar{X}) &= w_{1}E(X_{1}|\bar{X}) + w_{2}E(X_{2}|\bar{X}) \\
&= w_{1}E(X_{1}|\bar{X}) + (1-w_{1})E(X_{1}|\bar{X}) \\
&= E(X_{1}|\bar{X}) = c
\end{align}
$$
Note that $X_{1}$ and $X_{2}$ are i.i.d, so,
$$
E(X_{1}|\bar{X}) = E(X_{2}|\bar{X})
$$
So,
$$
\bar{X}= E(\bar{X}|\bar{X}) = \frac{1}{2}E(X_{1}|\bar{X}) + \frac{1}{2}E(X_{2}|\bar{X}) = c
$$
So,
$$
E(w_{1}X_{1}+w_{2}X_{2}|\bar{X}) = \bar{X}
$$
###### 3. Let $X$ be the height of a randomly chosen adult man, and $Y$ be his father's height, where $X$ and $Y$ have been standardized to have mean 0 and standard deviation 1. Suppose that $(X,Y)$ is Bivariate Normal, with $X,Y\sim \mathcal{N}(0,1)$ and $\text{Corr}(X, Y) = \rho$.
(a) Find a constant $c$ (in terms of $\rho$) and an r.v. $V$ such that $Y = cX+V$, with $V$ independent of $X$.
(b) Find a constant $d$ (in terms of $\rho$) and an r.v. $W$ such that $X=dY+W$, with $W$ independent of $Y$.
(c) Find $E(Y|X)$ and $E(X|Y)$.

Sol)
(a)
Since $\text{Corr}(X,Y) = \rho$ and $Var(X), Var(Y) = 1, 1$, $\text{Cov}(X, Y) = \rho$.
Note that
$$
\begin{align}
\text{Cov}(X,Y) &= \text{Cov}(X, cX+V) \\
&=cVar(X) + \text{Cov}(X,V) \\
&= c = \rho
\end{align}
$$
Since $\text{Cov}(X,V) = 0$.($V$ are independent of $X$.)
$V = Y-cX$ and we know that $(X, Y)$ are Bivariate Normal, so, $V$ also follows normal distribution.
$$\begin{align}
Var(V) &= Var(Y-cX) \\
&= Var(Y)+Var(-cX)+2\text{Cov}(Y,-cX) \\
&= Var(Y)+c^{2}-2c\rho \\
&= 1+c^{2}-2c\rho = 1-c^{2}
\end{align}$$
$$
\begin{align}
E(V) &= E(Y-cX) \\
&= E(Y)-cE(X) = 0
\end{align}
$$
So, $V \sim \mathcal{N}(0,1-c^{2})$.

(b)
Note that
$$
\begin{align}
\rho = \text{Cov}(X, Y) &= \text{Cov}(dY+W, Y) \\
&=dVar(Y) + \text{Cov}(W,Y) \\
&=dVar(Y) = d
\end{align}
$$
since $W$ is independent of $Y$.
$W = X-dY$ and we know that $(X, Y)$ are Bivariate Normal, so, $W$ also follows normal distribution.
$$
\begin{align}
Var(W) &= Var(X-dY) \\
&=Var(X) + Var(-dY) + 2\text{Cov}(X,-dY) \\
&=1+d^{2}-2d\rho = 1-d^{2}
\end{align}
$$
$$
\begin{align}
E(W) &= E(X-dY) \\
&=E(X)-dE(Y) = 0
\end{align}
$$
So, $W\sim \mathcal{N}(0,1-d^{2})$.

(c)
Note that $Y = cX+V$ where $V$ is independent of $X$ and $V$ is normal distribution.
$$
\begin{align}
E(Y|X) &= E(cX+V|X) \\
&=E(cX|X)+E(V|X) \\
&= cX + E(V) \\
&= cX = \rho X
\end{align}
$$
Note that $X = dY + W$ where $W$ is independent of $Y$ and $W$ is normal distribution.
$$
\begin{align}
E(X|Y) &= E(dY+W|Y) \\
&= E(dY|Y) + E(W|Y) \\
&= dY + E(W) \\
&= dY = \rho Y
\end{align}
$$
###### 4. Let $X$ and $Y$ be random variables with finite variances, and let $W = Y - E(Y|X)$. This is residual: the difference between the true value of $Y$ and the predicted value of $Y$ based on $X$.
(a) Compute $E(W)$ and $E(W|X)$
(b) Compute $Var(W)$, for the case that $W|X \sim \mathcal{N}(0,X^{2})$ with $X \sim \mathcal{N}(0, 1)$.

Sol)
(a)
$$
\begin{align}
E(W) &= E(Y-E(Y|X)) \\
&= E(Y) - E(E(Y|X)) \\
&=E(Y) - E(Y) = 0
\end{align}
$$
$$
\begin{align}
E(W|X) &= E(Y-E(Y|X)|X) \\
&= E(Y|X)-E(E(Y|X)|X) \\
&= E(Y|X) - E(Y|X) = 0
\end{align}
$$
(b)
$$
\begin{align}
Var(W) &= E(Var(W|X)) + Var(E(W|X)) \\
&= E(X^{2}) + Var(0) \\
Var(X) = E(X^{2})-E(X)^{2}\rightarrow&= 1+0 = 1 
\end{align}
$$

###### 5. Show that if $E(Y|X)=c$ is a constant, then $X$ and $Y$ are uncorrelated.

Sol)
$$
\begin{align}
\text{Cov}(X, Y) &= E(XY)-E(X)E(Y)
\end{align}
$$
By adam's law, $E(Y) = E(E(Y|X)) = E(c) = c$.
$E(XY) = E(E(XY|X)) = E(X\cdot E(Y|X))=E(X\cdot c) = cE(X)$.
So,
$$
\text{Cov}(X,Y) = cE(X)-cE(X) = 0
$$

###### 6. In a national survey, a random sample of people are chosen and asked whether they support a certain policy. Assume that everyone in the population is equally likely to be surveyed at each step, and that the sampling is with replacement. Let $n$ be the sample size, and let $\hat{p}$ and $p$ be the proportion of people who support the policy in the sample and in the entire population, respectively. Show that for every $c > 0$, $$P(\lvert \hat{p} - p \rvert > c )\leq \frac{1}{4nc^{2}}$$

Sol)
Each sample is an independent Bernoulli trial with success probability $p$. So, $$
\hat{p} = \frac{1}{n}\sum_{i=1}^{n}X_{i}
$$ where $X_{i}$ is 1 if $i$-th sampled person support policy, otherwise 0 and $X_{i}$ and $X_{j}$ are independent.
So,
$$
E(\hat{p}) = \frac{1}{n}\cdot n\cdot p=p, Var(\hat{p}) = \frac{1}{n^{2}}np(1-p) = \frac{p(1-p)}{n}
$$
By Chebyshev inequality,
$$
P(\lvert \hat{p}-p \rvert > c ) \leq \frac{p(1-p)}{nc^{2}}
$$
Note that $0 \leq p\leq 1$, so, $p(1-p)\leq \frac{1}{4}$.
So,
$$
P(\lvert \hat{p} - p \rvert > c )\leq \frac{p(1-p)}{nc^{2}} \leq \frac{1}{4nc^{2}}
$$
###### 7. For i.i.d. r.v.s $X_{1}, \dots, X_{n}$ with mean $\mu$ and variance $\sigma^{2}$, find a value of $n$ which will ensure that there is at least a 99% chance that the sample mean will be within 2 standard deviations of the true mean $\mu$.

Sol)
Note that sample mean $\bar{X}_{n}$ is a r.v. with $E(\bar{X}_{n}) = \mu$ and $Var(\bar{X}_{n})=\frac{\sigma^{2}}{n}$.
By Chebyshev inequality,
$$
P(\lvert \bar{X}_{n} - \mu \rvert \geq 2\sigma ) \leq \frac{\sigma^{2}}{4n\sigma^{2}}=\frac{1}{4n} \leq 0.01
$$
So, $n$ should be at least 25.

###### 8. Let $X$ and $Y$ be i.i.d. positive r.v.s, and let $c > 0$. For each part below, fill in the appropriate equality or inequality symbol. If no relation holds in general, write "?".
(a) $E(X), \sqrt{ E(X^{2}) }$
(b) $P(X > c), E(X^{3}) / c^{3}$
(c) $E(X^{3}), \sqrt{ E(X^{2})E(X^{4}) }$
(d) $P(\lvert X +Y\rvert > 2), E((X+Y)^{4})/10$
(e) $E(Y|X), E(Y|X+3)$
(f) $P(X+Y>2), (E(X)+E(Y)) / 2$

Sol)
(a)
Let $Y = 1$. By Cauchy-Schwarz inequality, $E(X) \leq \sqrt{ E(X^{2}) }$ holds.
(b)
Take funciton $g(x) = x^{3}$ which is strictly increasing. By Markov's inequality, $P(X > c) = P(X^{3} > c^{3}) \leq E(X^{3}) / c^{3}$ holds.
(c)
By Cauchy-Schwarz inequality, $E(X^{3}) \leq \sqrt{ E(X^{2})E(X^{4}) }$ holds.
(d)
By Markov's inequality, $$
P(\lvert X+Y \rvert > 2 ) = P((X+Y)^{4} > 16) \leq \frac{E((X+Y)^{4})}{16} < \frac{E((X+Y)^{4})}{10}
$$, $<$ holds.
(e)
Since $X$ and $Y$ are independent, equality holds.
$$
E(Y|X) = E(Y) = E(Y|X+3)
$$
(f)
By Markov's inequality,
$$
P(X+Y>2) \leq \frac{E(X+Y)}{2} = \frac{E(X)+E(Y)}{2}
$$

###### 9. Consider i.i.d. $\text{Pois}(\lambda)$ r.v.s $X_{1}, X_{2}, \dots$. The MGF of $X_{j}$ is $M(t) = e^{\lambda(e^{t}-1)}$.
(a) Find the MGF $M_{n}(t)$ of the sample mean $\bar{X}_{n} = \frac{1}{n}\sum_{j=1}^{n}X_{j}$.
(b) Find the limit of $M_{n}(t)$ as $n\to \infty$.

Sol)
(a)
$$
\begin{align}
M_{n}(t) &= E(e^{t\bar{X}_{n}}) \\
&= E\left( \prod_{j=1}^{n} e^{tX_{j}/n} \right) \\
&=\prod_{j=1}^{n}E(e^{tX_{j}/n}) \\
&= \prod_{j=1}^{n}M\left( \frac{t}{n} \right) \\
&= \exp(n\lambda(e^{t/n}-1))
\end{align}
$$
(b)
$$
\begin{align}
\lim_{ n \to \infty } M_{n}(t) &= \lim_{ n \to \infty } \exp(n\lambda(e^{t/n}-1)) \\
&= \exp(\lambda\lim_{ n \to \infty } n(e^{t/n}-1)) \\
&= \exp(\lambda t)
\end{align}
$$
###### 10. Let $Y = e^{X}$, with $X\sim \text{Expo}(3)$.
(a) Find the mean and variance of $Y$.
(b) For $Y_{1}, \dots, Y_{n}$ i.i.d. with the same distribution as $Y$, what is the approximate distribution of the sample mean $\bar{Y}_{n} = \frac{1}{n}\sum_{j=1}^{n}Y_{j}$ when $n$ is large?

Sol)
(a)
$$
\begin{align}
E(Y) &= E(e^{X}) \\
&= M(1) \\
&= \frac{3}{2} 
\end{align}
$$
$$
\begin{align}
Var(Y) &= E(Y^{2})-E(Y)^{2} \\
&= E(e^{2X}) - \frac{9}{4} \\
&= M(2) - \frac{9}{4} \\
&= 3 - \frac{9}{4} = \frac{3}{4}
\end{align}
$$
(b)
By CLT, $\bar{Y}_{n}\sim \mathcal{N}\left( \frac{3}{2} , \frac{3}{4n}\right)$.