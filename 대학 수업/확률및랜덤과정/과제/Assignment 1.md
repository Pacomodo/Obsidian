###### 1. According to the CDC (Centers for Disease Control and Prevention), men who smoke are 20 times more likely to develop lung cancer than men who don’t smoke. Also according to the CDC, 20% of men in the U.S. smoke. What is the probability that a man in the U.S. is a smoker, given that he develops lung cancer?

Sol)
Let $A$ be the event that a man in U.S. smoke.
Let $B$ be the event that a man in U.S. has lung cancer.
We want to find that $P(A|B)$.
We know that $P(B|A) : P(B|A^{c}) = 20:1$ and $P(A) = 0.2$.
$$
\begin{align}
P(A|B) &= \frac{P(A\cap B)}{P(B)} \\
\xrightarrow{\text{by LOTP}}&= \frac{P(A\cap B)}{P(B|A)P(A)+P(B|A^{c})P(A^{c})} \\
\xrightarrow{\text{by Bayes Rule}} &= \frac{P(B|A)P(A)}{P(B|A)P(A)+P(B|A^{c})P(A^{c})} \\
&= \frac{20P(B|A^{c})\cdot 0.2}{20P(B|A^{c})\cdot 0.2+P(B|A^{c})\cdot 0.8} \\
&=\frac{4}{4.8}=\frac{5}{6} 
\end{align}
$$

___
###### 2. Fred is answering a multiple-choice problem on an exam, and has to choose one of $n$ options (exactly one of which is correct). Let $K$ be the event that he knows the answer, and $R$ be the event that he gets the problem right (either through knowledge or through luck). Suppose that if he knows the right answer he will deﬁnitely get the problem right, but if he does not know then he will guess completely randomly. Let $P (K) = p$.

1) Find $P(K|R)$ (in terms of $p$ and $n$).
2) Show that $P(K|R) \geq p$. When (if ever) does $P (K|R)$ equal $p$?

Sol)
1)
Note that when he knows the answer, he will always get the problem right.
So, $P(R|K) = 1$. If he does not know, then he will choose completely randomly, so, $P(R|K^{c}) = \frac{1}{n}$.
$$
\begin{align}
P(K|R) &= \frac{P(R|K)P(K)}{P(R|K)P(K)+P(R|K^{c})P(K^{c})} \\
&= \frac{1\cdot p}{1\cdot p+\frac{1}{n}(1-p)} = \frac{np}{np-p+1}
\end{align}
$$
2)
Note that $0 \leq P(K)\leq 1, n \geq 1$.
It is enough to show that $\frac{np}{np-p+1} \geq p$.
$$
\begin{align} \\
& n \geq 1 \\
\xrightarrow{p^{2}-p\leq 0} & p^{2}-p\geq n(p^{2}-p) \\ 
\rightarrow & np \geq np^{2}-p^{2}+p \\
\rightarrow & \frac{np}{np-p+1} \geq p
\end{align}
$$
If $p = 0$, it is obvious that $P(K|R) = 0 = p$.
If $p=1$, $P(K|R) = \frac{n}{n} = 1 = p$.
When $n = 1$, $P(K|R) =  \frac{p}{p-p+1} = p$.
Hence, equality holds if and only if when $p = 0, p = 1$ or $n=1$.
___
###### 3. A hat contains 100 coins, where 99 are fair but one is double-headed (always landing Heads). A coin is chosen uniformly at random. The chosen coin is ﬂipped 7 times, and it lands Heads all 7 times. Given this information, what is the probability that the chosen coin is double-headed?

