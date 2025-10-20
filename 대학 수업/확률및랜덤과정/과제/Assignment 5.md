###### 1. Let $X$ and $Y$ be i.i.d. $\text{Expo}(1)$. Find the CDF and PDF of $Z=\lvert X-Y \rvert$.

Sol)
The CDF of $Z$ is
$$
F_{Z}(z) = P(Z\leq z) = P(\lvert X-Y \rvert\leq z ) = 1-P(\lvert X-Y \rvert > z)
$$
where $z \geq 0$.
Note that
$$
P(\lvert X-Y \rvert>z ) = P(X-Y > z)+P(Y-X>z) = 2P(X-Y>z)
$$
since $X$ and $Y$ are i.i.d.
Since $X$ and $Y$ are independent, $f_{X,Y}(x,y) = e^{-x}e^{-y}$ for $x,y\geq 0$.
So,
$$
\begin{align}
P(X-Y>z) &= P(X>Y+z) \\
&= \int _{y=0}^{\infty}P(X>y+z)f_{Y}(y) \, dy \\
&= \int _{y=0}^{\infty}e^{-(y+z)}e^{-y} \, dy  \\
&=e^{-z} \int _{y=0}^{\infty} e^{-2y}\, dy = \frac{e^{-z}}{2}
\end{align}
$$
So,
$$
F_{Z}(z) = 1-e^{-z}
$$
for $z \geq 0$.
$$
f_{Z}(z) = e^{-z}
$$
for $z\geq 0$.

###### 2. A stick of length $L$ (a positive constant) is broken at a uniformly random point $X$. Given that $X = x$, another breakpoint $Y$ is chosen uniformly on the interval $[0, x]$.

(a) Find the joint PDF of $X$ and $Y$. Be sure to specify the support.
(b) Find the marginal distribution of $Y$.
(c) Find the conditional PDF of $X$ given $Y = y$.

Sol)
(a)
The conditional PDF of $Y$ given $X=x$ is
$$
f_{Y|X}(y|x) = \frac{1}{x} \text{ if }y \in[0, x] \text{ else }0
$$
Also PDF of $X$ is
$$
f_{X}(x) = \frac{1}{L} \text{ if }x \in [0, L] \text{ else } 0
$$
So, $f_{X,Y}(x,y)$ is
$$
f_{X,Y}(x, y) = \frac{1}{Lx}
$$
for $0 \leq y \leq x \leq L$.

(b)
$$
f_{Y}(y) = \int_{x=y}^{L} f_{X,Y}(x,y) \, dx = \frac{1}{L}(\ln L-\ln y) 
$$
for $y \in (0, L]$.

(c)
$$
\begin{align}
f_{X|Y}(x|y) &= \frac{f_{X,Y}(x,y)}{f_{Y}(y)} \\
&=\frac{1}{x(\ln L - \ln y)}
\end{align}
$$
for given $Y = y, x \in [y, L]$.

###### 3. Let $X$ and $Y$ have joint PDF $$f_{X,Y}(x,y) = cxy, \text{ for } 0<x<y<1.$$
(a) Find $c$ to make this a valid joint PDF.
(b) Are $X$ and $Y$ independent?
(c) Find the marginal PDFs of $X$ and $Y$.
(d) Find the conditional PDF of $Y$ given $X=x$.

Sol)
(a)
$$
\begin{align}
1 &= \int _{y=0}^{y=1}\int_{x=0}^{x=y} f_{X,Y}(x,y) \, dx  \, dy \\
&= \int _{y=0}^{y=1}\int_{x=0}^{x=y} cxy \, dx  \, dy \\
&= c\int _{y=0}^{y=1} \frac{1}{2}y^{3} \, dy \\
&= \frac{c}{8}
\end{align}
$$
So, $c=8$.

(b)
No. Since the support of $X$ and $Y$ are dependent.

(c)
$$
\begin{align}
f_{X}(x) &= \int _{y=x}^{y=1} 8xy\, dy =4x-4x^{3} \\
f_{Y}(y) &= \int _{x=0}^{x=y} 8xy\, dx=4y^{3} 
\end{align}
$$
where $0 < x< 1$ and $0 < y < 1$.

(d)
$$
f_{Y|X}(y|x) = \frac{f_{X,Y}(x,y)}{f_{X}(x)} = \frac{8xy}{4x-4x^{3}}=\frac{2y}{1-x^{2}}
$$
for $y \in [x, 1]$.

###### 4. Let $(X, Y)$ be a uniformly random point in the triangle in the plane with vertices $(0, 0), (0, 1), (1, 0)$.

(a) Find the joint PDF of $X$ and $Y$.
(b) Find the marginal PDF of $X$.
(c) Find the conditional PDF of $X$ given $Y$.
(d) Find $\text{Cov}(X, Y)$.

