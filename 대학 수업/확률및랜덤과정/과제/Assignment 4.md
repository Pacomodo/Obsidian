###### 1. Let $F$ be the CDF of a continuous r.v., and $f = F'$ be the PDF.

(a) Show that $g$ defined by $g(x) = 2F(x)f(x)$ is also a valid PDF.
(b) Show that $h$ defined by $h(x) = f(-x) / 2 + f(x) / 2$ is also a valid PDF.

Sol)
(a)
To show that a function is a valid PDF, function must be nonnegative and when it integrates, its value must be 1.
It is obvious that $F \geq 0$ since $F$ is CDF of a continuous r.v.. Also, $f$ is PDF, $f \geq 0$.
So, $g(x) = 2F(x)f(x) \geq 0$.
Note that $f$ is PDF,
$$
\int _{-\infty}^{\infty}f(x) \, dx = \lim_{ x \to \infty }[F(x) - F(-x)]  = 1 
$$
Hence,
$$
\begin{align}
\int _{-\infty}^{\infty}2F(x)f(x) \, dx &= \lim_{ x \to \infty }[F(x)^{2}-F(-x)^{2}] \\
&= \lim_{ x \to \infty } [F(x)-F(-x)][F(x)+F(-x)] \\
&=1\cdot (\lim_{ x \to \infty } F(x) + \lim_{ x \to -\infty } F(x)) \\
&=1\cdot(1+0) = 1
\end{align}
$$

(b)
Since $f\geq 0$, it is obvious that $h \geq 0$.
$$
\begin{align}
\int _{-\infty}^{\infty} \frac{f(x)+f(-x)}{2} \, dx &= \lim_{ x \to \infty } \frac{F(x)-F(-x)+F(x)-F(-x)}{2} \\
&= \lim_{ x \to \infty } [F(x) - F(-x)] \\
&= 1
\end{align}
$$
___
###### 2. A stick of length 1 is broken at a uniformly random point, yielding two pieces. Let $X$ and $Y$ be the lengths of the shorter and longer pieces, respectively, and let $R=X / Y$ be the ratio of the lengths $X$ and $Y$.

(a) Find the CDF and PDF of $R$.
(b) Find the expected value of $R$.

Sol)
(a)
Let $U$ be the position of broken points. Then, $U\sim \text{Unif}(0, 1)$.
When $U \leq \frac{1}{2}$, $R = X / Y = \frac{U}{1-U}$ and when $U > \frac{1}{2}$, $R = X / Y = \frac{1-U}{U}$.
Note that $R$ always between $0$ and $1$.
We need to compute $F_{R}(r) = P(R \leq r)$ for $r \in [0, 1]$.
If $U\leq \frac{1}{2}$, i.e., suppose $U \in\left[ 0, \frac{1}{2} \right]$,
Then, $R\leq r \rightarrow \frac{U}{1-U}\leq r \rightarrow U \leq r-rU \rightarrow U\leq \frac{r}{1+r}$
$$
\begin{align}
P\left( R\leq r | U\in \left[ 0, \frac{1}{2} \right] \right)&= P\left( U\leq \frac{r}{1+r}|U\in\left[ 0, \frac{1}{2} \right] \right) \\
&= \frac{2r}{1+r} 
\end{align}
$$
If $U \geq \frac{1}{2}$,
$R\leq r\rightarrow \frac{1-U}{U}\leq r \rightarrow U \geq \frac{1}{1+r}$
$$
\begin{align}
P\left( R\leq r|U\in \left[ \frac{1}{2}, 1 \right] \right) &= P\left( U\geq \frac{1}{1+r}|U\in \left[ \frac{1}{2}, 1 \right] \right) \\
&=\frac{2r}{1+r} 
\end{align}
$$
So,
$$
\begin{align}
P(R\leq r) &= P\left( R\leq r|U\in\left[ 0, \frac{1}{2} \right] \right)P\left( U\in\left[ 0, \frac{1}{2} \right] \right) \\
&+ P\left( R\leq r|U\in\left[ \frac{1}{2}, 1 \right] \right)P\left( U\in\left[ \frac{1}{2}, 1 \right] \right) \\
&= \frac{2r}{1+r}
\end{align}
$$
Then, $f_{R}(r) = F'_{R}(r)$, So,
$$
f_{R}(r) = \frac{2}{1+r} -\frac{2r}{(1+r)^{2}} = \frac{2}{(1+r)^{2}}
$$
(b)
$$
\begin{align}
\int _{0}^{1}rf_{R}(r) \, dr &= \int_{0}^{1} \frac{2r}{(1+r)^{2}} dr  \, \\
&=\int _{0}^{1} \frac{2r+2}{(1+r)^{2}} - \frac{2}{(1+r)^{2}} \, dr \\
&=\left[\ln(1+r)^{2}\right]^{1}_{0} + \int _{1}^{2} -\frac{2}{x^{2}} \, dx \\
&=\ln 4 + \left[ \frac{2}{x} \right]^{2}_{1}=\ln 4 - 1 
\end{align}
$$
___
###### 3. Let $U\sim \text{Unif}(0, 1)$. As a function of $U$, create an r.v. $X$ with CDF $F(x) = 1-e^{-x^{3}}$ for $x > 0$.

