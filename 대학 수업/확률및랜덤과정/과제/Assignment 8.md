###### 1. Consider the Markov chain shown below, where $0 < p < 1$ and the labels on the arrows indicate transition probabilites.
![[Pasted image 20241207205347.png|center|200]]
(a) Find the transition matrix $Q$.
(b) Find the stationary distribution.
(c) What happens to $Q^{n}$ as $n \to \infty$?

Sol)
(a)
We have two state, $\{1, 2\}$. Transition probability from state $1$ to state $1$ is $p$, from state $1$ to state $2$ is $1-p$. Similiarly, from state $2$ to state $1$ is $1-p$ and from state $2$ to state $2$ is $p$. Therefore,
$$
Q = \begin{bmatrix}
p & 1-p \\
1-p & p
\end{bmatrix}
$$
(b)
Recall the definition of the stationary distribution.
Let $\mathbf{s} = (s_{1}, s_{2})$ and $s_{1} + s_{2} = 1$ with $\mathbf{s}Q = \mathbf{s}$.
Hence,
$$
\begin{align}
\mathbf{s}Q &= (s_{1},s_{2})\begin{bmatrix}
p & 1-p \\
1-p & p
\end{bmatrix} \\
&=(s_{1}p+s_{2}-s_{2}p, s_{1}-s_{1}p + s_{2}p) \\
&=(s_{1}p+1-s_{1}-p+s_{1}p, 1-s_{2} -p+s_{2}p+s_{2}p) \\
&=(p(2s_{1}-1)+(1-s_{1}), p(2s_{2}-1)+(1-s_{2})) \\
&=(s_{1}, s_{2})=\left( \frac{1}{2}, \frac{1}{2} \right)
\end{align}
$$
(c)
Note that $0 < p < 1$. By convergence to stationary distribution, $Q^{n}$ goes to
$$
\begin{bmatrix}
\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2}
\end{bmatrix}
$$
when $n$ goes to infinity.

###### 2. Consider the Markov chain shown below, with state space $\{1,2,3,4\}$ and the labels on the arrows indicate transition probabilities.
![[Pasted image 20241208004509.png|center|200]]
(a) Find the transition matrix $Q$.
(b) Which state (if any) are recurrent? Which states (if any) are transient?
(c) Find two different stationary distributions for the chain.