Sol)
(a)
Note that the area of triangle is $1 /2$.
So,
$$
f_{X,Y}(x,y) = 2
$$
for $x\geq 0,y\geq 0,x+y\leq 1$, otherwise $0$.

(b)
$$
\begin{align}
f_{X}(x) &= \int _{y=0}^{y=1-x} 2\, dy=2-2x 
\end{align}
$$
for $x \in [0, 1]$

(c)
$$
\begin{align}
f_{Y}(y) &= \int _{x=0}^{x=1-y}2 \, dx=2-2y \\
 f_{X|Y}(x|y) &= \frac{f_{X,Y}(x,y)}{f_{Y}(y)}  \\
&= \frac{2}{2-2y} = \frac{1}{1-y}
\end{align}
$$
for $y \in [0, 1], x \in [0, 1-y]$.

(d)
$$
\begin{align}
E(XY) &= \int _{x=0}^{x=1}\int _{y=0}^{y=1-x} 2xy\, dy \, dx \\
&=\int _{0}^{1}x(1-x)^{2} \, dx \\
&= \int _{0}^{1} x^{3}-2x^{2}+x \, dx  \\
&= \frac{1}{4}-\frac{2}{3}+\frac{1}{2} =\frac{1}{12}  
\end{align}
$$
$$
\begin{align}
E(X) = E(Y) = \int _{0}^{1}(2x-2x^{2})\, dx=1-\frac{2}{3} = \frac{1}{3} 
\end{align}
$$
$$
\text{Cov}(X,Y) = \frac{1}{12}-\frac{1}{9} = -\frac{1}{36}
$$

###### 5. A chicken lays a $\text{Pois}(\lambda)$ number $N$ of eggs. Each egg hatches a chick with probability $p$, independently. Let $X$ be the number which hatch, so $X|N = n ∼ \text{Bin}(n, p)$. Find the correlation between $N$ (the number of eggs) and $X$ (the number of eggs which hatch).

Sol)
$$
\text{Corr}(X, N) = \frac{\text{Cov}(X, N)}{\sqrt{ \text{Var}(X)\text{Var}(N) }}
$$
Since $X \sim \text{Pois}(\lambda p)$, $\text{Var}(X) = p\lambda$ and $\text{Var}(N) = \lambda$, $E(X) = p\lambda$, $E(N) = \lambda$.
$$
\text{Cov}(X, N) = E(XN) - E(X)E(N)
$$
Using the fact that $N = X + (N-X)$.
$$
E(NX) = E(X^{2}) + E((N-X)X)
$$
We know that $(N-X)$ and $X$ are both independent,
$$
E((N-X)X) = (E(N) -E(X))E(X) = \lambda^{2}p(1-p)
$$
We know that $E(X^{2}) =\lambda p + \lambda^{2}p^{2}$, so, $E(NX) = \lambda p(1+\lambda)$.
So,
$$
\text{Cov}(X, N) = \lambda p(1+\lambda) - \lambda^{2}p = \lambda p
$$
Hence,
$$
\text{Corr}(X, N) = \sqrt{ p }
$$

###### 6. Let $X = V+W, Y = V+Z$, where $V, W, Z$ are i.i.d. $\text{Pois}(\lambda)$.

(a) Find $\text{Cov}(X, Y)$.
(b) Find the conditional joint PMF of $X, Y$ given $V$, $P(X=x, Y=y|V=v)$.

Sol)
(a)
$$
\begin{align}
\text{Cov}(X, Y) &= \text{Cov}(V+W, V+Z) \\
&= \text{Cov}(V, V)+\text{Cov}(V, Z) + \text{Cov}(W, V) + \text{Cov}(W, Z) \\
&= \text{Var}(V) = \lambda
\end{align}
$$
(b)
Given $V=v$, $X = v+W$ and $Y = v+Z$ are independent.
Also,
$$
P(X=x|V=v) = P(W=x-v) = \frac{e^{-\lambda}\lambda^{x-v}}{(x-v)!}
$$
Similliarly,
$$
P(Y=y|V=v) = P(Z = y-v) = \frac{e^{-\lambda}\lambda^{y-v}}{(y-v)!}
$$
Since, $X$ and $Y$ are independent given $V = v$,
$$
P(X=x, Y=y|V=v) = \frac{e^{-\lambda}\lambda^{x-v}}{(x-v)!}\frac{e^{-\lambda}\lambda^{y-v}}{(y-v)!}
$$
for $x, y \geq v$.

###### 7. Let $X$ and $Y$ be i.i.d. $\mathcal{N}(0,1)$, and let $S$ be a random sign ($1$ or $-1$, with equal probabilities) independent of $(X, Y)$.