Sol)
We want to use universality of Uniform Distribution.
Note that $F_{X}(x) = 1-e^{-x^{3}}$, So, $F^{-1}_{X}(x) = \sqrt[3]{-\ln(1-x)}$.
Then, $X = \sqrt[3]{-\ln(1-U)}$.
Since $U\sim \text{Unif}(0,1)$ and $1-U$ has same distribution, it is ok to replace $1-U$ into $U$.
So, $X = \sqrt[3]{-\ln U}$.
___
###### 4. Let $Z \sim \mathcal{N}(0,1)$. Define $X = Z\cdot I_{Z>0}$, where $I_{Z>0}$ is the indicator r.v. for $\{Z>0\}$. Find $E(X)$ and $Var(X)$.

Sol)
$$
\begin{align}
E(X) &= \frac{1}{\sqrt{ 2\pi }}\int _{0}^{\infty}ze^{-z^{2}/2} \, dz \\
-\frac{z^{2}}{2}=u\rightarrow zdz = -du &= \frac{1}{\sqrt{ 2\pi }} \int _{0}^{-\infty}-e^{u} \, du \\
&=\frac{1}{\sqrt{ 2\pi }}[-e^{u}]^{-\infty}_{0} =\frac{1}{\sqrt{ 2\pi }} 
\end{align}
$$
$$
\begin{align}
Var(X) &= E(X^{2}) - (EX)^{2} \\
&= E(X^{2}) - \frac{1}{2\pi}
\end{align}
$$
We want to compute $E(X^{2})$.
$$
\begin{align}
E(X^{2}) &= \frac{1}{\sqrt{ 2\pi } }\left(\int_{0}^{\infty}z^{2}e^{-z^{2}/2} \, dz\right) \\
f=z, g'=ze^{-z^{2}/2}\to &= \frac{1}{\sqrt{ 2\pi } }\left(fg - \int _{0}^{\infty}f'g \, dz \right) \\
&=\frac{1}{\sqrt{ 2\pi }}\left( [-ze^{-z^{2}/2}]^{\infty}_{0}+\int _{0}^{\infty}e^{-z^{2}/2} \, dz  \right)
\end{align}
$$
Note that
$$
\begin{align}
\left(\int _{-\infty}^{\infty}e^{-z^{2}/2}\, dz\right)^{2} = 2\pi 
\end{align}
$$
So,
$$
\begin{align}
&= \frac{1}{\sqrt{ 2\pi }} \left( 0+\frac{\sqrt{ 2\pi }}{2} \right) \\
&= \frac{1}{2} = E(X^{2})
\end{align}
$$
Hence,
$$
Var(X) = \frac{1}{2} - \frac{1}{2\pi} = \frac{\pi - 1}{2\pi}
$$
___
###### 5. Let $T$ be the time until a radioactive particle decays, and suppose (as is often done in physics and chemistry) that $T\sim \text{Expo}(\lambda)$.

(a) The half-life of the particle is the time at which there is a 50% chance that the particle has decayed. Find the half-life of the particle.
(b) Now consider $n$ radioactive particles, with i.i.d. times until decay $T_{1}, \dots , T_{n} ∼\text{Expo}(\lambda)$. Let $L$ be the ﬁrst time at which one of the particles decays. Find the CDF of $L$. Also, ﬁnd $E(L)$ and $Var(L)$.
(c) Continuing (b), ﬁnd the mean and variance of $M = \max(T_{1},\dots, T_{n})$, the last time at which one of the particles decays.

Sol)
(a)
Let $t_{h}$ be the time at which there is a 50% chance the particle has decayed. i.e.$P(T \leq t_{h}) = 0.5$.
Since $T\sim \text{Expo}(\lambda)$, $P(T \leq t_{h}) = 1-e^{-\lambda t_{h}} = 0.5$.
$$
\begin{align}
1-e^{-\lambda t_{h}} &= 0.5 \\
\ln \left( \frac{1}{2} \right) &=-\lambda t_{h} \\
t_{h} &=\frac{\ln2}{\lambda}
\end{align}
$$