Sol)
(a)
$$
Q = \begin{bmatrix}
0.5 & 0.5 & 0 & 0 \\
0.25 & 0.75 & 0 & 0 \\
0 & 0 & 0.25 & 0.75 \\
0 & 0 & 0.75 & 0.25
\end{bmatrix}
$$
(b)
Note that state $1$ and state $2$ forms closed communicating class and state $3$ and state $4$ forms closed communicating class. Hence, all states are recurrent, no states are transient.
(c)
Let $\mathbf{s} = \begin{bmatrix}s_{1}&s_{2}&s_{3}&s_{4}\end{bmatrix}$ where $\sum s_{i} = 1$.
$$
\begin{align}
\mathbf{s}Q &= \left\{
\begin{aligned}
0.5s_{1} + 0.25s_{2} &= s_{1} \\
0.5s_{1} + 0.75s_{2} &= s_{2} \\
0.25s_{3}+0.75s_{4} &= s_{3} \\
0.75s_{3}+0.25s_{4} &= s_{4}
\end{aligned} \right. \\ \\
&= \left\{\begin{aligned}
s_{1}&=0.5s_{2} \\ 
s_{3}&=s_{4}
\end{aligned} \right. \\
&\Rightarrow \mathbf{s} = \begin{bmatrix}
0.5s_{2} & s_{2} & s_{3} & s_{3}
\end{bmatrix} \\
&\rightarrow 1.5s_{2} + 2s_{3} = 1 \\
&\rightarrow s_{2} = \frac{2}{3}-\frac{4}{3}s_{3} \\
&\Rightarrow \mathbf{s} = \begin{bmatrix}
\frac{1}{3}-\frac{2}{3}s_{3} & \frac{2}{3}-\frac{4}{3}s_{3}  & s_{3} & s_{3}
\end{bmatrix} \text{ where }0\leq s_{3} \leq 0.5
\end{align}
$$
Note that this Markov chain is reducible, so stationary distribution $\mathbf{s}$ is not unique.
If we take $s_{3}$ as $0$, $\mathbf{s} = \begin{bmatrix} \frac{1}{3} & \frac{2}{3} & 0 & 0\end{bmatrix}$. If we take $s_{3}$ as $\frac{1}{2}$, $\mathbf{s} = \begin{bmatrix} 0 & 0 & \frac{1}{2} & \frac{1}{2}\end{bmatrix}$.

###### 3. A Markov chain $X_{0}, X_{1}, \dots$ with state space $\{-3, -2, -1, 0, 1, 2, 3 \}$ proceeds as follows. The chain starts at $X_{0} = 0$. If $X_{n}$ is not an end point ($-3$ or $3$), then $X_{n+1}$ is $X_{n-1}$ or $X_{n+1}$, each with probability $1/2$. Otherwise, the chain gets reflected off the endpoint, i.e., from $3$ it always goes to $2$ and from $-3$ it always goes to $-2$. A diagram of the chain is shown below.
![[Pasted image 20241208023742.png|center|400]]
(a) Is $\lvert X_{0} \rvert, \lvert X_{1} \rvert, \lvert X_{2} \rvert, \dots$ also a Markov chain?
(b) Let $\text{sgn}$ be the sign function: $\text{sgn}(x) = 1$ if $x > 0$, $\text{sgn}(x) = -1$ if $x < 0$, and $\text{sgn}(0) = 0$. Is $\text{sgn}(X_{0}), \text{sgn}(X_{1}), \text{sgn}(X_{2}), \dots$ a Markov chain?
(c) Find the stationary distribution of the chain $X_{0}, X_{1}, X_{2}, \dots$.

Sol)
(a)
Let $Y_{n} = \lvert X_{n} \rvert$. We have to check $Y_{n}$ has Markov property, which means $Y_{n+1}$ depends only on $Y_{n}$. Note that the state space for $Y_{n} = \{0, 1, 2, 3\}$.
If $Y_{n} = 0$, then $X_{n} = 0$. $X_{n+1}$ must be $\pm 1$ with equal probability $\frac{1}{2}$. Regardless of whether we go, $\lvert X_{n+1} \rvert = Y_{n} = 1$. It means from $Y_{n} = 0$, we have $Y_{n+1} = 1$ with probability $1$. This transition depends only on $Y_{n}$.
If $Y_{n} = 1$, then $X_{n} = 1 \text{ or } -1$. If $X_{n} = 1$, $X_{n+1} = 0 \text{ or }2$ with equal probability $\frac{1}{2}$. If $X_{n} = -1$, $X_{n+1} = 0 \text{ or }-2$ with equal probability $\frac{1}{2}$. No matter what $X_{n}$ is, $Y_{n+1} = \lvert X_{n+1} \rvert = 0 \text{ or }2$ with equal probability $\frac{1}{2}$. This transition depends only on $Y_{n}$.
Similiar with $Y_{n}=2$ and $Y_{n} = 3$. So, YES.
(b)
Let $Z_{n} = \text{sgn}(X_{n})$. We have to check $Z_{n}$ has Markov property, which means $Z_{n+1}$ depends only on $Z_{n}$. Note that the state space for $Z_{n} = \{-1, 0, 1\}$.
If $Z_{n} = 0$, then $X_{n} = 0$. $X_{n+1}$ must be $\pm 1$ with equal probability $\frac{1}{2}$. Then, $Z_{n+1} = \pm 1$ with equal probability $\frac{1}{2}$. This transition depends only on $Z_{n}$.
If $Z_{n} = 1$, then $X_{n} = 1, 2, 3$. If $X_{n} = 1$, $X_{n+1} = 0 \text{ or }2 \rightarrow Z_{n+1} = 0 \text{ or }1$ with equal probability $\frac{1}{2}$. If $X_{n} = 2$, $X_{n+1} = 1 \text{ or }3\rightarrow Z_{n+1} = 1$ with probability $1$. Here, Markov property fails because $Z_{n+1}$ depends not only $Z_{n}$, but also $X_{n}$. It means we don't know transition probability of $Z_{n}$ without knowing actual value of $X_{n}.$ So, No.
(c)
Consider transition matrix $Q$.
$$
Q = \begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 & 0 \\
\frac{1}{2} & 0 & \frac{1}{2} & 0 & 0 & 0 & 0 \\
0 & \frac{1}{2} & 0 & \frac{1}{2} & 0 & 0 & 0 \\
0 & 0 & \frac{1}{2} & 0 & \frac{1}{2} & 0 & 0 \\
0 & 0 & 0 & \frac{1}{2} & 0 & \frac{1}{2} & 0 \\
0 & 0 & 0 & 0 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & 0 & 0 & 0 & 0 & 1 & 0
\end{bmatrix}
$$
Let $\mathbf{s} = \begin{bmatrix}s_{1}&\cdots & s_{7}\end{bmatrix}$ where $\sum s_{i} = 1$.
Then,
$$
\begin{align}
&s_{1} = \frac{1}{2}s_{2}, s_{2} = s_{3} = s_{4} = s_{5} = s_{6}, s_{7} = \frac{1}{2}s_{6} \\
\rightarrow & \mathbf{s} = \begin{bmatrix} s_{1} & 2s_{1} & 2s_{1} & \cdots &2s_{1}&s_{1}\end{bmatrix} \\
\rightarrow & \mathbf{s} = \begin{bmatrix} \frac{1}{12} & \frac{1}{6}  & \frac{1}{6}  & \frac{1}{6} & \frac{1}{6} & \frac{1}{6} & \frac{1}{12}\end{bmatrix}
\end{align}
$$

###### 4. Find the stationary distribution of the Markov chain shown below, without using matrices. The number above each arrow is the corresponding transition probability.
![[Pasted image 20241208221618.png|center|500]]

Sol)
We use reversibility.
$$
\begin{align}
s_{1}&=\frac{1}{2}s_{2}  \\
\frac{1}{2}s_{2}&=\frac{1}{4}s_{3} \\
\frac{1}{3}s_{3}&=\frac{1}{6}s_{4} \\
\frac{1}{4}s_{4}&=\frac{1}{8}s_{5} \\
\rightarrow \mathbf{s} &= \begin{bmatrix}
s_{1} & 2s_{1} & 4s_{1} & 8s_{1} & 16s_{1}
\end{bmatrix} \\
\rightarrow \mathbf{s} &= \begin{bmatrix}
\frac{1}{31} & \frac{2}{31} & \frac{4}{31} & \frac{8}{31} & \frac{16}{31}
\end{bmatrix}
\end{align}
$$
If we take two state $i$ and $j$ which is not adjacent, such as state $1$ and state $3$, there is no transition between two state, so, detailed balanced condition must satiesfy.
Since this Markov chain is reversible with $\mathbf{s}$, $\mathbf{s}$ is a stationary distribution of the chain.

