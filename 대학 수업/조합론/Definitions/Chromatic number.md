___

**DEF**) The smallest number of colors need to color a graph $G$ is called the **chromatic number of $G$**.
Denoted by $\chi (G)$.
Recall [[Coloring]].

___

**Example**

* Consider the complete graph $K_n$ , $\chi(K_n)$.
![[Pasted image 20231010034109.png]]
Since each vertex is adjacent to all other $n-1$ vertices, $\chi (K_n) = n$.

* Consider the cycle graph, or connected $2$-regular graph, $C_n$.
![[Pasted image 20231010040404.png]]
If $n$ is even, $\chi (C_n) = 2$, if $n$ is odd, $\chi (C_n) = 3$.

___

![[Pasted image 20231010040846.png]]
Chromatic number를 정하는 데에 있어서 가장 최악의 경우는 인접한 모든 vertices들의 색깔이 전부 다 다른 경우이므로, $\chi (G) \leq \Delta + 1$이 성립한다.

___