(b)
$L$ is first time at which one of the particles decays. It means, $L = \min(T_{1},\dots,T_{n})$.
So, the probability that all particles are not decay is
$$
\begin{align}
P(t < L) &= P(t<T_{1},\dots,t < T_{n}) \\
\xrightarrow{\text{independent}}&=P(t<T_{1})P(t<T_{2})\cdots P(t<T_{n}) \\
&=(e^{-\lambda t})^{n} = e^{-\lambda nt}
\end{align}
$$
Hence, CDF of $L$ is
$$
P(L \leq t) = 1-e^{-\lambda nt}
$$
Hence, $L\sim \text{Expo}(n\lambda)$.
Note that mean and variance of exponential distribution $Y\sim\text{Expo}(\mu)$ is
$$
E(Y) = \frac{1}{\mu}, Var(Y) = \frac{1}{\mu^{2}}
$$
So, $E(L) = 1 / n\lambda, Var(L) = 1 / (n\lambda)^{2}$.

(c)
$M$ means the first time at which all particles decay.
So, the probability that all particles decay is
$$
\begin{align}
P(t\geq M) &= P(t\geq T_{1}, \dots, t\geq T_{n}) \\
\xrightarrow{\text{i.i.d}}&=(1-e^{-\lambda t})^{n}
\end{align}
$$
So, PDF of $M$ is
$$
f_{M}(t) = \frac{d}{dt} (1-e^{-\lambda t})^{n} = n\lambda e^{-\lambda t}(1-e^{-\lambda t})^{n-1}
$$
So, $E(M)$ is
$$
E(M) = \int _{0}^{\infty}n\lambda te^{-\lambda t}(1-e^{-\lambda t})^{n-1} \, dt
$$
Let $u = e^{-\lambda t}$, then $-du = \lambda e^{-\lambda t}dt$ and $\ln u = -\lambda t\rightarrow t = \frac{\ln u}{-\lambda}$, $t=0 \to u=1$, $t = \infty \to 0$.
$$
=\int _{1}^{0} n \frac{\ln u}{\lambda}(1-u)^{n-1} \, du = -\frac{n}{\lambda} \int _{0}^{1}\ln u (1-u)^{n-1} \, du 
$$
We use well-known integral formula below,
$$
\int _{0}^{1}u^{a-1}(1-u)^{b-1}\ln u \, du = B(a,b)[\psi(a)-\psi(a+b)] 
$$
where $B(a,b)$ is beta function and $\psi(a)$ is digamma function, which is the derivative of natural logarithm of gamma function.
By this formula,
$$
\begin{align}
&= -\frac{n}{\lambda}B(1,n)(\psi(1)-\psi(1+n)) \\
&=-\frac{n}{\lambda} \frac{\Gamma(1)\Gamma(n)}{\Gamma(1+n)}[-\gamma +\gamma-H_{n}] \\
&=\frac{n}{\lambda} \frac{1}{n} H_{n} = \frac{H_{n}}{\lambda} = E(M)
\end{align}
$$
where $H_{n}$ is harmonic number and $\gamma$ is Euler-Mascheroni constant.
$$
Var(M) = E(M^{2}) - (EM)^{2}
$$
and
$$
\begin{align}
E(M^{2}) &= \int _{0}^{\infty}n\lambda t^{2}e^{-\lambda t}(1-e^{-\lambda t})^{n-1} \, dt \\
&= \int _{0}^{1} n \frac{(\ln u)^{2}}{\lambda^{2}}(1-u)^{n-1} \, du \\
&=\frac{n}{\lambda^{2}}B(1, n)\{[\psi(1)-\psi(1+n)]^{2} + \psi_{1}(a) -\psi_{1}(a+b)\}
\end{align}
$$
where $\psi_{1}$ is trigamma function, which is second derivative of natural logarithm of gamma function. (This formula is too long, so, ommit.)
$$
\begin{align}
&= \frac{n}{\lambda^{2}} \frac{1}{n} \{H_{n}^{2}+G_{n}\}
\end{align}
$$
where $G_{n}$ is sum of square numbers up to $n$.
Hence,
$$
Var(M)= \frac{H_{n}^{2}+G_{n}}{\lambda^{2}} - \frac{H^{2}_{n}}{\lambda^{2}}=\frac{G_{n}^{2}}{\lambda^{2}}
$$
___
###### 6. Let $U_{1}, U_{2}, \dots, U_{60}$ be i.i.d. $\text{Unif}(0,1)$ and $X = U_{1}+U_{2}+\cdots+U_{60}$. Find the MGF of $X$.