###### 5. Let $\{X_{n}\}$ be a Markov chain on states $\{0,1,2\}$ with transition matrix $$\begin{pmatrix}0.8 & 0.2 & 0 \\0 & 0.8 & 0.2 \\0 & 0 & 1\end{pmatrix}$$ The chain starts at $X_{0}=0$. Let $T$ be the time it takes to reach state $2$: $$T=\min\{n: X_{n}=2\}$$ Find $E(T)$ and $Var(T)$.

Sol)
Here is interpretation of the chain. Starting from state 0, it stays with probability 0.8, moves to state 1 with probability 0.2. From state 1, it stays with probability 0.8, moves to state 2 with probability 0.2. If we reach state 2, we always stay in state 2.

Let $E_{0} = E(T|X_{0}=0), E_{1} = E(T|X_{0}=1)$.

We compute $E_{1}$ first.
With probability 0.2, it takes 1 step to reach state 2. With probability 0.8, it stays (which means it spends 1 step) and try again.
Hence, $E_{1} = 0.2\cdot 1 + 0.8\cdot (1+E_{1}) = 1+0.8E_{1} \Rightarrow E_{1} = 5$.

Second, we compute $E_{0}$.
With probability 0.2, it takes 1 step and move state 1. From state 1 to reach state 2, we have to take $E_{1}$ times. With probability 0.8, it stays (which means it spends 1 step) and try again.
Hence, $E_{0}=0.2(1+E_{1})+0.8(1+E_{0})=2+0.8E_{0}\Rightarrow E_{0}=10$.
Hence, $\boxed{ E(T) = 10 }$.

To compute variance, we need to find $E(T^{2})$.

Let $M_{0} = E(T^{2}|X_{0}=0), M_{1} = E(T^{2}|X_{0}=1)$.

