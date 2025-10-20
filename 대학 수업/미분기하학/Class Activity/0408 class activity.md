___
곡면
$$
\boldsymbol{\sigma}(u, v) = (u, v, u^{2}-v^{2}), (1,1,0)
$$
에 대해서, 먼저 벡터 함수의 편미분을 구하고:
(1) $\boldsymbol{\sigma}_{u}(1,1) = \frac{ \partial \boldsymbol{\sigma} }{ \partial u }$ at ($u=1, v=1$)
(2) $\boldsymbol{\sigma}_{v}(1,1) = \frac{ \partial \boldsymbol{\sigma} }{ \partial v }$ at ($u=1, v=1$)

다음 두 곡선
$$
\boldsymbol{\gamma}_{1}(t)=(3t,3t,0),
\boldsymbol{\gamma}_{2}(s)=(2-s,s^{2},(2-s)^{2}-s^4)
$$
에 대해
(3) 각각 점 $(1,1,0)$에서의 tangent vectors를 구하고(at $t=\frac{1}{3}$ & $s=1$)

(4) 위의 두 곡선들이 $\boldsymbol{\sigma}$에 의해 주어진 곡면 위에 있는 곡선들이고 점 $\boldsymbol{\sigma}(1,1) = (1,1,0)$을 지나는 것을 확인한 후, (3)에서 구한 접벡터들을 (1), (2)에서 구한 벡터들의 선형 조합(linear combination) 꼴로 써봅시다.

___

**Sol**)
(1) $\boldsymbol{\sigma}_{u}(1,1) = \frac{ \partial \boldsymbol{\sigma} }{ \partial u } = (1,0,2u)_{\text{at }(1,1)} = (1,0,2)$
(2) $\boldsymbol{\sigma}_{v}(1,1) = \frac{ \partial \boldsymbol{\sigma} }{ \partial v } = (0, 1, -2v)_{\text{at }(1,1)} = (0,1,-2)$

(3)
$$
\begin{align}
\boldsymbol{\gamma}'_{1}(t) = (3,3,0), \boldsymbol{\gamma}'_{1}\left( \frac{1}{3} \right) &= (3,3,0), \mathbf{T}_{\boldsymbol{\gamma}_{1}}=\left( \frac{1}{\sqrt{2 }}, \frac{1}{\sqrt{ 2 }}, 0 \right) \\
\boldsymbol{\gamma}'_{2}(s) = (-1,2s,-4s^{3}+2s-4), \boldsymbol{\gamma}'_{2}(1) &= (-1,2,-6), \mathbf{T}_{\boldsymbol{\gamma}_{2}}=\left( -\frac{1}{\sqrt{ 41 }}, \frac{2}{\sqrt{ 41 }},-\frac{6}{\sqrt{ 41 }} \right)
\end{align}
$$
(4) 평면 $\mathbb{R}^{2}$위의 곡선 $\boldsymbol{\alpha}_{1}(t) = (3t, 3t)$을 정의하면, $\boldsymbol{\sigma}\circ\boldsymbol{\alpha}_{1}(t) = \boldsymbol{\gamma}_{1}(t)$임을 확인할 수 있습니다. 마찬가지로, 평면 $\mathbb{R}^{2}$위의 곡선 $\boldsymbol{\alpha}_{2}(t) = (2-s, s^{2})$을 정의하면, $\boldsymbol{\sigma}\circ\boldsymbol{\alpha}_{2}(s) = \boldsymbol{\gamma}_{2}(s)$임을 확인할 수 있습니다. 따라서, 위의 두 곡선들은 각각 $\boldsymbol{\sigma}$에 의해 주어진 곡면 위에 있는 곡선임을 확인할 수 있습니다.
또한, 각각의 함수 $\boldsymbol{\alpha}_{1}(t), \boldsymbol{\alpha}_{2}(s)$에 $t = \frac{1}{3}$과 $s = 1$을 대입하면, $\boldsymbol{\alpha}_{1}\left( \frac{1}{3} \right) = (1,1)$, $\boldsymbol{\alpha}_{2}(1) = (1,1)$이기 때문에 $\boldsymbol{\sigma}(1,1) = (1,1,0)$을 지남을 확인할 수 있습니다.
(3)에서 구한 $\mathbf{T}_{\boldsymbol{\gamma}_{1}}$과 $\mathbf{T}_{\boldsymbol{\gamma}_{2}}$를 (1), (2)에서 구한 벡터들의 선형 조합으로 나타내면 다음과 같이 나타낼 수 있습니다.
$$
\begin{align}
\mathbf{T}_{\boldsymbol{\gamma}_{1}} = \left( \frac{1}{\sqrt{ 2 }}, \frac{1}{\sqrt{ 2 }}, 0 \right) &= \frac{1}{\sqrt{ 2 }} \cdot (1,0,2) + \frac{1}{\sqrt{ 2 }}(0,1,-2) \\
&= \frac{1}{\sqrt{ 2 }}\boldsymbol{\sigma}_{u}(1,1) + \frac{1}{\sqrt{ 2 }}\boldsymbol{\sigma}_{v}(1,1) \\
\mathbf{T}_{\boldsymbol{\gamma}_{2}}=\left( -\frac{1}{\sqrt{ 41 }}, \frac{2}{\sqrt{ 41 }},-\frac{6}{\sqrt{ 41 }} \right)&= -\frac{1}{\sqrt{ 41 }}\cdot(1,0,2) + \frac{2}{\sqrt{ 41 }}\cdot(0,1,-2) \\
&= -\frac{1}{\sqrt{ 41 }}\boldsymbol{\sigma}_{u}(1,1) + \frac{2}{\sqrt{ 41 }}\boldsymbol{\sigma}_{v}(1,1)
\end{align}
$$

___