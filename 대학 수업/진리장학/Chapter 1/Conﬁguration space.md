Reference : https://en.wikipedia.org/wiki/Configuration_space_(physics)
**Definition)** In classical mechanics, the parameters that define the configuration of a system are called **generalized coordinates**, and the space defined by these coordinates is called the **configuration space** of the physical system.
It is often the case that these parameters satisfy mathematical constraints, such that the **set of actual configurations of the system is a manifold** in the space of generalized coordinates. This [manifold](https://en.wikipedia.org/wiki/Manifold "Manifold") is called the **configuration manifold** of the system.

### Examples
#### 1. a particle in 3D space
일반적으로 Euclidean 3-space에서 움직이는 Single particle을 생각해보자.
이건 $q = (x, y, z)$라는 벡터로 표현 가능하다.
따라서, 이 경우 Configuration space $Q = \mathbb{R}^{3}$가 된다.
Single particle $q$가 제약조건이 걸려서 하나의 특정한 Manifold를 형성할 수도 있다.
예를 들어, $q$가 rigid [[Linkage]]에 부착되어있고, Linkage는 원점에 고정되있고 자유롭게 움직일 수 있으면, $q$의 궤적은 구면이 될 것이다.
따라서, 이때의 configuration manifold는 $Q = S^{2}$이다.
$N$개의 disconnected, non-interating point particle의 경우, Configuration space는 $\mathbb{R}^{3N}$이 된다.
근데 일반적으로는 이렇게 non-interacting한 경우는 별로 관심이 없고, 상호작용하는 경우에 관심이 더 많다.
예를 들자면, 기어, 도르래, rolling ball등 특정 위치가 미끄러지지 않고 이동되도록 제한되는 경우를 생각해보자.
이 경우 $\mathbb{R}^{3N}$이 Configuration space가 되지 않고, 여기의 subspace(submanifold)가 Configuration space가 된다.
#### 2. rigid body in 3D space



#### 3. robotic arm