We compute $M_{1}$ first.
With probability 0.2, it takes 1 step to reach state 2. With probability 0.8, it stays (which means it spends 1 step) and try again.
Hence,
$$
\begin{align}
M_{1} &= E(T^{2}|X_{0}=1) \\
&= 0.2\cdot 1\cdot 1 + 0.8\cdot E((1+T)^{2}|X_{0} = 1) \\
&= 0.2 + 0.8(1+2E(T|X_{0}=1) + E(T^{2}|X_{0}=1)) \\
&= 1 + 8+0.8M_{1} \\
\Rightarrow M_{1} &= 45
\end{align}
$$

We compute $M_{0}$ second.
With probability 0.2, it takes 1 step and move state 1. With probability 0.8, it stays (which means it spends 1 step) and try again.
Hence,
$$
\begin{align}
M_{0} &= E(T^{2}|X_{0}=0) \\
&= 0.2E((1+T)^{2}|X_{0} = 1) +0.8E((1+T)^{2}|X_{0}=0) \\
&= 0.2+0.4E_{1}+0.2M_{1} + 0.8+1.6E_{0}+0.8M_{0} \\
0.2M_{0}&=1+2+9+16 \\
M_{0} &= 140
\end{align}
$$

Therefore,
$$
Var(T) = M_{0} - E_{0}^{2} = \boxed{ 40 }
$$

###### 6. Let us consider random walk on a weighted undirected network. Suppose that an undirected network is given, where each edge $(i, j)$ has a nonnegative weight $w_{ij}$ assigned to it (we allow $i = j$ as a possibility). We assume that $w_{ij} = w_{ji}$ since the edge from $i$ to $j$ is considered the same as the edge from $j$ to $i$. When $(i, j)$ is not an edge, we set $w_{ij}=0$. When at node $i$, the next step is determined by choosing an edge attached to $i$ with probabilites proportional to the weights.

(a) Let $v_{i}=\sum_{j}w_{ij}$ for all nodes $i$. Show that the stationary distribution of node $i$ is proportional to $v_{i}$.
(b) Show that every reversible Markov chain can be represented as a random walk on a weighted undirected network.

Sol)
(a)
Note that when at node $i$, the next step is determined by choosing an edge attached to $i$ with probabilites proportional to the weights. It means the definition of transition probability $P(i\to j)$ is
$$
P(i\to j) = \frac{w_{ij}}{\text{Total sum of weight which edge attached to $i$}}=\frac{w_{ij}}{\sum_{j} w_{ij}}
$$
Note that we defined $\sum_{j}w_{ij}$ as $v_{i}$. We can rewrite it.
$$
P(i\to j) = \frac{w_{ij}}{v_{i}}
$$
Let the stationary distribution $\mathbf{s} = \begin{bmatrix}s_{1}& s_{2}&\cdots & s_{n}\end{bmatrix}$.
By the definition of stationary distribution, $\mathbf{s}$ must satiesfy below condition.
$$
s_{i} = \sum_{j=1}^{n}s_{j}P(j\to i)
$$
Note that $P(i\to j) = w_{ij} / v_{i}$, so, $P(j\to i) = w_{ji} / v_{j}$
$$
s_{i} = \sum_{j} \frac{s_{j}w_{ji}}{v_{j}} 
$$
Let $s_{j} = v_{j} / \sum v$. I'll claim that this true.
$$
\begin{align}
s_{i} &= \sum_{j} \frac{v_{j}}{\sum v}\cdot \frac{w_{ji}}{v_{j}} \\
&=\frac{1}{\sum v}\sum_{j}w_{ij} \\
&= \frac{v_{i}}{\sum v}
\end{align}
$$
So, it holds.
Therefore, $s_{i}$ is proportional to $v_{i}$, which is total weight sum of weight which edge attached to $i$.

(b)
Remind the definition of reversible chain, which means there is a vector $\mathbf{s}$ for $Q = (q_{ij})$, for every $i$ and $j$, $s_{i}q_{ij} = s_{j}q_{ji}$.
Define weights on edges by
$$
w_{ij} = s_{i}q_{ij} = s_{j}q_{ji} = w_{ji}
$$
, which ensures graph is undirected. Note that if $q_{ij} = 0$, then $w_{ij} =0$.
Then, consider transition probability $P(i\to j)$ as we did above.
$$
P(i\to j) = \frac{w_{ij}}{v_{i}} = \frac{w_{ij}}{\sum_{k}w_{ik}} = \frac{s_{i}q_{ij}}{s_{i}\sum_{k} q_{ik}} = \frac{q_{ij}}{\sum_{k}q_{ik}} = q_{ij}
$$
It means, the original transition probability $q_{ij}$ of reversible Markov chain is same as the transition probability $P(i\to j)$ of constructed weighted undirected graph.
This shows that every reversible Markov chain can be represented in this manner.