Sol)
$$
\begin{align}
M_{X}(t) &= E(e^{tX}) \\
&= E(e^{t(U_{1}+U_{2}+\cdots+U_{60})}) \\
\xrightarrow{\text{i.i.d}}&= \left(\frac{e^{t}-1}{t}\right)^{60}
\end{align}
$$
___
###### 7. Let $X$ and $Y$ be i.i.d. $\text{Expo}(1)$, and $L = X-Y$. The Laplace distribution has PDF $$f(x)=\frac{1}{2}e^{-|x|}$$ for all real $x$. Use MGFs to show that the distribution of $L$ is Laplace.

Sol)
$$
\begin{align}
M_{L}(t) &= M_{X-Y}(t) =E(e^{t(X-Y)}) \\
\xrightarrow{\text{independent}} &= E(e^{tX})E(e^{-tY})=M_{X}(t)M_{Y}(-t) \\
&= \frac{1}{1-t} \frac{1}{1+t} \\
&= \frac{1}{1-t^{2}} \text{ where }-1<t<1
\end{align}
$$
MGF of Laplace distribution $Z$ is
$$
\begin{align}
M_{Z}(t) &= E(e^{tZ}) \\
&=\int _{-\infty}^{\infty} \frac{1}{2}e^{tx}e^{-|x|} \, dx \\
&=\frac{1}{2}\left( \int _{0}^{\infty}e^{(t-1)x} \, dx +\int _{-\infty}^{0} e^{(t+1)x} \, dx   \right) \\
&=\frac{1}{2}\left(\left[ \frac{e^{(t-1)x}}{t-1} \right]^{\infty}_{0}+\left[ \frac{e^{(t+1)x}}{t+1} \right]^{0}_{-\infty}\right) \\
&=\frac{1}{2}\left( -\frac{1}{t-1}+\frac{1}{t+1} \right)\text{ where }-1<t<1 \\
&=\frac{1}{1-t^{2}}
\end{align}
$$
So, $L$ has Laplace distribution.
___
###### 8. Let $W = X^{2}+Y^{2}$, with $X,Y$ i.i.d. $\mathcal{N}(0,1)$. The MGF of $X^{2}$ turns out to be $(1-2t)^{-1/2}$ for $t<1 / 2$.

(a) Find the MGF of $W$.
(b) From the MGF of $W$, identify the distribution of $W$.

Sol)
(a)
Note that the MGF of $X^{2} = (1-2t)^{-1 / 2}$.
Since $X^{2}$ and $Y^{2}$ are i.i.d.,
$$
M_{W}(t) = M_{X^{2}+Y^{2}}(t) = M_{X^{2}}(t)M_{Y^{2}}(t) = \frac{1}{1-2t} = \frac{\frac{1}{2}}{\frac{1}{2}-t}
$$
where $t < \frac{1}{2}$.

(b)
Hence, $W\sim \text{Expo}\left( \frac{1}{2} \right)$.
___
###### 9. Let $Y=X^{3}$, with $X\sim \text{Expo}(1)$.

(a) Find $P(Y>s+t|Y>s)$ for $s,t>0$. Does $Y$ have the memoryless property?
(b) Find the mean and variance of $Y$, and the $n$-th moment $E(Y^{n})$ for $n=1, 2, \dots$.
(c) Determine whether or not the MGF of $Y$ exists.

Sol)
(a)
$P(Y>s) = P(X^{3}>s) = P(X>s^{1 / 3}) = e^{-s^{1/3}}$.
$P(Y>s+t) = e^{-(s+t)^{1/3}}$
So, $P(Y>s+t|Y>s) = e^{-(s+t)^{1/3}}\cdot e^{s^{1/3}}\neq e^{-t^{1/3}}$
So, $Y$ does not have memoryless property.

(b)
$E(Y) = E(X^{3}) = 3! = 6$.
$Var(Y) = E(X^{6})-(E(X^{3}))^{2} = 6! - 36 = 720-36=684$.
$E(Y^{n}) = E(X^{3n}) = (3n)!$.

(c)
$$
\begin{align}
M_{Y}(t) &= \int _{0}^{\infty}e^{tx^{3}-x} \, dx \\
\end{align}
$$
If $t > 0$, $M_{Y}(t) \to \infty$,
If $t = 0$,
$$
M_{Y}(0) = \int _{0}^{\infty} e^{-x} \, dx= 1 
$$
Similarly, if $t < 0$, $M_{Y}(t)$ has finite value.
Hence, $M_{Y}(t)$ exists only $t \leq 0$, which means MGF of $Y$ does not exists.
___
