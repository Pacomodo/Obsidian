___
### Chapter 8. Gaussian, mean and principal curvatures
#### 8.1 Gaussian and mean curvatures
___
##### Propositions 8.1.2
$\boldsymbol{\sigma}$를 방향이 주어진 Surface $\mathcal{S}$의 surface patch라고 합시다. $\boldsymbol{\sigma}$위의 한 점 $\mathbf{p}$가 놓여있고, 이 점의 접평면을 $T_{\mathbf{p}}\mathcal{S}$라고 합시다.
이 상황에서, Weingarten map(와인가르덴 사상) $\mathcal{M}$ 또는 Shape operator (모양 연산자) $S$가 다음과 같이 $S : T_{\mathbf{p}}\mathcal{S} \to T_{\mathbf{p}}\mathcal{S}$로 주어져 있다고 합시다.
이때, Basis $\mathcal{B} = \{\boldsymbol{\sigma}_{u}, \boldsymbol{\sigma}_{v}\}$에 대한 $S$의 행렬 표현은 다음과 같습니다.
$$
[S]_{\mathcal{B}} = \begin{bmatrix}
E & F \\
F & G
\end{bmatrix}^{-1}\begin{bmatrix}
L & M \\
M & N
\end{bmatrix}
$$
___
**이거 존나 중요한 내용이니까, 잘 봅시다.(240513 수업내용)**
$S_{\mathbf{p}}(\mathbf{v}) := -D_{\mathbf{v}}\mathbf{U}$라고 정의함을 상기시킵시다.
즉, 점 $\mathbf{p}$에서 $\mathbf{v}$방향으로 $\mathbf{U}$를 Covarient derivative(공변 미분)한 것입니다. 이때 $\mathbf{v}\in T_{\mathbf{p}}\mathcal{S}$입니다.
이 Proposition에서 떠올려야 할 주요 개념들은 다음과 같습니다.
1. Covarient derivative(공변 미분)의 정의
2. Covarient derivative로 정의한 모양 연산자가 "잘" 정의된 연산인가? 즉, 정말 $T_{\mathbf{p}}\mathcal{S}$에서 $T_{\mathbf{p}}\mathcal{S}$로 가는 연산이 맞는가?
3. 모양 연산자가 Linear Transformation인가? (그래야만 행렬로 표현이 되기 때문)
4. 그렇다면, 행렬로 어떻게 표현하는가?
___
1. Covarient derivative(공변 미분)의 정의

다음과 같은 상황을 상기시켜봅시다.
![[SmartSelect_20240615_033423_Samsung Notes.jpg]]
일변수 함수 $y = f(x)$의 경우, 미분은 오른쪽 한 방향으로만 정의되었습니다.
반면, 이변수 함수 $z = f(x,y)$를 생각하면 여러 방향의 미분을 생각해볼 수 있는데, 이를 **Directional derivative of $f$ at $\mathbf{p}$ in the direction of $\mathbf{v}$(방향미분계수)** 라고 했습니다.
$f : \mathbb{R}^{2} \text{ or } \mathbb{R}^{3} \to \mathbb{R}$이 주어져있다고 합시다.
$D_{\mathbf{v}}f$ 또는, $D_{\mathbf{v},\mathbf{p}}f$는 $\mathbf{p}$점에서 $\mathbf{v}$방향으로 미분한 것을 의미합니다.
즉, 다음과 같이 정의됩니다.
$$
\begin{align}
D_{\mathbf{v}}f &:= \lim_{ t \to 0 } \frac{f(\mathbf{p}+t\mathbf{v})-f(\mathbf{p})}{t}=\lim_{ t \to 0 } \frac{F(t)-F(0)}{t-0}=F'(0) \\
(=D_{\mathbf{v},\mathbf{p}}f) &= \left[\frac{d}{dt} f(\mathbf{p}+t\mathbf{v})\right]_{t=0}
\end{align}
$$
만약 $f:\mathbb{R}^{3}\to \mathbb{R}$이라고 해봅시다.
$$
\begin{align}
(x,y,z) &= \mathbf{p}+t\mathbf{v} \\
&= (x_{0},y_{0},z_{0}) + t(a,b,c)
\end{align}
$$