Sol)
Let $D$ be the event that choose double-headed coin.
Let $H$ be the event that a chosen coin lands heads all 7 times.
We want to find $P(D|H)$.
Note that $P(D) = 0.01$, $P(H|D) = 1$, $P(H|D^{c}) = \frac{1}{2^{7}}$.
$$
\begin{align}
P(D|H) &= \frac{P(H|D)P(D)}{P(H|D)P(D)+P(H|D^{c})P(D^{c})} \\
&= \frac{0.01}{0.01+\frac{1}{2^{7}}\cdot 0.99} \\
&= \frac{1}{1+\frac{99}{2^{7}}} =\frac{2^{7}}{2^{7}+99}=\frac{128}{227}
\end{align}
$$
___
###### 4. A hat contains 100 coins, where at least 99 are fair, but there may be one that is doubleheaded (always landing Heads); if there is no such coin, then all 100 are fair. Let $D$ be the event that there is such a coin, and suppose that $P(D) = 1/2$. A coin is chosen uniformly at random. The chosen coin is ﬂipped 7 times, and it lands Heads all 7 times.

(a) Given this information, what is the probability that one of the coins is doubleheaded?
(b) Given this information, what is the probability that the chosen coin is doubleheaded?

Sol)
(a)
Let $D$ be the event that there is doubleheaded coin.
Let $H$ be the event that a chosen coin lands heads all 7 times.
Let $B$ be the event that we choose doubleheaded coin.
We want to find $P(D|H)$.
Note that $P(D) = \frac{1}{2}$.
$$
\begin{align}
P(D|H) &= \frac{P(H|D)P(D)}{P(H|D)P(D)+P(H|D^{c})P(D^{c})} \\
&= \frac{P(H|D)\cdot\frac{1}{2}}{P(H|D)\cdot\frac{1}{2}+P(H|D^{c})\cdot \frac{1}{2}}
\end{align}
$$
By LOTP with extra conditioning,
$$
\begin{align}
P(H|D) &= P(H|B,D)P(B|D) + P(H|B^{c},D)P(B^{c}|D) \\
&= 1\cdot0.01 + \frac{1}{2^7}\cdot0.99  \\
P(H|D^{c}) &= P(H|B,D^{c})P(B|D^{c}) + P(H|B^{c},D^{c})P(B^{c}|D^{c}) \\
&= \frac{1}{2^7}\\
\end{align}
$$
So, 
$$
\begin{align}
P(D|H) &= \frac{1\cdot0.01 + \frac{1}{2^7}\cdot0.99}{1\cdot0.01 + \frac{1}{2^7}\cdot0.99 + \frac{1}{2^{7}}}=\frac{2^{7}+99}{2^{7}+99+100}=\frac{227}{327}
\end{align}
$$
(b)
We want to find $P(B|H)$. If we pick fair coin, the probability of lands head all 7 times is $\frac{1}{2^{7}}$.
$$
\begin{align}
P(B|H) &= \frac{P(H|B)P(B)}{P(H|B)P(B)+P(H|B^{c})P(B^{c})} \\
&= \frac{1\cdot P(B)}{1\cdot P(B)+\frac{1}{2^{7}}\cdot P(B)}
\end{align}
$$
By LOTP,
$$
\begin{align}
P(B) = P(B|D)P(D)+P(B|D^{c})P(D^{c}) = \frac{1}{200} \\
P(B^{c}) = P(B^{c}|D)P(D)+P(B^{c}|D^{c})P(D^{c}) = 0.99\cdot\frac{1}{2}+1\cdot \frac{1}{2} = \frac{199}{200} \\
\end{align}
$$
So,
$$
P(B|H) = \frac{2^{7}}{2^{7}+199}=\frac{128}{327}
$$
___
###### 5. A bag contains one marble which is either green or blue, with equal probabilities. A green marble is put in the bag (so there are 2 marbles now), and then a random marble is taken out. The marble taken out is green. What is the probability that the remaining marble is also green?

