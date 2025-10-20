___
공지사항에 올린 Gauss-Bonnet theorem handout 파일의 56쪽 첫번째 등식을 증명해봅시다. 
$$
(e_{1})_{v}\cdot e_{2} = \frac{G_{u}}{2\sqrt{ EG }}
$$
___
Sol)
$e_{1}$과 $e_{2}$가 접평면 $T_{p}S$의 직교기저를 정규화 한 것임을 상기시킵시다. 즉, 다음 식을 상기시킵시다.
$$
e_{1}=\frac{\boldsymbol{\sigma}_{u}}{\sqrt{ \boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{u} }} = \frac{\boldsymbol{\sigma}_{u}}{\sqrt{ E }},e_{2}=\frac{\boldsymbol{\sigma}_{v}}{\sqrt{ \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v} }} = \frac{\boldsymbol{\sigma}_{v}}{\sqrt{ G }} 
$$
곱의 미분법을 사용합시다.
$$
\begin{align}
(e_{1})_{v}\cdot e_{2} &= \left( \frac{\boldsymbol{\sigma}_{u}}{\sqrt{ E }} \right)_{v}\cdot e_{2} \\
&= \left[ \frac{\boldsymbol{\sigma}_{uv}}{\sqrt{ E }} + \boldsymbol{\sigma}_{u}\left( \frac{1}{\sqrt{ E }} \right)_{v} \right]\cdot e_{2} \\
&=\frac{\boldsymbol{\sigma}_{uv}\cdot \boldsymbol{\sigma}_{v}}{\sqrt{ EG }}
\end{align}
$$
마지막 등호에서는 $\boldsymbol{\sigma}_{u}\cdot \boldsymbol{\sigma}_{v} = 0$이기 때문에 뒤의 항이 사라집니다.
$G = \boldsymbol{\sigma}_{v}\cdot \boldsymbol{\sigma}_{v}$를 $u$로 편미분하면 다음과 같습니다.
$$
G_{u} = 2\boldsymbol{\sigma}_{uv}\cdot \boldsymbol{\sigma}_{v}
$$
따라서, 마지막 식을 다음과 같이 변형시킬 수 있습니다.
$$
(e_{1})_{v}\cdot e_{2} = \frac{G_{u}}{2\sqrt{ EG }}
$$
___