(a) Determine whether or not $(X, Y, SX+SY)$ is Multivariate Normal.
(b) Determine whether or not $(SX, SY)$ is Multivariate Normal.

Sol)
(a)
No.
Consider $P(X+Y+SX+SY = 0) = P(S=-1) = 1 /2$, it means, $X+Y+SX+SY$ can not be Gaussian.
(b)
Yes.
When $S = 1$, $(SX, SY) = (X,Y)$, when $S=-1, (SX, SY) = (-X,-Y) = (X,Y)$.
So, $(SX,SY)$ is same distribution as $(X,Y)$, which is multivariate normal.

###### 8. Consider a two-dimensional jointly Gaussian random vector $\mathbf{X} = [X, Y]^{T}$ with the mean vector $\mu = [\mu_{X}, \mu_{Y}]^{T}$ and the covariance matrix $$\Sigma = \begin{bmatrix}\sigma^{2}_{X}  & \text{Cov}(X,Y) \\ \text{Cov}(X, Y) & \sigma^{2}_{Y}\end{bmatrix}$$. Let the correlation coefficient of $X$ and $Y$ be $\rho$. Show that the joint pdf given in the matrix form $$f_{XY}(\mathbf{x})=\frac{1}{\sqrt{ (2\pi)^{2}\lvert \det \Sigma \rvert  }}\exp\left( -\frac{1}{2}(\mathbf{x}-\mu)^{T}\Sigma ^{-1}(\mathbf{x}-\mu) \right),$$ for $\mathbf{x} = [x,y]^{T}$ is equivalent to the following form $$f_{XY}(x,y) = \frac{1}{2\pi \sigma_{X}\sigma_{Y}\sqrt{ 1-\rho^{2} }}e^{\left( -\frac{1}{2(1-\rho^{2})}\left[ \left(\frac{x-\mu_{x}}{\sigma_{X}}\right)^{2} -2\rho\frac{(x-\mu_{X})(y-\mu_{Y})}{\sigma_{X}\sigma_{Y}} + \left( \frac{y-\mu_{Y}}{\sigma_{Y}} \right)^{2}\right] \right)}$$

Sol)
Note that $\text{Cov}(X,Y) = \rho\sigma_{X}\sigma_{Y}$. So,
$$\Sigma = \begin{bmatrix}\sigma^{2}_{X}  & \rho\sigma_{X}\sigma_{Y} \\ \rho\sigma_{X}\sigma_{Y} & \sigma^{2}_{Y}\end{bmatrix}$$
So,
$$
\det \Sigma = (1-\rho^{2})\sigma^{2}_{X}\sigma^{2}_{Y}
$$
So,
$$
\frac{1}{\sqrt{ (2\pi)^{2}\lvert \det \Sigma \rvert  }} = \frac{1}{2\pi \sigma_{X}\sigma_{Y}\sqrt{ 1-\rho^{2} }}
$$
Note that for $2\times 2$ matrix,
$$
\Sigma = \begin{bmatrix}
a & b \\
b & d
\end{bmatrix}, \Sigma ^{-1}=\frac{1}{\det \Sigma}\begin{bmatrix}
d &-b \\
-b & a
\end{bmatrix}
$$
So,
$$
\Sigma ^{-1}=\frac{1}{\sigma^{2}_{X}\sigma^{2}_{Y}(1-\rho^{2})}\begin{bmatrix}
\sigma_{Y}^{2} & -\rho \sigma_{X}\sigma_{Y} \\
-\rho\sigma_{X}\sigma_{Y} & \sigma_{X}^{2}
\end{bmatrix}
$$
$$
\begin{align}
&-\frac{1}{2}(\mathbf{x}-\mu)^{T}\Sigma ^{-1}(\mathbf{x}-\mu)\\
&=-\frac{1}{2\sigma^{2}_{X}\sigma^{2}_{Y}(1-\rho^{2})}\begin{bmatrix}
x-\mu_{X} & y-\mu_{Y}
\end{bmatrix}\begin{bmatrix}
\sigma_{Y}^{2} & -\rho \sigma_{X}\sigma_{Y} \\
-\rho\sigma_{X}\sigma_{Y} & \sigma_{X}^{2}
\end{bmatrix}\begin{bmatrix}
x-\mu_{X} \\
y-\mu_{Y}
\end{bmatrix} \\
&= -\frac{1}{2(1-\rho^{2})}\left[ \left(\frac{x-\mu_{x}}{\sigma_{X}}\right)^{2} -2\rho\frac{(x-\mu_{X})(y-\mu_{Y})}{\sigma_{X}\sigma_{Y}} + \left( \frac{y-\mu_{Y}}{\sigma_{Y}} \right)^{2}\right]
\end{align}
$$