Sol)
Let $G$ be the event that a bag contains green marble initially.
Let $M_{1}$ be the event that first marble is green.
Let $M_{2}$ be the event that second marble is green.
We want to find $P(M_{2}|M_{1})$.
$$
P(M_{2}|M_{1}) = \frac{P(M_{1}\cap M_{2})}{P(M_{1})}
$$
By LOTP,
$$
\begin{align}
P(M_{1}) &= P(M_{1}|G)P(G)+P(M_{1}|G^{c})P(G^{c}) \\
&= \frac{1}{2}+\frac{1}{2}\cdot\frac{1}{2}=\frac{3}{4}
\end{align}
$$
By LOTP,
$$
\begin{align}
P(M_{1},M_{2}) &= P(M_{1}, M_{2}|G)P(G)+P(M_{1}, M_{2}|G^{c})P(G^{c}) \\
&=\frac{1}{2} + 0 = \frac{1}{2}
\end{align}
$$
Hence, $P(M_{2}|M_{1}) = \frac{2}{3}$.
___
###### 6. A crime is committed by one of two suspects, A and B. Initially, there is equal evidence against both of them. In further investigation at the crime scene, it is found that the guilty party had a blood type found in 10% of the population. Suspect A does match this blood type, whereas the blood type of Suspect B is unknown.

(a) Given this new information, what is the probability that A is the guilty party?
(b) Given this new information, what is the probability that B’s blood type matches that found at the crime scene?

Sol)
(a)
Let $R$ is guilty party blood type.
Let $E$ is the event that the guilty party has blood type $R$ and A has same blood type.
Let $G_{A}$ is the event that A is guilty.
Let $G_{B}$ is the event that B is guilty.
First, $P(G_{A}) = P(G_{B}) = \frac{1}{2}$.

We want to find $P(G_{A}|E)$.
$$
\begin{align} 
P(G_{A}|E) &= \frac{P(E|G_{A})\cdot P(G_{A})}{P(E|G_{A})\cdot P(G_{A}) + P(E|G_{B})\cdot P(G_{B})} \\
&=\frac{P(E|G_{A})}{P(E|G_{A})+P(E|G_{B})} = \frac{1}{1.1}=\frac{10}{11}
\end{align}
$$
(b)
Let $R_{B}$​ is the event that B has blood type $R$.
We want to find $P(R_{B}|E)$.
By LOTP,
$$
\begin{align}
P(R_{B}|E) &= P(R_{B}|G_{A},E)P(G_{A}|E) + P(R_{B}|G_{B},E)P(G_{B}|E) \\
&= 0.1\cdot \frac{10}{11} +1\cdot \frac{1}{11} = \frac{2}{11}
\end{align}
$$
___
###### 7. A family has 3 children, named A, B, and C. Any of the 3 children is equally likely to be older than other one.

(a) Find the probability that A is older than B, given that A is older than C.
(b) Determine whether the event “A is older than B” is independent of the event “A is older than C”.

Sol)
(a)
Consider all cases, $(A,B,C), (A, C, B), (B, A, C), (B, C, A), (C, A, B), (C, B, A)$.
Let $O_{AB}$ be the event that A is older than B.
Let $O_{AC}$ be the event that A is older than C.
Then, $P(O_{AB}|O_{AC}) = \frac{2}{3}$.

(b)
$P(O_{AB}) = \frac{1}{2}, P(O_{AC}) = \frac{1}{2}$, but, $P(O_{AB}|O_{AC})\neq P(O_{AB})$.
Therefore, these two events are dependent.
___
###### 8. You are going to play 2 games of chess with an opponent whom you have never played against before. Your opponent is equally likely to be a beginner, intermediate, or a master. Depending on which, your chances of winning an individual game are 90%, 50%, or 30%, respectively.

(a) What is your probability of winning the ﬁrst game?
(b) Given the information that you won the ﬁrst game, what is the probability that you will also win the second game (assume that given the skill level of your opponent, the outcomes of the two games are independent each other)?

Sol)
(a)
Let $F$ be the event that winning the first game.
Let $W$ be the event that winning the individual game.
Let $B, I, M$ be the event that choose opponent beginner, intermediate, master.
By LOTP,
$$
\begin{align}
P(F) &= P(W|B)P(B)+P(W|I)P(I)+P(W|M)P(M) \\
&= \frac{0.9+0.5+0.3}{3} = \frac{1.7}{3}=\frac{17}{30}
\end{align}
$$

