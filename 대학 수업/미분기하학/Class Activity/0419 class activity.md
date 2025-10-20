___
곡면이 $\boldsymbol{\sigma}(u,v) = (u,v,u^{2}+v^{2})$로 주어졌을때, 이 곡면 위에 있는 곡선 $\gamma(t) = (\cos t,\sin t,1)$의 (1) curvature $\kappa$, (2) normal curvature $\kappa_{n}$, (3) geodesic curvature $\kappa_{g}$를 구해봅시다.
___
(1) 곡선 $\gamma(t)$의 속력을 구하기 위해 미분해봅시다.
$\gamma'(t) = (-\sin t, \cos t, 0) \to \lVert \gamma' \rVert = \sqrt{ \sin ^{2}t + \cos ^{2}t } = 1$이므로, 일반적인 속력에 대한 곡률 공식을 사용하지 않아도 됩니다. 즉, $\gamma(t)$는 Unit speed Curve임을 확인할 수 있습니다. 더불어, $\gamma'(t) = \mathbf{T}(t)$임을 확인할 수 있습니다.
따라서, $\lVert \mathbf{T'}(t) \rVert = \kappa(t) = \sqrt{ \cos ^{2}t + \sin ^{2}t} = 1$임을 확인할 수 있습니다.
(2) Normal Curvature $\kappa_{n}$을 구하기 위해 $\boldsymbol{\sigma}$의 Normal unit vector field $\mathbf{U}$를 구해봅시다.
$\mathbf{U} = \frac{\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v}}{\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert}$이므로, 각각의 편미분을 계산해봅시다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (1,0,2u) \\
\boldsymbol{\sigma}_{v} &= (0,1,2v) \\
\boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} &= (-2u, -2v, 1) \\
\lVert \boldsymbol{\sigma}_{u}\times \boldsymbol{\sigma}_{v} \rVert &= \sqrt{ 4u^{2}+4v^{2}+1 }
\end{align}
$$
더불어, $\gamma(t) = \boldsymbol{\sigma}(\alpha(t)) = \boldsymbol{\sigma}(u(t), v(t)) = (\cos t, \sin t, 1)$이므로, $\alpha(t) = (\cos t, \sin t)$임을 확인할 수 있습니다. 따라서, $\mathbf{U}(t)$는 다음과 같습니다.
$$
\begin{align}
\mathbf{U}(u,v) &= \frac{1}{\sqrt{ 4u^{2}+4v^{2}+1 }}(-2u, -2v, 1) \\
\mathbf{U}(t) &= \frac{1}{\sqrt{ 5 }}(-2\cos t, -2\sin t, 1)
\end{align}
$$
$\kappa_{n}(t)=\frac{\gamma''\cdot \mathbf{U}}{\lVert \gamma' \rVert^{2}}$이므로, $\kappa_{n}(t) = (-\cos t, -\sin t, 0)\cdot\frac{1}{\sqrt{ 5 }}(-2\cos t, -2\sin t, 1) = \frac{2}{\sqrt{ 5 }}$임을 확인할 수 있습니다.
(3) Geodesic Curvature $\kappa_{g}$는 $\sqrt{ \kappa^{2}-\kappa_{n}^{2} }$이므로, $\frac{1}{\sqrt{ 5 }}$임을 확인할 수 있습니다.
