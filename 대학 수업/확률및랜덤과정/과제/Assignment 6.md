###### 1. For $Z\sim \mathcal{N}(0,1)$
(a) Find the PDF of $Z^{3}$.
(b) Find the PDF of $Z^{4}$.

Sol)
(a)
Let $X = Z^{3}$.
Starting from CDF.
$$
\begin{align}
F_{X}(x) &= P(Z^{3}\leq x) = P(Z \leq \sqrt[3]{ x }) = \Phi(\sqrt[3]{ x })  \\
f_{X}(x) &= \frac{d}{dx}F(x) = \varphi(\sqrt[3]{x})\cdot \frac{1}{3}x^{-2/3} \\
&=\boxed{ \frac{1}{3\sqrt{ 2\pi }}e^{-x^{2/3}/2}x^{-2/3}  }
\end{align}
$$
(b)
Let $Y = Z^{4}$.
Starting from CDF.
$$
\begin{align}
F_{Y}(y) &= P(Z^{4}\leq y) = P(-\sqrt[4]{y}\leq Z\leq \sqrt[4]{y})=\Phi(\sqrt[4]{y}) - \Phi(-\sqrt[4]{y}) \\
&=2\Phi(\sqrt[4]{y})-1 \\
f_{Y}(y) &= \frac{d}{dy}F(y) = 2\varphi(\sqrt[4]{ y })\cdot \frac{1}{4}y^{-3/4} = \frac{1}{2} \varphi(\sqrt[4]{ y })y^{-3/4} \\
&= \boxed{ \frac{1}{2\sqrt{ 2\pi }}e^{-y^{1/2}/2}y^{-3/4}, \ \ y \geq 0. }
\end{align}
$$

###### 2. Let $U\sim \text{Unif}\left( 0, \frac{\pi}{2} \right)$. Find the PDF of $\sin(U)$.

Sol)
Note that CDF of $U$ is $\frac{2}{\pi}x$ where $0 \leq x \leq \frac{\pi}{2}$.
Let $Y = \sin(U)$.
$$
\begin{align}
F_{Y}(y) &= P(Y \leq y) = P(\sin(U)\leq y) = P(U\leq \arcsin(y)) = \frac{2}{\pi}\arcsin(y) \\
f_{Y}(y) &= \frac{d}{dy}F(y) = \boxed{ \frac{2}{\pi\sqrt{ 1-y^{2} }}, \ \ 0 \leq y \leq 1 }
\end{align}
$$

###### 3. Let $X$ and $Y$ have joint PDF $f_{X,Y}(x,y)$, and transform $(X, Y)\mapsto(T, W)$ linearly by letting $$T=aX+bY \text{ and }W=cX+dY,$$ where $a,b,c,d$ are constants such that $ad - bc \neq 0$.
(a) Find the joint PDF $f_{T,W}(t, w)$ (in terms of $f_{X, Y}$ as a function of $t$ and $w$).
(b) For a special case where $T = X+Y, W = X-Y,$ write down $f_{T,W}(t, w)$.

Sol)
(a)
Let this transform $g$.
Then,
$$
\mathbf{y}=g(\mathbf{x}) \rightarrow \begin{bmatrix}
t \\
w
\end{bmatrix} = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}
$$
Let's consider Jacobian matrix $\frac{ \partial \mathbf{y} }{ \partial \mathbf{x} }$.
$$
\frac{ \partial \mathbf{y} }{ \partial \mathbf{x} } = \begin{pmatrix}
\frac{ \partial t }{ \partial x }  & \frac{ \partial t }{ \partial y }  \\
\frac{ \partial w }{ \partial x }  & \frac{ \partial w }{ \partial y } 
\end{pmatrix} =\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$
So,
$$
\begin{align}
f_{\mathbf{Y}}(\mathbf{y}) &= f_{T,W}(t, w) \\
&= \frac{1}{\left\lvert  \det\left( \frac{ \partial \mathbf{y} }{ \partial \mathbf{x} }  \right)  \right\rvert }f_{\mathbf{X}}(g^{-1}(\mathbf{y})) \\
&= \frac{1}{|ad-bc|}f_{X,Y}(g^{-1}(t, w)) \\
&=\boxed{ \frac{1}{|ad-bc|}f_{X,Y}\left( \frac{dt-bw}{ad-bc}, \frac{-ct+aw}{ad-bc} \right) }
\end{align}
$$
(b)
If $T = X+Y, W=X-Y$, then, $a=b=c=1$ and $d = -1$, So,
$$
f_{T,W}(t,w) = \boxed{ \frac{1}{2}f_{X,Y}\left( \frac{t+w}{2}, \frac{t-w}{2} \right) }
$$