위의 식을 대입해서 계산하면 다음과 같습니다.
$$
\begin{align}
\left[\frac{d}{dt} f(x,y,z)\right]_{t=0} &= \left[\frac{d}{dt} f(x_{0}+ta, y_{0}+tb, z_{0}+tc)\right]_{t=0} \\
&= \frac{ \partial f }{ \partial x } a + \frac{ \partial f }{ \partial y } b+\frac{ \partial f }{ \partial z } c \\
&=\left( \frac{ \partial f }{ \partial x } ,\frac{ \partial f }{ \partial y } , \frac{ \partial f }{ \partial z }  \right)_{\text{at }\mathbf{p}}\cdot(a,b,c) \\
&= \nabla f(\mathbf{p})\cdot \mathbf{v}
\end{align}
$$
Covarient Derivative는 Directional Derivative의 Generalization입니다.
다음 Vector field를 생각해봅시다.
$$
\begin{align}
\overline{W}:\mathbb{R}^{3}&\to \mathbb{R}^{3} \\
(x,y,z)&\mapsto(f(x,y,z),g(x,y,z),h(x,y,z))
\end{align}
$$
위에서 정의한것과 비슷하게, $D_{\mathbf{v}}\overline{W}$는 다음과 같이 정의됩니다.
$$
\begin{align}
D_{\mathbf{v}}\overline{W} &= \left[\frac{d}{dt}\overline{W}(\mathbf{p}+t\mathbf{v})\right]_{t = 0} \\
&= \left[\frac{d}{dt} (f(\mathbf{p}+t\mathbf{v}),g(\mathbf{p}+t\mathbf{v}),h(\mathbf{p}+t\mathbf{v}))\right]_{t=0} \\
&= \left( \left[ \frac{d}{dt} f(\mathbf{p}+t\mathbf{v}) \right]_{t=0} , \left[ \frac{d}{dt} g(\mathbf{p}+t\mathbf{v}) \right]_{t=0},\left[ \frac{d}{dt} h(\mathbf{p}+t\mathbf{v}) \right]_{t=0}\right) \\
&= (\nabla f(\mathbf{p})\cdot \mathbf{v}, \nabla g(\mathbf{p})\cdot \mathbf{v}, \nabla h(\mathbf{p})\cdot \mathbf{v})
\end{align}
$$
Directional Derivative의 성질들로부터 Covarient Derivative의 성질들을 이끌어낼 수 있는데, 세 가지의 성질이 있습니다.
1. Linear with vector
2. Linear with function

위의 두 성질들은 직접 쉽게 증명할 수 있습니다.(직접 해보는 것을 추천합니다.)
마지막 성질을 서술하기에 앞서, $q(x,y,z) = {<}\overline{W}_{1}, \overline{W}_{2}{>}$라고 합시다. 즉, $q(x,y,z) = f_{1}f_{2}+g_{1}g_{2}+h_{1}h_{2}$라고 합시다. 그러면, 다음 성질이 성립합니다.

3. $D_{\mathbf{v}}q = D_{\mathbf{v}}{<}\overline{W}_{1}, \overline{W}_{2}{>} = {<}D_{\mathbf{v}}\overline{W}_{1}, \overline{W}_{2}{>} + {<}\overline{W}_{1}, D_{\mathbf{v}}\overline{W}_{2}{>}$

즉, 내적에 대해서 분배가 가능합니다.

예시를 들어봅시다.
* Covarient derivative of $\overline{W}(x,y,z) = (x^{2},0,yz)$ at $\mathbf{p} = (2,1,0)$ in the direction of $\mathbf{v}=(-1, 0, 2)$?

$$
\begin{align}
\left[ \frac{d}{dt} \overline{W}(\mathbf{p}+t\mathbf{v}) \right]_{t=0} &= \left[ \frac{d}{dt} \overline{W}(2-t, 1, 2t) \right]_{t=0} \\
&=\left[\frac{d}{dt} ((2-t)^{2}, 0, 2t) \right]_{t=0} \\
&= (-2(2-t), 0, 2)_{t=0} \\
&= (-4, 0, 2)
\end{align}
$$
___
2. Covarient derivative로 정의한 모양 연산자가 "잘" 정의된 연산인가? 즉, 정말 $T_{\mathbf{p}}\mathcal{S}$에서 $T_{\mathbf{p}}\mathcal{S}$로 가는 연산이 맞는가?

