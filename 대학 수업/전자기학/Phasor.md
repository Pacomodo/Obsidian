시간에 따라 진동하는 전기장 $\mathbf{E}(t,z)$가 다음과 같이 주어져 있다고 합시다.
$$
\mathbf{E}(z, t) = \mathbf{E}_{0}\cos(\omega t+\theta(z))
$$
이때, $\theta(z)$는 $z$에 따라 변화하는 함수입니다.
오일러 공식에 의해 다음과 같이 작성할 수 있습니다.
$$
\begin{align}
\mathbf{E}(z, t) &= \mathbf{E}_{0}\cos(\omega t+\theta(z)) \\
&= \mathrm{Re}[\mathbf{E}_{0}e^{j(\omega t+\theta(z))}] \\
&=\mathrm{Re}[\mathbf{E}_{0}e^{j\theta(z)}e^{j\omega t}] \\
&=\mathrm{Re}[\tilde{\mathbf{E}}e^{j\omega t}]
\end{align}
$$
이때, $\tilde{\mathbf{E}} = \mathbf{E}_{0}e^{j\theta(z)}$를 $\mathbf{E}(z,t)$의 Phasor라고 합니다.
Phasor의 의미를 잘 생각해보면, 기존 진폭 $\mathbf{E}_{0}$와 각도 $\theta(z)$를 결합한 것이라고 생각할 수 있습니다.