###### 4. Let $X$ and $Y$ be independent positive r.v.s, with PDFs $f_{X}$ and $f_{Y}$, respectively. Let $T$ be the ratio $X / Y$ and $W = X$.
(a) Find the joint PDF of $T$ and $W$, using a Jacobian.
(b) Find the marginal PDF of $T$, as a single integral.

Sol)
(a)
Note that since $X$ and $Y$ are independent, the joint PDF of $X$ and $Y$ is $f_{X,Y}(x,y) = f_{X}f_{Y}$.
Let $[T, W] = g([X, Y])$ be an invertible function from $\mathbb{R}^{2}\to \mathbb{R}^{2}$ and $\mathbf{y} = [t,w]$ and $\mathbf{x} = [x, y]$.
Then, the joint PDF of $T$ and $W$ is
$$
\begin{align}
f_{T, W}(t, w) &= \frac{1}{\left\lvert  \det\left( \frac{ \partial \mathbf{y} }{ \partial \mathbf{x} }  \right)  \right\rvert}f_{X,Y}(g^{-1}([t,w])) \\
&= \frac{y^{2}}{x}f_{X,Y}(x, y) \\
&=\boxed{ \frac{w}{t^{2}}f_{X}(x)f_{Y}(y) = \frac{w}{t^{2}}f_{W}(w)f_{Y}\left( \frac{w}{t} \right) }
\end{align}
$$
(b)
Note that $X$ and $Y$ are positive random variables. The marginal PDF of $T$ is
$$
f_{T}(t) = \int _{0}^{\infty}f_{T,W}(t,w) \, dw = \boxed{ \frac{1}{t^{2}}\int _{0}^{\infty}f_{W}(w)f_{Y}\left( \frac{w}{t} \right) \, dw }
$$

###### 5. Let $X$ and $Y$ be i.i.d. $\text{Expo}(\lambda)$, and transform them to $T=X+Y, W=X / Y$.
(a) Find the joint PDF of $T$ and $W$. Are they independent?
(b) Find the marginal PDFs of $T$ and $W$.

Sol)
(a)
Let $X, Y$ be $\mathbf{x}$ and $T, W$ be $\mathbf{y}$. Consider the Jacobian $J$.
$$
J = \left\lvert  \frac{ \partial \mathbf{y} }{ \partial \mathbf{x} }   \right\rvert = \begin{bmatrix}
\frac{ \partial t }{ \partial x }  & \frac{ \partial t }{ \partial y }  \\
\frac{ \partial w }{ \partial x }  & \frac{ \partial w }{ \partial y } 
\end{bmatrix} = \begin{bmatrix}
1 & 1 \\
\frac{1}{y} & -\frac{x}{y^{2}}
\end{bmatrix}
$$
So,
$$
\begin{align}
f_{T,W}(t,w) &= \frac{1}{\lvert \det J \rvert } f_{X,Y}(x,y) \\
&= \frac{y^{2}}{x+y}f_{X}(x)f_{Y}(y) \\
&= \frac{t}{(w+1)^{2}}\lambda^{2} \exp\left( -\frac{\lambda wt}{w+1} \right)\exp\left( -\frac{\lambda t}{w+1} \right) \\
&=\boxed{ \frac{t}{(w+1)^{2}}\lambda^{2}\exp(-\lambda t) \text{ for }t,w > 0}
\end{align}
$$
Since they factored into two nonnegative functions, they are independent.

(b)
$$
\begin{align}
f_{T}(t) &= \int_{0}^{\infty} \frac{t}{(w+1)^{2}}\lambda^{2}\exp(-\lambda t) \, dw  \\
&= t\lambda^{2}\exp(-\lambda t)\left[ -\frac{1}{w+1} \right]^{\infty}_{0} \\
&=\boxed{ t\lambda^{2}\exp(-\lambda t) \text{ for }t > 0} 
\end{align}
$$
$$
\begin{align}
f_{W}(w) &= \frac{\lambda^{2}}{(w+1)^{2}}\int _{0}^{\infty}t\exp(-\lambda t) \, dt \\
&= \frac{\lambda^{2}}{(w+1)^{2}}\left[ -\frac{\exp(-\lambda t)(\lambda t+1)}{\lambda^{2}} \right]^{\infty}_{0} \\
&= \boxed{ \frac{1}{(w+1)^{2}} \text{ for } w>0}
\end{align}
$$