Shape operator $S := -D_{\mathbf{v}}\mathbf{U}$임을 상기시킵시다.
즉, 곡면의 Unit normal vector $\mathbf{U}$를 $T_{\mathbf{p}}\mathcal{S}$의 원소 $\mathbf{v}$로 Covarient derivative한 것입니다.
2번에서 이야기하고자 하는 것은 다음과 같은 명제입니다.
* Claim : When $\mathbf{v} \in T_{\mathbf{p}}\mathcal{S}$, $D_{\mathbf{v}}\mathbf{U}\in T_{\mathbf{p}}\mathcal{S}$.

**Proof)**
써먹을 내용은 2가지입니다.
1. $\mathbf{U}$가 unit이어서 같은 걸 내적하면 1이 나옴.
2. Covarient Derivative의 3번째 성질.

$$
\begin{align}
& \lVert \mathbf{U} \rVert = 1 \\
\rightarrow& {<}\mathbf{U}, \mathbf{U}{>} = 1 \\
\xrightarrow{\mathbf{v}\text{로 미분}}& 2{<}\mathbf{U}, D_{\mathbf{v}}\mathbf{U}{>} = 0 \\
\rightarrow&\mathbf{U}\perp D_{\mathbf{v}}\mathbf{U}
\end{align}
$$
이때, $\mathbf{U} \perp T_{\mathbf{p}}\mathcal{S}$이므로, $D_{\mathbf{v}}\mathbf{U} \in T_{\mathbf{p}}\mathcal{S}$임을 보일 수 있습니다.

추가적으로, 다음과 같은 사실을 기억합시다.
* Claim : $\mathbf{U}_{u}$와 $\mathbf{U}_{v}$의 선형 조합으로 $D_{\mathbf{v}}\mathbf{U}$를 표현할 수 있습니다.

증명은 다음과 같습니다.
**Proof)**
먼저, $\mathbf{v} \in T_{\mathbf{p}}\mathcal{S}$라면 $\gamma'(0) = \mathbf{v}$를 만족하는 임의의 곡면 위의 Curve $\gamma = \boldsymbol{\sigma}\circ\alpha$가 존재합니다.
![[SmartSelect_20240616_135115_Samsung Notes.jpg|center|500]]
이때 $D_{\mathbf{v}}\mathbf{U}$를 계산해봅시다.
$$
\begin{align}
D_{\mathbf{v}}\mathbf{U} &= \left[ \frac{d}{dt} \mathbf{U}(u(t), v(t)) \right]_{t=0} \\
&= \left( \frac{ \partial \mathbf{U} }{ \partial u }\frac{ du }{ dt } +\frac{ \partial \mathbf{U} }{ \partial v } \frac{ dv }{ dt } \right)_{t=0} \\
&= \mathbf{U}_{u}(\mathbf{p})\cdot u'(0)+\mathbf{U}_{v}(\mathbf{p})\cdot v'(0)
\end{align}
$$
즉, $D_{\mathbf{v}}\mathbf{U}$는 $\mathbf{U}_{u}(\mathbf{p})$와 $\mathbf{U}_{v}(\mathbf{p})$의 선형 조합으로 표현 가능합니다.

___
3. 모양 연산자가 Linear Transformation인가? (그래야만 행렬로 표현이 되기 때문)

먼저 위에서, $S(\mathbf{v}) = -D_{\mathbf{v}}\mathbf{U} \in T_{\mathbf{p}}\mathcal{S}$임을 보였습니다.(즉, 잘 정의되는 함수임을 보였습니다.)
1번에서 공변 미분의 성질 2가지를 배웠습니다. Linear하다는 성질이었고, 이를 적용하면 다음과 같습니다.
$$
\begin{align}
S(\alpha \mathbf{v}+\beta \mathbf{w}) = -D_{\alpha \mathbf{v}+\beta \mathbf{w}}\mathbf{U} = -\alpha D_{\mathbf{v}}\mathbf{U} -\beta D_{\mathbf{w}}\mathbf{U} = \alpha S(\mathbf{v})+\beta S(\mathbf{w})
\end{align}
$$
따라서 Linear Transformation입니다.

___
4. 그렇다면, 행렬로 어떻게 표현하는가?