###### 7. There are two urns with a total of $2N$ distinguishable balls. Initially, the first urn has $N$ white balls and the second urn has $N$ black balls. At each stage, we pick a ball at random from each urn and interchange them. Let $X_{n}$ be the number of black balls in the first urn at time $n$. This is a Markov chain on the state space $\{0, 1, \dots, N\}$.

(a) Give the transition probabilities of the chain.
(b) Show that $(s_{0}, s_{1}, \dots, s_{N})$ where $$s_{i}= \frac{{N \choose i}{N \choose N-i}}{{2N \choose N}}$$ is the stationary distribution, by verifying the reversibility condition.

Sol)
(a)
Note that the transition $i \to j$ where $\lvert i -j \rvert > 1$ is impossible, since we can add at most $1$ black ball in a urn in one swap.
First, consider the transition probability $P(0\to 0)$.
It is impossible, since if there is no black balls in first urn, then it means all black balls in second urn. Hence, we have to change a white ball in first urn and a black ball in second urn. So, $P(0 \to 1) = 1$. Similarly, $P(N \to N-1) = 1$ and $P(N \to N) = 0$
Let $i \neq 0, N$.
Consider the transition probability $P(i \to i)$.
To maintain the number of black balls in first urn, we have to choose same color balls in both urns. Note that state $i$ means the number of black balls in first urn.
Therefore,
$$
P(i\to i) = \frac{i}{N}\cdot \frac{N-i}{N} + \frac{N-i}{N}\cdot \frac{i}{N} = \frac{2i(N-i)}{N^{2}}
$$
Consider the transition probability $P(i \to i+1)$.
To increase the number of black balls in first urn, we have to choose white ball in first urn, black ball in second urn.
Therefore,
$$
P(i\to i+1) = \frac{N-i}{N}\cdot \frac{N-i}{N} = \frac{(N-i)^{2}}{N^{2}}
$$
Consider the transition probability $P(i\to i-1)$.
To decrease the number of black balls in first urn, we have to choose black ball in first urn, white ball in second urn.
Therefore,
$$
P(i \to i-1) = \frac{i}{N}\cdot \frac{i}{N} = \frac{i^{2}}{N^{2}}
$$

(b)
Note that $\sum s_{i} = 1$.
We have to check whether detailed balanced condition holds.
$$
\begin{align}
s_{i}P(i \to i+1) &= s_{i+1}P(i+1 \to i) \\
s_{i}P(i\to i-1) &=s_{i-1}P(i-1\to i)
\end{align}
$$
$$
\begin{align}
s_{i}P(i \to i+1) &= \frac{{N \choose i}{N \choose N-i}}{{2N \choose N}}\frac{(N-i)^{2}}{N^{2}} \\ 
&= \frac{1}{{2N \choose N}N^{2}}\cdot \frac{N!N!}{i!i!(N-i-1)!(N-i-1)!} \\
&= \frac{1}{{2N \choose N}N^{2}}\cdot \frac{(i+1)^{2}N!N!}{(i+1)!(i+1)!(N-i-1)!(N-i-1)!} \\
&= \frac{{N \choose i+1}{N \choose N-i-1}}{{2N \choose N}}\frac{(i+1)^{2}}{N^{2}}  \\
&= s_{i+1}P(i+1 \to i)
\end{align}
$$

$$
\begin{align}
s_{i}P(i\to i-1) &= \frac{{N \choose i}{N \choose N-i}}{{2N \choose N}}\frac{i^{2}}{N^{2}} \\
&= \frac{1}{{2N \choose N}N^{2}}\cdot \frac{N!N!}{(i-1)!(i-1)!(N-i)!(N-i)!} \\
&= \frac{1}{{2N \choose N}N^{2}}\cdot \frac{N!N!(N-i+1)^{2}}{(i-1)!(i-1)!(N-i+1)!(N-i+1)!} \\
&= \frac{{N \choose i-1}{N \choose N-i+1}}{{2N \choose N}}\frac{(N-i+1)^{2}}{N^{2}}
\\&= s_{i-1}P(i-1\to i) 
\end{align}
$$
