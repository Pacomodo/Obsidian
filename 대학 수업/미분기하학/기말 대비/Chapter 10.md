### Chapter 10. Gauss' Theorema Egregium
#### 10.2 Gauss’ remarkable theorem
가우스의 지랄지랄 정리로 부터...

가우스 곡률은 $F = 0$일때 다음과 같음을 상기시킵시다.
> [!Recall]
> $$
K = -\frac{1}{2\sqrt{ EG }}\left[ \frac{ \partial }{ \partial u }\left( \frac{G_{u}}{\sqrt{ EG }} \right) + \frac{ \partial }{ \partial v } \left( \frac{E_{v}}{\sqrt{ EG }} \right)   \right]$$

##### Example 10.2.4
회전면(Surface of revolution)의 방정식을 생각해봅시다.

> [!Recall] 회전면의 방정식
> $$\boldsymbol{\sigma}(u,v) = (f(u)\cos v, f(u)\sin v, g(u))$$

이 방정식은 $xz$평면 위에 놓여있는 곡선 $u \mapsto (f(u), 0, g(u))$을 한 바퀴 돌린 회전면입니다. 편의 상 $f(u) > 0$이라고 합시다. 이 곡선이 단위 속력(unit speed)이라고 가정합시다. 즉, $f'^{2}+g'^{2} = 1$이라고 합시다.
$$
\begin{align}
\boldsymbol{\sigma}_{u} &= (f'\cos v, f'\sin v, g') \\
\boldsymbol{\sigma}_{v} &= (-f\sin v, f\cos v, 0) \\
E &= f'^{2} + g'^{2} = 1 \\
F &= 0 \\
G &= f^{2}
\end{align}
$$

이 회전면의 가우스 곡률을 가.놀.정.으로 부터도 얻어낼 수 있습니다.(Example 8.1.4에서 이미 얻어낸 결과를 상기시킵시다.)
$$
K = -\frac{1}{\sqrt{ G }}\frac{ \partial^{2} \sqrt{ G } }{ \partial u^{2} }= - \frac{f''}{f} 
$$
