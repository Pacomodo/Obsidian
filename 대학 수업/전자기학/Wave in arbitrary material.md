이전에 Conductor, Dielectrics, Magnetic materials에 대해 다뤘고 다음과 같은 관계를 가졌었다.
$$
\begin{align} 
\mathbf{J}_{c} &= \sigma \mathbf{E} \\
\mathbf{D} &= \varepsilon \mathbf{E} \\
\mathbf{B} &= \mu \mathbf{H}
\end{align}
$$
이때, $(\sigma, \varepsilon, \mu)$ 혹은, $(\sigma, \varepsilon_{r}, \mu_{r})$을 **Constitutive Parameters**이라고 정의한다.
물질의 특성은 이러한 Parameters에 의해 결정된다.
___
다음과 같은 상황을 가정하자.
![[Pasted image 20241212111510.png|center|300]]
$\mathbf{J}_{s}(t) = -J_{S_{0}}\cos \omega t\mathbf{a}_{x}$로 정의된다.(Sinusoidal하게 변화함.)
또한, Current sheet 양쪽의 매질은 $(\sigma, \varepsilon, \mu)$라는 Constitutive Parameter를 가지고 있다.
이제 여기서 $\mathbf{E}, \mathbf{H}$를 찾는 것이 우리의 목적이다.
___
Faraday's Law와 Ampere's Circuit Law에 의해 임의의 위치에 대하여 다음이 성립한다. (임의의 위치에서 고려하므로 Point form을 사용함에 유의하자. 또한, 우리는 Infinite sheet위에서 따지는 것이 아니라 $z>0, z<0$인 영역에서 고려함에 유의하자.)
$$
\begin{align}
\nabla \times \mathbf{E} &= -\frac{ \partial \mathbf{B} }{ \partial t } =-\mu \frac{ \partial \mathbf{H} }{ \partial t } \\
\nabla \times \mathbf{H} &= \mathbf{J}+\frac{ \partial \mathbf{D} }{ \partial t } \\
\xrightarrow{z<0, z>0}&= \sigma \mathbf{E} + \varepsilon \frac{ \partial \mathbf{E} }{ \partial t }    
\end{align}
$$
위의 편미분 방정식은 $\sigma \mathbf{E}$ term때문에 해결하기 힘드므로, [[Phasor]] 개념을 사용하여 해결할 수 있다.
Phasor에 의해 $\mathbf{E}, \mathbf{H}$를 다음과 같이 작성할 수 있다.
$$
\mathbf{E} = \mathrm{Re}[\tilde{\mathbf{E}}e^{j\omega t}], \mathbf{H}=\mathrm{Re}[\tilde{\mathbf{H}}e^{j\omega t}]
$$
이를 통해 위의 식을 정리하면 다음과 같다.
$$
\begin{align}
\nabla \times \mathrm{Re}[\tilde{\mathbf{E}}e^{j\omega t}] &= -\mu \frac{ \partial  }{ \partial t } \mathrm{Re}[\tilde{\mathbf{H}}e^{j\omega t}] \\
\nabla \times \mathrm{Re}[\tilde{\mathbf{H}}e^{j\omega t}] &= \sigma \mathrm{Re}[\tilde{\mathbf{E}}e^{j\omega t}]+\varepsilon \frac{ \partial  }{ \partial t } \mathrm{Re}[\tilde{\mathbf{E}}e^{j\omega t}]
\end{align}
$$
이때, 미분 연산자와 $\mathrm{Re}$ 모두 선형적이므로, 독립적으로 작용한다. 따라서 둘 사이에는 교환법칙이 성립한다. 이를 통해 식을 다시 작성할 수 있다.
$$
\begin{align}
\mathrm{Re}[\nabla \times(\tilde{\mathbf{E}}e^{j\omega t})] &= \mathrm{Re}\left[ -\mu \frac{ \partial  }{ \partial t } (\tilde{\mathbf{H}}e^{j\omega t}) \right] \\
\mathrm{Re}[\nabla \times(\tilde{\mathbf{H}}e^{j\omega t})] &= \mathrm{Re}\left[ \tilde{\sigma}\mathbf{E}e^{j\omega t}+\varepsilon \frac{ \partial  }{ \partial t } (\tilde{\mathbf{E}}e^{j\omega t}) \right]
\end{align}
$$
다시 작성하면,
$$
\begin{align}
\mathrm{Re}[(\nabla \times\tilde{\mathbf{E}})e^{j\omega t}] &= \mathrm{Re}\left[ -\mu \frac{ \partial  }{ \partial t } (\tilde{\mathbf{H}}e^{j\omega t}) \right]  \\
\Rightarrow \mathrm{Re}[(\nabla \times\tilde{\mathbf{E}})e^{j\omega t}] &= \mathrm{Re}\left[ -\mu j\omega \tilde{\mathbf{H}}e^{j\omega t} \right] \\
\mathrm{Re}[(\nabla \times\tilde{\mathbf{H}})e^{j\omega t}] &= \mathrm{Re}\left[ \sigma\tilde{\mathbf{E}}e^{j\omega t}+\varepsilon \frac{ \partial  }{ \partial t } (\tilde{\mathbf{E}}e^{j\omega t}) \right] \\
\Rightarrow \mathrm{Re}[(\nabla \times\tilde{\mathbf{H}})e^{j\omega t}] &= \mathrm{Re}\left[ (\sigma\tilde{\mathbf{E}}+\varepsilon j\omega\tilde{\mathbf{E}})e^{j\omega t}) \right] 
\end{align}
$$
실수부에 대한 방정식이 성립한다고 해서 복소수가 성립한다고 볼 수는 없다.
하지만, 위의 두 식은 임의의 시간 $t$와 공간 변수 $z$에 대해서 성립하는 식이다.
다시 말해, 두 변수를 임의로 잡아도 성립해야 하는 식이다.
식의 형태를 보면, 왼쪽과 오른쪽 모두 $e^{j\omega t}$가 곱해진 후에 $\mathrm{Re}$연산자를 취하고 있다. $e^{j\omega t}$를 곱한다는 뜻은 복소 평면에서 $\omega t$만큼 회전한다는 뜻이다.
근데, **모든 시간 $t$에 대해서 성립하는** 식이므로, 실수부만 취한 위의 두 식이 근본적으로 같기 위해서는 Phasor가 같아야 한다. 따라서 다음이 성립한다.
$$
\begin{align}
\nabla \times  \tilde{\mathbf{E}} &= -\mu j\omega \tilde{\mathbf{H}} \\
\nabla \times \tilde{\mathbf{H}} &= \sigma \tilde{\mathbf{E}} + \varepsilon j\omega \tilde{\mathbf{E}}
\end{align}
$$
이 식을 이제 풀어서 작성해보자.
$$
\begin{align}
&\left( \frac{ \partial \tilde{E}_{z} }{ \partial y } - \frac{ \partial \tilde{E}_{y} }{ \partial z }   \right)\mathbf{a}_{x} + \left( \frac{ \partial \tilde{E}_{x} }{ \partial z } - \frac{ \partial \tilde{E}_{z} }{ \partial x }   \right)\mathbf{a}_{y} +\left( \frac{ \partial \tilde{E}_{y} }{ \partial x } - \frac{ \partial \tilde{E}_{x} }{ \partial y }   \right)\mathbf{a}_{z}  \\
&= -j\omega \mu \tilde{H}_{x}\mathbf{a}_{x}-j\omega \mu \tilde{H}_{y}\mathbf{a}_{y}-j\omega \mu \tilde{H}_{z}\mathbf{a}_{z} \\
&\left( \frac{ \partial \tilde{H}_{z} }{ \partial y } - \frac{ \partial \tilde{H}_{y} }{ \partial z }   \right)\mathbf{a}_{x} + \left( \frac{ \partial \tilde{H}_{x} }{ \partial z } - \frac{ \partial \tilde{H}_{z} }{ \partial x }   \right)\mathbf{a}_{y} +\left( \frac{ \partial \tilde{H}_{y} }{ \partial x } - \frac{ \partial \tilde{H}_{x} }{ \partial y }   \right)\mathbf{a}_{z}  \\
&= (\sigma \tilde{E}_{x}+j\omega\varepsilon \tilde{E}_{x})\mathbf{a}_{x} + (\sigma \tilde{E}_{y}+j\omega\varepsilon \tilde{E}_{y})\mathbf{a}_{y} + (\sigma \tilde{E}_{z}+j\omega\varepsilon \tilde{E}_{z})\mathbf{a}_{z}
\end{align}
$$
우리는 $z=0$ surface위에서 $\mathbf{J}_{s}$의 방향이 $-x$임을 알고있다. Uniform plane wave와 마찬가지인 상황으로, $\mathbf{J}_{s}$에 의해 생성되는 $\mathbf{E}$와 $\mathbf{H}$ field의 component는 각각 $x, y$ component만 존재하므로, 다음과 같이 식을 정리할 수 있다.
$$
\begin{align}
\frac{ \partial \tilde{E}_{x} }{ \partial z } &= -j\omega \mu \tilde{H}_{y} \\
-\frac{ \partial \tilde{H}_{y} }{ \partial z } &= \sigma \tilde{E}_{x}+j\omega \varepsilon \tilde{E}_{x} 
\end{align}
$$
연립하면 다음과 같다.
$$
\frac{ \partial^{2} \tilde{E}_{x} }{ \partial z^{2} } = -j\omega \mu \frac{ \partial \tilde{H}_{y} }{ \partial z } = \underbrace{ j\omega \mu(\sigma+j\omega\varepsilon) }_{ \gamma^{2} }\tilde{E}_{x} 
$$
이때 괄호 친 부분을 $\gamma^{2}$로 정의한다면, $\tilde{E}_{x}$의 일반해를 다음과 같이 작성할 수 있다.
$$
\tilde{E}_{x}=Ae^{-\gamma z} + Be^{\gamma z}
$$
여기서 $A, B$는 모두 임의의 Complex number이고, $\gamma = \alpha+j\beta$라고 하자. 일반해를 오일러 공식을 사용해 Exponential form으로 바꾸면,
$$
\tilde{E}_{x}(z) = \lvert A \rvert e^{j\theta}e^{-\alpha z}e^{-j\beta z} + \lvert B \rvert e^{j\phi}e^{\alpha z}e^{j\beta z}
$$
이제 시간에 따른 변화를 생각하기 위해 $e^{j\omega t}$ term을 곱하고, $\mathrm{Re}$연산자를 취하자.
$$
\begin{align}
E_{x}(z, t) &= \mathrm{Re}[\tilde{E}_{x}(z)e^{j\omega t}] \\
&= \mathrm{Re}[\lvert A \rvert e^{-\alpha z}e^{j(\theta-\beta z+\omega t)} + \lvert B \rvert e^{\alpha z}e^{j(\phi + \beta z + \omega t)}] \\
&=\lvert A \rvert e^{-\alpha z}\cos(\omega t -\beta z+\theta) + \lvert B \rvert e^{\alpha z}\cos(\omega t + \beta z + \phi)
\end{align}
$$
이때, $z < 0$인 영역에서는 Positive wave($\cos(\omega t-\beta z+\theta)$)가 존재할 수 없으므로, 다음과 같은 Electric field가 생성된다.
$$
\mathbf{E}(z, t) =\left\{ \begin{aligned}
&\lvert A \rvert e^{-\alpha z}\cos(\omega t-\beta z+\theta)\mathbf{a}_{x} &\text{for }z>0 \\
&\lvert B \rvert e^{\alpha z}\cos(\omega t+\beta z+\phi)\mathbf{a}_{x}  &\text{for }z<0
\end{aligned}\right.
$$
$e^{-\alpha z}$나 $e^{\alpha z}$와 같은 term이 곱해져 있는 것을 확인할 수 있다. 이는 각각 $z$의 절댓값이 증가할 때, 즉, Wave가 $+z$혹은 $-z$방향으로 진행할 때 $e^{-\alpha \lvert z \rvert}$만큼 곱해져서 감쇠함을 의미한다.
여기서 $\alpha$를 **Attenuation Constant(감쇠 상수)** 라고 부른다.
$$
\begin{align}
\frac{ \partial \tilde{E}_{x} }{ \partial z } &= -j\omega \mu \tilde{H}_{y} \\
-\frac{ \partial \tilde{H}_{y} }{ \partial z } &= \sigma \tilde{E}_{x}+j\omega \varepsilon \tilde{E}_{x} 
\end{align}
$$
이제 $\tilde{H}_{y}$를 구하기 위해 첫번째 식과 이전에 구했던 $\tilde{E}_{x}$를 이용하자.
$$
\begin{align}
\frac{ \partial \tilde{E}_{x} }{ \partial z } &= -j\omega \mu \tilde{H}_{y}  \\
\rightarrow \tilde{H}_{y}&= -\frac{1}{j\omega \mu}\frac{ \partial \tilde{E}_{x} }{ \partial z } \\
\xrightarrow{\tilde{E}_{x} = Ae^{-\gamma z} + Be^{\gamma z}} &= \frac{\gamma}{j\omega \mu}(Ae^{-\gamma z}-Be^{\gamma z}) \\
\xrightarrow{\gamma^{2} = j\omega \mu(\sigma+j\omega\varepsilon)}&=\frac{\sqrt{ j\omega \mu(\sigma+j\omega\varepsilon) }}{j\omega \mu}(Ae^{-\gamma z}-Be^{\gamma z}) \\
&=\sqrt{ \frac{\sigma + j\omega\varepsilon}{j\omega \mu} }(Ae^{-\gamma z}-Be^{\gamma z}) \\
\text{let }\eta = \sqrt{ \frac{j\omega \mu}{\sigma+j\omega\varepsilon} }\rightarrow &= \frac{1}{\eta}(A^{-\gamma z}-Be^{\gamma z})
\end{align}
$$
이때, $\eta$를 물질의 **Intrinsic impedance**(고유 임피던스)라고 정의한다. 진공의 경우, $\eta_{0} = \sqrt{ \frac{\mu_{0}}{\varepsilon_{0}} }$이다.
이 또한 Complex number이기 때문에, $\eta = \lvert \eta \rvert e^{j\tau}$라고 쓰자. 그러면 다음과 같이 작성할 수 있다.
$$
\tilde{H}_{y} = \frac{1}{\lvert \eta \rvert }e^{-j\tau}(Ae^{-\gamma z}-Be^{\gamma z})
$$
위에서 했던 식 정리와 동일하게 정리하면, 다음과 같이 정리할 수 있다.
$$
\begin{align}
H_{y}(z, t) &= \mathrm{Re}[\tilde{H}_{y}(z)e^{j\omega t}] \\
&= \mathrm{Re}\left[ \frac{\lvert A\rvert}{\lvert \eta \rvert } e^{-\alpha z}e^{j(\theta-\beta z+\omega t-\tau)} - \frac{\lvert B \rvert}{\lvert \eta \rvert } e^{\alpha z}e^{j(\phi + \beta z + \omega t-\tau)} \right] \\
&=\frac{\lvert A \rvert}{\lvert \eta \rvert} e^{-\alpha z}\cos(\omega t -\beta z+\theta-\tau) - \frac{\lvert B \rvert}{\lvert \eta \rvert } e^{\alpha z}\cos(\omega t + \beta z + \phi-\tau) \\
\Rightarrow\mathbf{H}(z, t) &= \left\{\begin{aligned}
\frac{\lvert A \rvert}{\lvert \eta \rvert } e^{-\alpha z}\cos(\omega t-\beta z+\theta-\tau)\mathbf{a}_{y} \ \ \ \ \text{for }z>0 \\
-\frac{\lvert B \rvert}{\lvert \eta \rvert } e^{\alpha z}\cos(\omega t+\beta z+\phi-\tau)\mathbf{a}_{y} \ \ \ \ \text{for }z<0
\end{aligned}\right.
\end{align}
$$
___
* Summary
$$
\begin{align}
\mathbf{E}(z, t) &= \left\{ \begin{aligned}
&\lvert A \rvert e^{-\alpha z}\cos(\omega t-\beta z+\theta)\mathbf{a}_{x} &\text{for }z>0 \\
&\lvert B \rvert e^{\alpha z}\cos(\omega t+\beta z+\phi)\mathbf{a}_{x}  &\text{for }z<0
\end{aligned}\right. \\
\mathbf{H}(z, t) &= \left\{\begin{aligned}
\frac{\lvert A \rvert}{\lvert \eta \rvert } e^{-\alpha z}\cos(\omega t-\beta z+\theta-\tau)\mathbf{a}_{y} \ \ \ \ \text{for }z>0 \\
-\frac{\lvert B \rvert}{\lvert \eta \rvert } e^{\alpha z}\cos(\omega t+\beta z+\phi-\tau)\mathbf{a}_{y} \ \ \ \ \text{for }z<0
\end{aligned}\right.
\end{align}
$$
___
여기서 $\tau, \theta, \phi, A, B$등과 같은 Unknown variables을 줄이기 위해, 다음과 같은 상황을 가정하여 문제를 해석해보자.
![[Pasted image 20241213223608.png|center|400]]
Infinite sheet을 관통하는 직사각형 모양의 Loop $abcd$를 고려하자. 이 Loop는 $ab$의 길이가 $\Delta x$이고, $da$의 길이가 $h$이다. 이 상황에서 Faraday's Law를 적용해보자. $h\to 0$으로 보낸다.
$$
\begin{align}
\oint_{abcda}\mathbf{E}\cdot d\mathbf{l} &= -\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S} \\
\int _{ab}\mathbf{E}\cdot d\mathbf{l} + \cancel{ \int _{bc}\mathbf{E}\cdot d\mathbf{l} }+\int _{cd}\mathbf{E}\cdot d\mathbf{l} +\cancel{ \int _{da}\mathbf{E}\cdot d\mathbf{l} } &=-\frac{d}{dt} \int _{S}\mathbf{B}\cdot d\mathbf{S}
\end{align}
$$
이때, $bc, da$일때의 선적분은 $d\mathbf{l}$과 $\mathbf{E}$가 서로 수직하므로 사라지고, 오른쪽 항은 $h\to 0$일때 $0$으로 간다. 또한, $ab, cd$일때의 선적분을 계산할 때 $h \to 0$이므로 $z=0$을 대입한다.
$$
\begin{align}
&\int _{ab}\mathbf{E}\cdot d\mathbf{l} +\int _{cd}\mathbf{E}\cdot d\mathbf{l} = 0 \\
&\lvert A \rvert \cos(\omega t-\beta z+\theta)\mathbf{a}_{x}\cdot (\Delta x)\mathbf{a}_{x} + \lvert B \rvert e^{\alpha z}\cos(\omega t+\beta z+\phi)\mathbf{a}_{x} \cdot (-\Delta x)\mathbf{a}_{x} \\
&= \lvert A \rvert \cos(\omega t+\theta)(\Delta x) + \lvert B \rvert \cos(\omega t+\phi) \cdot (-\Delta x) = 0 \\
&\Rightarrow \lvert A \rvert \cos(\omega t+\theta) =\lvert B \rvert \cos(\omega t+\phi) \\
&\Rightarrow \boxed{ \lvert A \rvert = \lvert B \rvert , \theta = \phi }
\end{align}
$$
이제 비슷하게 Loop $efgh$를 고려하자. 이 Loop는 $ef$의 길이가 $\Delta y$이고 $fg$의 길이가 $u$이며, $u \to 0$으로 보낸다. 이 상황에서 Ampere's Law를 적용해보자.
$$
\begin{align}
\oint _{efghe} \mathbf{H}\cdot d\mathbf{l} &= \int _{S}\mathbf{J}\cdot d\mathbf{S} + \frac{d}{dt} \int _{S}\mathbf{D}\cdot d\mathbf{S} \\
\int _{ef}\mathbf{H}\cdot d\mathbf{l}+\cancel{ \int _{fg}\mathbf{H}\cdot d\mathbf{l} }+\int _{gh}\mathbf{H}\cdot d\mathbf{l}+\cancel{ \int _{he}\mathbf{H}\cdot d\mathbf{l} }&= \int _{S}\mathbf{J}\cdot d\mathbf{S}+\frac{d}{dt} \int _{S}\mathbf{D}\cdot d\mathbf{S}  
\end{align}
$$
이때, $fg, he$일때의 선적분은 $d\mathbf{l}$과 $\mathbf{H}$가 서로 수직하므로 사라진다. $u\to 0$로 가므로 면적 $S$를 통과하는 Electric flux density $\mathbf{D}$는 존재하지 않는다. 또한, $ef, gh$일때의 선적분을 계산할 때 $u \to 0$이므로 $z=0$을 대입한다. 또한, Infinite sheet에 $J_{S_{0}}\cos \omega t$만큼의 Current density가 흐르므로 $u\to 0$으로 가도 Loop의 폭($ef$의 길이 = $\Delta y$)만큼의 전류는 항상 흐르고 있다. 따라서,
$$
\begin{align}
&\int _{ef}\mathbf{H}\cdot d\mathbf{l} + \int _{gh}\mathbf{H}\cdot d\mathbf{l} = \int _{S}\mathbf{J}\cdot d\mathbf{S}+\cancel{ \frac{d}{dt} \int _{S}\mathbf{D}\cdot d\mathbf{S}   }\\
=&\frac{\lvert A \rvert}{\lvert \eta \rvert } e^{-\alpha z}\cos(\omega t-\beta z+\theta-\tau)\mathbf{a}_{y}\cdot(\Delta y)\mathbf{a}_{y} + \frac{\lvert B \rvert}{\lvert \eta \rvert } e^{\alpha z}\cos(\omega t+\beta z+\phi-\tau)\mathbf{a}_{y}\cdot(\Delta y)\mathbf{a}_{y} \\
=&\frac{\lvert A \rvert}{\lvert \eta \rvert } \cos(\omega t+\theta-\tau)\cdot(\Delta y) + \frac{\lvert B \rvert}{\lvert \eta \rvert } \cos(\omega t+\phi-\tau)\cdot(\Delta y) \\
=&\frac{\lvert A \rvert}{\lvert \eta \rvert } \cos(\omega t+\theta-\tau)\cdot(\Delta y) + \frac{\lvert A \rvert}{\lvert \eta \rvert } \cos(\omega t+\theta-\tau)\cdot(\Delta y) \\
 =& J_{S_{0}}\cos \omega t \Delta y  \\
\Rightarrow& \frac{2\lvert A \rvert}{\lvert \eta \rvert } \cos(\omega t+\theta-\tau) = J_{S_{0}}\cos \omega t \\
\Rightarrow& \boxed{ \lvert A \rvert = \frac{\lvert \eta \rvert J_{S_{0}}}{2}, \theta=\tau }
\end{align}
$$
이를 통해 $\mathbf{E}, \mathbf{H}$를 다시 작성하면 다음과 같다.
___
* Summary
$$
\begin{align}
\mathbf{E}(z, t) &= \left\{ \begin{aligned}
&\frac{\lvert \eta \rvert J_{S_{0}}}{2} e^{-\alpha z}\cos(\omega t-\beta z+\tau)\mathbf{a}_{x} &\text{for }z>0 \\
&\frac{\lvert \eta \rvert J_{S_{0}}}{2} e^{\alpha z}\cos(\omega t+\beta z+\tau)\mathbf{a}_{x}  &\text{for }z<0
\end{aligned}\right. \\
\mathbf{H}(z, t) &= \left\{\begin{aligned}
\frac{J_{S_{0}}}{2} e^{-\alpha z}\cos(\omega t-\beta z)\mathbf{a}_{y} \ \ \ \ \text{for }z>0 \\
-\frac{J_{S_{0}}}{2}  e^{\alpha z}\cos(\omega t+\beta z)\mathbf{a}_{y} \ \ \ \ \text{for }z<0
\end{aligned}\right.
\end{align}
$$
___