###### 6. Let $X$ and $Y$ be i.i.d. $\text{Unif}(0,1)$. Find the joint distribution $U = X+Y$ and $V = X-Y$.

Sol)
Use the result of problem 3,
$$
\begin{align}
f_{U,V}(u,v) &= \frac{1}{2}f_{X,Y}\left( \frac{u+v}{2}, \frac{u-v}{2} \right) \\
&=\frac{1}{2} \text{ where } 0 \leq u+v \leq 2 \text{ and }0 \leq u-v \leq 2 \text{ (diamond shape region)}
\end{align}
$$

###### 7. Let $X$ and $Y$ be i.i.d. Gaussian Normal $\mathcal{N}(0,1)$. Let $$R=\sqrt{ X^{2}+Y^{2} }$$ and $$U=\begin{cases}\tan ^{-1}(Y / X) & x>0 \\\tan ^{-1}(Y / X) +\pi& x<0, y \geq 0 \\\tan ^{-1}(Y / X) - \pi & x<0, y < 0\end{cases}$$ Find the pdf of $R$.

Sol)
We will make marginal pdf of $R$ using joint pdf of $R$ and $U$.
We can consider transformation $(X, Y)$ into $(R, U)$ as coordinate change from Cartesian into polar.
Hence, $X = R\cos U, Y=R\sin U$.
Consider the Jacobian determinant
$$
J = \left\lvert  \frac{ \partial (X,Y) }{ \partial (R,U) }   \right\rvert = \begin{vmatrix}
\cos u & -r\sin u \\
\sin u & r\cos u
\end{vmatrix} = r
$$
$$
\begin{align}
f_{R, U}(r, u) &= \lvert J \rvert f_{X,Y}(x,y) \\
&= \frac{r}{2\pi}\exp\left( -\frac{x^{2}+y^{2}}{2} \right) \\
&= \frac{r}{2\pi}\exp\left( -\frac{r^{2}}{2} \right)
\end{align}
$$
Now, integrate it from $-\pi$ to $\pi$.
$$
f_{R}(r) = \int _{-\pi}^{\pi}f_{R,U}(r,u) \, du = \boxed{ r \exp\left( -\frac{r^{2}}{2} \right) \text{ for }r \geq 0 }
$$

###### 8. Let $T$ and $V$ be random variables with the joint pdf $$f_{T,V}(t,v)=\frac{1}{\sqrt{ \pi }\Gamma(n / 2)} \frac{1}{2^{(n+1)/2}} \frac{1}{\sqrt{ n }} v^{(n+1)/2 - 1}\exp\left( -\frac{v}{2}\left( 1+\frac{t^{2}}{n} \right) \right) \text{ (for }v > 0\text{)}$$. Compute the marginal pdf of $T$.

Sol)
Integrate the joint pdf with $v$ from $0$ to $\infty$.
$$
\begin{align}
f_{T}(t) &= \frac{1}{\sqrt{ \pi }\Gamma(n / 2)} \frac{1}{2^{(n+1)/2}} \frac{1}{\sqrt{ n }} \int _{0}^{\infty} v^{(n+1)/2 - 1}\exp\left( -\frac{v}{2}\left( 1+\frac{t^{2}}{n} \right) \right) \, dv
\end{align}
$$
Note that by definition of gamma function,
$$
\int _{0}^{\infty} x^{k-1}e^{-\lambda x}\, dx =\frac{\Gamma(k)}{\lambda^{k}}
$$
Using this, let $k = (n+1) / 2, \lambda = (1+t^{2} / n) / 2$.
Then,
$$
\begin{align}
f_{T}(t) &= \frac{1}{\sqrt{ \pi }\Gamma(n / 2)} \frac{1}{2^{(n+1)/2}} \frac{1}{\sqrt{ n }} \int _{0}^{\infty} v^{(n+1)/2 - 1}\exp\left( -\frac{v}{2}\left( 1+\frac{t^{2}}{n} \right) \right) \, dv \\
&= \frac{1}{\sqrt{ \pi }\Gamma(n / 2)} \frac{1}{2^{(n+1)/2}} \frac{1}{\sqrt{ n }} \Gamma\left( \frac{n+1}{2} \right) \frac{2^{(n+1)/2}}{\left( 1+\frac{t^{2}}{n} \right)^{(n+1)/2}} \\
&= \boxed{ \frac{\Gamma\left( \frac{n+1}{2} \right)}{\sqrt{ n\pi }\Gamma(n / 2)} \left( 1+\frac{t^{2}}{n} \right)^{-(n+1)/2}}
\end{align}
$$