임의의 $\mathbf{v} \in T_{\mathbf{p}}\mathcal{S}$에 대해서, $\mathbf{v}$를 $\boldsymbol{\sigma}_{u}$와 $\boldsymbol{\sigma}_{v}$의 선형 결합으로 표현할 수 있음을 상기시킵시다.
이 말은, $\mathbf{v} = (1, 0)$이라면 $\mathbf{v} = \boldsymbol{\sigma}_{u}$라는 말과 동일합니다.
따라서, $\mathbf{v} = \boldsymbol{\sigma}_{u}$ 혹은 $\mathbf{v}=\boldsymbol{\sigma}_{v}$에 대해서 Shape operator를 적용해봅시다.
1. When $\mathbf{v} = \boldsymbol{\sigma}_{u} = (1,0)$.

$$
\begin{align}
S(\boldsymbol{\sigma}_{u}) = -D_{\mathbf{v}}\mathbf{U} = -D_{\boldsymbol{\sigma}_{u}}\mathbf{U} &= -\left[ \frac{d}{dt} \mathbf{U}(u_{0}+t, v_{0}) \right]_{t=0} \\
&= -\mathbf{U}_{u}\frac{ du }{ dt } -\cancel{ \mathbf{U}_{v}\frac{ dv }{ dt } }  \\
&= -\mathbf{U}_{u}
\end{align}
$$
2. When $\mathbf{v} = \boldsymbol{\sigma}_{v} = (0,1)$.

