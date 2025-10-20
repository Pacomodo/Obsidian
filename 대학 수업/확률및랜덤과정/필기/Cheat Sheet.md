* $\text{Expo}(\lambda):f(x) = \lambda e^{-\lambda x}$; $E(X)=\frac{1}{\lambda}, Var(X)=\frac{1}{\lambda^{2}}$
* CDF: $\iint_{R}f_{X,Y}(x,y)dxdy$
* $f_{X, Y}(x, y)=f_{Y|X}(y|x)\cdot f_{X}(x)=f_{X|Y}(x|y)\cdot f_{Y}(y)$
* Indep$\Leftrightarrow$$f_{X,Y}(x,y) = f_{X}(x)f_{Y}(y)$ for all $x, y$$\Rightarrow$$\text{Cov}(X, Y)=0$
* $E(g(X,Y))=\iint_{R}g(x,y)f_{X,Y}(x,y)dxdy$ (2D LOTUS)
* $\text{Cov}(X,Y)=E(XY)-E(X)E(Y)$
* Chicken lays $\text{Pois}(\lambda)$ number $N$ of eggs, $X$=number of hatch, $X|N\sim \text{Bin}(n, p)$, $Y$=number of not hatch. $X, Y$ are indep. $X\sim \text{Pois}(p\lambda)$.
* $\text{Pois}(\lambda): \frac{e^{-\lambda}\lambda^{k}}{k!}$; $E(X)=Var(X)=\lambda$. Interpret as rate of occurence.
* $\text{Corr}(X, Y)=\frac{\text{Cov}(X,Y)}{\sqrt{ Var(X)Var(Y) }}$
* $$\begin{align}\text{Cov}(X,X) &= Var(X)\\ \text{Cov}(X, Y) &= \text{Cov}(Y, X)\\ \text{Cov}(X, c)&=0\\ \text{Cov}(aX, Y)&=a\text{Cov}(X, Y) \\ \text{Cov}(X+Y, Z)&=\text{Cov}(X, Z)+\text{Cov}(Y, Z) \\ Var(X+Y) &= Var(X)+Var(Y)+2\text{Cov}(X,Y)\\ \rightarrow Var(X_{1}+\cdots+X_{n})&=Var(X_{1})+\cdots+Var(X_{n})+2\sum_{i<j}\text{Cov}(X_{i},X_{j})\end{align}$$
* $$\begin{align}\text{Sum of indep Pois}&\rightarrow \text{Pois}\\ X\sim \text{Pois}(\lambda_{1}), Y\sim \text{Pois}(\lambda_{2})&\rightarrow X+Y\sim \text{Pois}(\lambda_{1}+\lambda_{2})\end{align}$$
* $X,Y$ i.i.d. $\text{Expo}(\lambda)$ $\rightarrow$ $\min(X,Y)\sim \text{Expo}(2\lambda)$; $M-m$ is indep to $m$; $M-m\sim \text{Expo}(\lambda)$
* Joint MGF: $E(e^{t_{1}X_{1}+t_{2}X_{2}+\cdots})$ = (2개일때 2D LOTUS 사용)
* if $X_{1},\dots ,X_{n}$ are indep, $M_{X}(t) = E\left( \prod e^{tX} \right)\Rightarrow \prod M_{X}(t) = \prod E(e^{tX})$.
* Mutivariate Normal(Jointly Gaussian) $\Leftrightarrow$ $t_{1}X_{1}+\cdots+t_{k}X_{k}$ is gaussian for all $t_{1},\dots, t_{k}$.
* 여기선 $\text{Cov}=0\rightarrow$indep. ex) $X+Y, X-Y$, i.i.d $\mathcal{N}(0,2)$.
* if $k=2$, Bivariate Normal.
* if $(X_{1}, \dots, X_{n})$ is jointly gaussian $\xleftarrow{\text{X}}\xrightarrow{\text{O}}$ $X_{i}$ is gaussian
* ex) $X\sim \mathcal{N}(0,1)$, $Y\sim SX$ where $S=1\text{or -1}$ with $\frac{1}{2}$ prob. $Y\sim \mathcal{N}(0, 1)$. But $(X,Y)$ are not.
* Gaussian: $\varphi(z) = \frac{1}{\sqrt{ 2 }\pi}e^{-z^{2}/2}\sim \mathcal{N}(0,1)$, $X=\mu+\sigma z$, mean $\mu$, Var $\sigma^{2}$.
* Moment: $M(t) = E(e^{tX})$
* $n$th moment $E(X^{n})=\frac{d^{n}}{dt^{n}}M(t)|_{t=0}=M^{(n)}(0)$
* Bernoulli: $M(t)=e^{t}p+1-p$, $E(X)=p$
* Geometric: $M(t) = \frac{p}{1-(1-p)e^{t}}$, $E(X) = \frac{1-p}{p}$, $\text{FS}$일땐 $\frac{1}{p}$, $Var(X) = \frac{1-p}{p^{2}}$, $P(X=k)=(1-p)^{k}p$, $\text{FS}$는 $(1-p)^{k-1}p$
* Uniform: $M(t) = \frac{e^{tb}-e^{ta}}{t(b-a)} (t\neq 0), 1(t=0)$, $Var(X) = \frac{(b-a)^{2}}{12}$
* Binom: $M(t) = (pe^{t}+q)^{n}$, $E(X)=np, Var(X) = np(1-p)$
* Normal: $M(t) = e^{\mu t+\sigma^{2}t^{2}/2}\Rightarrow E(Z^{2n})=(2n-1)!!$ 홀수는 $0$
* Expo: $M(t) = \frac{\lambda}{\lambda-t}\Rightarrow E(X^{n})=\frac{n!}{\lambda^{n}}$
* Pois: $M(t)=e^{\lambda(e^{t}-1)}$
* Joint PDF factors $g(x)h(y)$ where$g(x), h(y) > 0$ for all $x, y$ $\rightarrow$ $X, Y$ indep.
* 변수 바꾸기(1변수)
* 1. 단조증가/감소 일때 $f_{Y}(y) = f_{X}(x)\cdot \frac{1}{\left\lvert  \frac{dy}{dx}  \right\rvert}=f_{X}(x)\cdot \left\lvert  \frac{dx}{dy}  \right\rvert$
* 2. 그외 $\rightarrow$ CDF미분
* Maximum of indep r.v's
* $X=\max\{X_{1},\dots , X_{n}\}$, $X_{i}$ are indep. $F_{X}(x) = \prod_{i=1}^{n}F_{X_{i}}(x)$.
* if $X_{i}$ are i.i.d. $\rightarrow$ $F_{X}(x) = [F_{X_{1}}(x)]^{n}, f_{X}(x)=n[F_{X_{1}}(x)]^{n-1}\cdot f_{X_{1}}(x)$
* Minumum of indep r.v's
* $F_{X}(x) = 1-\prod_{i=1}^{n}(1-F_{X_{i}}(x))$.
* if $X_{i}$ are i.i.d. $\rightarrow$ $F_{X}(x) = 1-(1-F_{X_{1}}(x))^{n}, f_{X}(x) = n(1-F_{X_{1}}(x))^{n-1}\cdot f_{X_{1}}(x)$
* ex) min of $\text{Expo}$'s = $X\sim \text{Expo}(\lambda_{1}+\cdots+\lambda_{n})$
* 변수 바꾸기(다변수)
* $f_{\mathbf{Y}}(\mathbf{y})=f_{\mathbf{X}}(g^{-1}(\mathbf{y}))\cdot \frac{1}{\left\lvert  \det \left( \frac{ \partial \mathbf{y} }{ \partial \mathbf{x} } \right)  \right\rvert}$
* $$\frac{ \partial \mathbf{y} }{ \partial \mathbf{x} }=\begin{pmatrix}\frac{ \partial y_{1} }{ \partial x_{1} } & \frac{ \partial y_{1} }{ \partial x_{2} }  & \cdots \\ \frac{ \partial y_{2} }{ \partial x_{1} }  & \frac{ \partial y_{2} }{ \partial x_{2} }  & \cdots \\ \vdots  & \vdots & \ddots \end{pmatrix}$$
* $\Gamma(n) = (n-1)!$
* $$\Gamma(a)=\int _{0}^{\infty}x^{a-1}e^{-x} \, dx =\int _{0}^{\infty}\lambda^{a}x^{a-1}e^{-\lambda x} \, dx$$ (where $\lambda>0$)
* $X\sim \text{Beta}(a,b):f(x)=\frac{1}{\beta(a,b)}x^{a-1}(1-x)^{b-1}; 0<x<1$
* $$\beta(a,b) = \frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)}=\int _{0}^{1}x^{a-1}(1-x)^{b-1} \, dx=\frac{1}{(a+b-1){a+b-2 \choose a-1}}$$
* $a=1,b=1\Leftrightarrow\text{Unif}(0,1)$
* Baye's Billiards: $n+1$ balls, $1$ gray ball, randomly throw in $(0,1)$, $G\sim \text{Unif}(0,1)$, $X=$number of white balls to the left of gray
* $$P(X=k)=\int _{0}^{1}P(X=k|G=p)f_{G}(p) \, dp =\int _{0}^{1}{n \choose k} p^{k}(1-p)^{n-k} \, dp = \frac{1}{n+1}$$
* For beta distribution, $$E(X^{n})=\frac{\Gamma(a+n)\Gamma(b)}{\Gamma(a+b+n)} \frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)};\ E(X) = \frac{a}{a+b};\ Var(X) = \frac{ab}{(a+b)^{2}(a+b+1)}$$
* Gamma distribution
* $X\sim \text{Gamma}(a,\lambda)\Rightarrow \frac{1}{\Gamma(a)}\lambda (\lambda x)^{a-1}e^{-\lambda x}\Rightarrow \text{Gamma}(1,\lambda)=\text{Expo}(\lambda)$
* $X_{1},\dots,X_{n}$ be i.i.d. $\text{Expo}(\lambda)\rightarrow$ $X_{1}+\cdots+X_{n}\sim \text{Gamma}(n,\lambda)$
* Example) A device is working with indep $3$ components. each of them $\sim \text{Expo}(1)$. Device is not working when all components are not working. What is probability of device working $>$ 3 years? (Sol) $X\sim \text{Gamma}(3,1)$ where $X$ = life time of device. $P(X>3)=\frac{1}{\Gamma(3)}\int _{x=3}^{\infty}x^{2}e^{-x} \, dx$
* $X\sim \text{Gamma}(a,\lambda); \ E(X) = \frac{a}{\lambda}; \ Var(X) = \frac{a}{\lambda^{2}}; \ E(X^{n}) = \frac{1}{\lambda^{n}} \frac{\Gamma(a+n)}{\Gamma (a)}$
* Beta gamma connection: indep $X\sim \text{Gamma}(a,\lambda), Y\sim \text{Gamma}(b,\lambda)$
* $T=X+Y\sim \text{Gamma}(a+b,\lambda); \ W=\frac{X}{X+Y}\sim \text{Beta}(a,b)$, $T,W$ are indep
* $\text{Gamma}(a,\lambda)+\text{Gamma}(b,\lambda)=\text{Gamma}(a+b,\lambda)$
* t-distribution($\text{student}(n),t(n)$)
* $T=\frac{X}{\sqrt{ (X_{1}^{2}+\cdots+X_{n}^{2}) / n }}$ $X,X_{1},\dots,X_{n}$ are i.i.d. $\mathcal{N}(0,1)$.
* $f_{T}(t) = \frac{\Gamma\left( \frac{n+1}{2} \right)}{\sqrt{ \pi }\Gamma\left( \frac{n}{2} \right)}\left( 1+\frac{t^{2}}{n} \right)^{-(n+1)/2} \frac{1}{\sqrt{ n }}$
* $T_{1}\sim \text{Expo}(\lambda_{1}),T_{2}\sim \text{Expo}(\lambda_{2})$, indep $\rightarrow$ $P(T_{1}<T_{2})=\frac{\lambda_{1}}{\lambda_{1}+\lambda_{2}}$
* Conditional Expectation $$E(Y|A)=\int yf(y|A) \, dy \ / \ f(y|A)= \frac{d}{dy} F(Y\leq y|A)=\frac{P(A|Y=y)f(y)}{P(A)}$$
* Adam's law $E(E(Y|X))=E(Y)$
* LOTE $E(Y) = \sum_{i}E(Y|A_{i})P(A_{i})$
* $E(Y|X)=g(x)=E(Y|X=x)=\int yf(y|X=x) \, dy$, So, $E(E(Y|X)), Var(E(Y|X))$ is ok.
* $X,Y$ indep $\rightarrow$ $E(Y|X)=E(Y)$
* $E(h(X)Y|X)=h(X)E(Y|X)$
* $E(E(Y|X,Z)|Z)=E(Y|Z)$
* For any function $h$, $Y-E(Y|X)$ (call residual) is uncorrelated with $h(X)$ $\Leftrightarrow$ $E((Y-E(Y|X))h(X))=0$
* Linear regression $$\begin{align}E(Y|X) = a+bX, \ Y=a+bX+\varepsilon, \ E(\varepsilon|X)=0 \\ b = \frac{\text{Cov}(X,Y)}{Var(X)}, \ a = E(Y) - \frac{\text{Cov}(X,Y)}{Var(X)}E(X)\end{align}$$
* Conditional Variance $$Var(Y|X)=E(Y^{2}|X)-(E(Y|X))^{2} \text{ (function  of }X)$$
* Eve's law $Var(Y)=E(Var(Y|X))+Var(E(Y|X))$
* Random sum
* $N$ customers in a day where $N$ is r.v. with finite $E(N), Var(N)$. $X_{j}$: amount of spent by $j$th customer, $E(X_{j})=\mu, Var(X_{j})=\sigma^{2}$. $N,X_{j}$ are indep. Let $X = \sum X_{j}$. $E(X), Var(X)=?$. (Sol) $E(X|N)=N\mu$, $E(X) = \mu E(N)$, $Var(X|N)=N\sigma^{2}$, $Var(X)=\sigma^{2}E(N)+\mu^{2}Var(N)$
* Inequalities$$\begin{align}\lvert E(XY) \rvert\leq \sqrt{ E(X^{2})E(Y^{2}) }\\P(\lvert X \rvert \geq a )\leq \frac{E(\lvert X \rvert )}{a} \ (a>0) \\ P(\lvert X-\mu \rvert \geq a) \leq \frac{\sigma^{2}}{a^{2}} \\ P(X\geq a) \leq \frac{E(e^{tX})}{e^{ta}} \end{align}$$ $X$ has $Var = \sigma^{2}, \text{mean}=\mu$. $Var(\bar{X_{n}})=\frac{\sigma^{2}}{n}$ where $\bar{X_{n}}=\frac{1}{n}\sum X_{i}$
* $Q=\begin{pmatrix}q_{11}&q_{12}&\cdots&q_{1M}\\ \vdots & \vdots &\ddots & \vdots\end{pmatrix}$
* Markov prop $\approx$ 이전에 영향 X $\Leftrightarrow$ $P(X_{n+1}=j|X_{n}=i)=P(X_{n+1}=j|X_{n}=i, \dots)$
* Recurrent: $i$에서 시작해서 결국 돌아오는 확률이 1
* Transient: $i$에서 시작해서 다시 못돌아올 확률이 존재
* Irriducible: $i$에서 유한한 step으로 $j$까지 가는 것이 가능
* Irriducible $\rightarrow$ all states recurrent
* Period of state $i$ = $i$에서 시작해서 $i$로 돌아오는 step들의 gcd = $d_{i}$
* State $i$가 aperiodic $\Leftrightarrow$ $d_{i} = 1$
* 모든 state가 aperiodic $\Leftrightarrow$ Chain이 aperiodic
* Irreducible periodic $\rightarrow$ $d_{i}=d_{j}$ for all $i, j$
* Irreducible chain is aperiodic $\Leftrightarrow$ $Q^{n}(i, j)>0$ for all $i, j$
* Irreducible Marcov chain with selfloop $\rightarrow$ aperiodic
* Stationary distribution: $\mathbf{s}Q=\mathbf{s}$
* Irreducible $\rightarrow$ unique stationary distribution
* irreducible, aperiodic $\rightarrow$ $\lim_{ n \to \infty }Q^{n} = \begin{pmatrix}\mathbf{s}\\\mathbf{s}\\ \vdots \end{pmatrix}$
* irreducible with $\mathbf{s}$ $\rightarrow$ $r_{i}$ = $i$에서 시작해서 $i$로 돌아오는 기대 시간. $s_{i} =\frac{1}{r_{i}}$
* Reversibility (=detailed balance condition): $s_{i}q_{ij}=s_{j}q_{ji}$ for all $i, j$
* reversible $\rightarrow$ stationary
* 열의 합이 전부 1 $\rightarrow$ $\left( \frac{1}{M}, \dots , \frac{1}{M} \right)$이 stationary
* Random walk on an undirected graph $$\mathbf{s}=\frac{1}{\sum d_{i}}\mathbf{d}, \mathbf{d}=(d_{1},\dots ,d_{n}), d_{j}=\text{node j의 degree}$$
* CLT(Central limit theorem): $X_{1}, X_{2}, \dots$ i.i.d with $\mu, \sigma^{2}$. $\bar{X_{n}}=\frac{1}{n}(X_{1}+\cdots+X_{n})$. as $h\to \infty$, $\bar{X_{n}}\sim \mathcal{N}\left( E(X), \frac{Var(X)}{n} \right)$
* $Y\sim \text{Pois}(n)=\sum_{n}\text{Pois}(1)$, $n\to \infty, Y\sim \mathcal{N}(n,n)$
* $Y\sim \text{Gamma}(n,\lambda)=\sum\text{Expo}(\lambda)$, $n\to \infty, Y\sim \mathcal{N}\left( \frac{n}{\lambda}, \frac{n}{\lambda^{2}} \right)$
* $Y\sim \text{Bin}(n,p)=\sum\text{Bern}(p), n\to \infty, Y\sim \mathcal{N}(np, np(1-p))$
* Birth-death chain $\rightarrow$ reversible, stationary; Birth-death chain: $\lvert i-j \rvert=1$일때 $q_{ij} > 0$이고 $\lvert i-j \rvert>2$일때 $q_{ij}=0$인 chain. $$s_{j}=s_{1} \frac{q_{12}q_{23}\cdots q_{j-1j}}{q_{jj-1}q_{j-1j-2}\cdots q_{21}}$$
* Ex) (Ehrenfest): 1번 바구니와 2번 바구니가 있음. $M$개의 particle이 모두 1번 바구니에 있음. particle임의로 선택해서 다른 바구니로 옮김. $s_{i}={M \choose i}\left( \frac{1}{2} \right)^{M}$
* Coupon collector = reducible
* Chicken egg with unknown parameters
* $X$는 매일 부화한 달걀 수. 닭은 $N$개의 알 낳음. $N\sim \text{Pois}(\lambda)$. $p$= 알의 부화확률. $p$는 모름. $p \sim \text{Beta}(a, b)$. $N$은 직접 접근 못함. $X$만 관찰 가능. $X|p \sim \text{Pois}(\lambda p)$. $$\begin{align}f(p|X=x) &= \frac{e^{-\lambda p}(\lambda p)^{x}p^{a-1}q^{b-1}}{\int _{0}^{1} e^{-\lambda p}(\lambda p)^{x}p^{a-1}q^{b-1} \, dp } \\ f(p|X=x, N = n) &\sim \text{Beta}(x+a, n-x+b) \\ f(N|X=x, P=p) &\sim \text{Pois}(\lambda(1-p))+x\end{align}$$
* 