(b)
Let $S$ be the event that winning second game.
We want to find $P(S|F)$.
By LOTP,
$$
\begin{align}
P(S|F) &= P(S|B,F)P(B|F)+P(S|I,F)P(I|F)+P(S|M,F)P(M|F) \\
&= 0.9P(B|F)+0.5P(I|F)+0.3P(M|F)
\end{align}
$$

$$
\begin{align}
P(B|F) &= \frac{P(F|B)P(B)}{P(F)} = 0.9\cdot\frac{1}{3}\cdot\frac{30}{17} \\
P(I|F) &= \frac{P(F|I)P(I)}{P(F)} = 0.5\cdot\frac{1}{3}\cdot\frac{30}{17} \\
P(M|F) &= \frac{P(F|M)P(M)}{P(F)} = 0.3\cdot\frac{1}{3}\cdot\frac{30}{17}
\end{align}
$$
So,
$$
P(S|F) = \frac{81+25+9}{170} = \frac{115}{170}
$$
___
###### 9. Calvin and Hobbes play a match consisting of a series of games, where Calvin has probability $p$ of winning each game (independently). They play with a “win by two” rule: the ﬁrst player to win two games more than his opponent wins the match. Find the probability that Calvin wins the match (in terms of $p$) by conditioning, using the law of total probability.

Sol)
Let $D_{i}$ be the state that Calvin wins $i$ games more than his opponent.
Possible values of $i$ are $-2, -1, 0, 1, 2$.
Let $P_{i}$ be the probability that Calvin wins the match starting from state $D_{i}$.
It is obvious that $P_{2} = 1, P_{-2} = 0$.(Already win, Already lose)
Let $q = 1-p$.
By LOTP,
$$
\begin{align}
P_{-1} &= pP_{0} + qP_{-2} = pP_{0} \\
P_{1} &= pP_{2} + qP_{0} = p+qP_{0} \\
P_{0} &= pP_{1} + qP_{-1} \\
&=p(p+qP_{0})+pqP_{0} \\
\rightarrow (1-2pq)P_{0}&=p^{2} \\
\rightarrow P_{0}&=\frac{p^{2}}{1-2p(1-p)}
\end{align}
$$
___
###### 10. Prove law of total probability with extra conditioning.

Sol)
Let $A_{i}$ be the partition of $S$ with $P(A_{i}\cap E) > 0$.
$$
\begin{align}
P(B|E) &= \frac{P(B\cap E)}{P(E)} \\
&= \frac{P\left( B\cap \left(\bigcup A_{i}\right) \cap E \right)}{P\left(\left(\bigcup A_{i}\right) \cap E \right)} \\
&=\sum \frac{P(B\cap A_{i}\cap E)}{P(E)} \\
&=\sum \frac{P(B\cap A_{i}\cap E)}{P(A_{i}\cap E)} \frac{P(A_{i}\cap E)}{P(E)} \\
&=\sum P(B|A_{i},E)P(A_{i}|E)
\end{align}
$$
___
###### 11. Prove: If $A$ and $B$ are independent, so do $A$ and $B^c$, $A^c$ and $B$, and $A^c$ and $B^c$.

Sol)
Want to show that $P(A\cap B^{c}) = P(A)P(B^{c})$.
Note that $P(A\cap B) = P(A)P(B)$ and $P(A\cap B) + P(A\cap B^{c}) = P(A)$.
So, $P(A)P(B) + P(A\cap B^{c}) = P(A)\rightarrow P(A\cap B^{c}) = P(A)(1-P(B)) = P(A)P(B^{c})$.
Simillarly,
$P(A^{c}\cap B)+P(A\cap B) = P(B)\rightarrow P(A^{c}\cap B) = P(B)(1-P(A)) = P(A^{c})P(B)$.
$P(A^{c}\cap B^{c}) + P(A^{c}\cap B) = P(A^{c})\rightarrow P(A^{c}\cap B^{c}) = P(A^{c})(1-P(B)) = P(A^{c})P(B^{c})$.
___