$$
\begin{align}
S(\boldsymbol{\sigma}_{v})=-D_{\mathbf{v}}\mathbf{U} = -D_{\boldsymbol{\sigma}_{v}}\mathbf{U} &= -\left[ \frac{d}{dt} \mathbf{U}(u_{0}, v_{0}+t) \right]_{t=0} \\
&= -\cancel{ \mathbf{U}_{u}\frac{ du }{ dt } } - \mathbf{U}_{v}\frac{ dv }{ dt }  \\
&= -\mathbf{U}_{v}
\end{align}
$$
선형대수 내용을 상기시켜봅시다.
![[SmartSelect_20240617_025221_Samsung Notes.jpg|center|500]]
따라서, $S(\boldsymbol{\sigma}_{u}) = -\mathbf{U}_{u} = a\boldsymbol{\sigma}_{u}+b\boldsymbol{\sigma}_{v}$, $S(\boldsymbol{\sigma}_{v}) = -\mathbf{U}_{v} = c \boldsymbol{\sigma}_{u}+d\boldsymbol{\sigma}_{v}$라고 합시다.
우리가 원하는 행렬은 다음과 같습니다.
$$
[S]_{\mathcal{B}} = \begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
$$
$a,b,c,d$를 결정지어봅시다.
$-\mathbf{U}_{u} = a\boldsymbol{\sigma}_{u}+b\boldsymbol{\sigma}_{v}$에서 양 변에 $\boldsymbol{\sigma}_{u}$를 내적해보면 $L = aE + bF$임을 확인할 수 있습니다.
마찬가지로, 양 변에 $\boldsymbol{\sigma}_{v}$, $-\mathbf{U}_{v}$일 때도 똑같이 해주면 다음과 같은 결과를 얻을 수 있습니다.
$$
\begin{cases}
L = aE+bF \\
M = aF+bG \\
M = cE+dF \\
N = cF+dG
\end{cases}
$$
이를 행렬로 표현하면 다음과 같습니다.
$$
\begin{bmatrix}
L & M \\
M & N
\end{bmatrix}=\begin{bmatrix}
E & F \\
F & G
\end{bmatrix}\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}
$$
따라서, 
$$
[S]_{\mathcal{B}} = \begin{bmatrix}
a & c \\
b & d
\end{bmatrix} =\begin{bmatrix}
E & F \\
F & G
\end{bmatrix}^{-1}\begin{bmatrix}
L & M \\
M & N
\end{bmatrix}
$$
___
##### Examples 8.1.4
Chapter 7에서 정의했던 회전면의 방정식을 생각해봅시다.
$$\boldsymbol{\sigma}(u,v) = (f(u)\cos v, f(u)\sin v, g(u))$$
$f'^{2}+g'^{2}=1$, $f>0$을 만족합니다.
$E, F, G, L, M, N$을 구하면 다음과 같습니다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (f'\cos v,f'\sin v,g') \\
\boldsymbol{\sigma}_{v} &= (-f\sin v,f\cos v, 0) \\
E, F, G &= 1, 0, f^{2}
\end{align}
$$
$L, M, N$은 Chapter 7의 내용을 사용하면 다음과 같습니다.
$$
L, M, N = f'g''-f''g', 0,fg'
$$
$f'^{2}+g'^{2}=1$의 양 변을 $u$로 미분하면 다음과 같은 식을 얻을 수 있습니다.
$f'f''+g'g''=0\rightarrow f'f'' = -g'g''$
가우스 곡률의 정의를 상기하여, 가우스 곡률을 구하면 다음과 같습니다.
$$
K = \frac{LN - M^{2}}{EG-F^{2}} = \frac{(f'g''-f''g')fg'}{f^{2}}=\frac{f'g'g''-f''g'g'}{f}=\frac{-f''(f'f'+g'g')}{f}=\frac{-f''}{f}
$$

##### Examples 8.1.7

##### Exercises 8.1.1

> [!Question] Problem
> $z = f(x,y)$에 대하여 Gaussian, Mean curvature를 구해보세요.

##### Exercises 8.1.2
> [!Question] Problem
> Calculate the Gaussian curvature of the helicoid and the catenoid, deﬁned in Exercises 4.2.6 and 5.3.1, respectively.
> $$\boldsymbol{\sigma}(u,v)=(u\cos v, u\sin v, v)$$
> $$\boldsymbol{\sigma}(u,v) = (\cosh u \cos v, \cosh u \sin v, u)$$
##### Exercises 8.1.6

> [!Question] Problem
> Show that the Weingarten map $\mathcal{W}$ of a surface satisﬁes the quadratic equation $$\mathcal{W}^{2} − 2H\mathcal{W} + K = 0$$in the usual notation.

**Proof)**
Note that $\mathcal{W}$ is symmetric matrix, So, $\mathcal{W}$ is diagonalizable.
Let $\mathcal{W} = Q^{-1}\begin{pmatrix}\kappa_{1}&0\\0&\kappa_{2}\end{pmatrix}Q$ where $\kappa_{1}, \kappa_{2}$ is eigenvalue of $\mathcal{W}$, which is principal curvature.
We want to use Cayley-Hamilton theorem.
Therefore, $\mathcal{W}^{2}-\text{tr}(\mathcal{W})\mathcal{W} + \det(\mathcal{W})I =0$.
Note that, $\text{tr}(\mathcal{W}) = \kappa_{1}+\kappa_{2} = 2H$ and $\det(\mathcal{W}) = \kappa_{1}\kappa_{2}=K$.
아니면 직접 제곱해서 계산해도 된다.
___
#### 8.2 Principal curvatures of a surface
##### Proposition 8.2.6
Principal Curvature은 아래 행렬식의 근이다.
$$
\begin{vmatrix}
L - \lambda E & M-\lambda F \\
M-\lambda F & N-\lambda G
\end{vmatrix} =0
$$

##### Examples 8.2.7
Unit Sphere의 Principal Curvature를 위의 행렬식을 통해 구해봄.
##### Examples 8.2.8
Unit Cylinder의 Principal Curvature를 위의 행렬식을 통해 구해봄.
##### Examples 8.2.10
Unit Sphere, Circular Cylinder, Plane에 대해서 Principal Curvature를 논하고, Elliptic, Parabolic, Planar를 논함.
##### Examples 8.2.11
Torus에 대한 Principal Curvature를 논함.
##### Exercises 8.2.1

> [!Question] Problem
> Calculate the principal curvatures of the helicoid and the catenoid, deﬁned in Exercises 4.2.6 and 5.3.1, respectively.
> $$\boldsymbol{\sigma}(u,v)=(u\cos v, u\sin v, v)$$
> $$\boldsymbol{\sigma}(u,v) = (\cosh u \cos v, \cosh u \sin v, u)$$

**Proof)**
직접 해보셈
#### 8.5 Surfaces of constant mean curvature
##### Exercises 8.5.2

> [!Question] Problem
>  Prove that $H = 0$ for the surface $$z = \ln\left( \frac{\cos y}{\cos x} \right)$$

**Proof)**
Class Activity 0520


  


  



  

