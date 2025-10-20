___
1. **아래의 E-R diagram으로 표현한 E-R modeling 결과를 relation schemas로 변환하여라.**
* 릴레이션명과 애트리뷰트명은 E-R diagram에서 사용한 이름을 사용하시오.
* 애트리뷰트 타입(type)은 정의할 필요 없음.
* E-R modeling 결과에 표현된 제약조건들을 빠짐없이 정의하여야 함.
* 변환된 각 relation schema는 아래 제시된 양식(참고양식)에 맞춰 작성하여야 함.
![[Pasted image 20240531142548.png]]
___
1. **주연배우**

| 속성명  | 제약조건 | 식별자구분 | 비고  |
| ---- | ---- | ----- | --- |
| 배우번호 | PK   | PK    |     |
| 배우예명 |      |       |     |
| 본명   |      |       |     |
| 생년월일 |      |       |     |

2. **출연**

| 속성명  | 제약조건  | 식별자구분 | 비고   |
| ---- | ----- | ----- | ---- |
| 배우번호 | PK,FK | PK,FK | 주연배우 |
| 영화번호 | PK,FK | PK,FK | 영화   |

3. **영화**

| 속성명  | 제약조건 | 식별자구분 | 비고  |
| ---- | ---- | ----- | --- |
| 영화번호 | PK   | PK    |     |
| 영화제목 |      |       |     |
| 영화장르 |      |       |     |

4. **영화 DVD**

| 속성명   | 제약조건  | 식별자구분 | 비고  |
| ----- | ----- | ----- | --- |
| 영화번호  | PK,FK | PK,FK | 영화  |
| DVD번호 | PK,FK | PK,FK | DVD |

5. **DVD**

| 속성명    | 제약조건 | 식별자구분 | 비고  |
| ------ | ---- | ----- | --- |
| DVD 번호 | PK   | PK    |     |
| DVD 방식 |      |       |     |

6. **대여 DVD**

| 속성명       | 제약조건             | 식별자구분  | 비고  |
| --------- | ---------------- | ------ | --- |
| 대여 번호     | PK, FK, Not Null | PK, FK | 대여  |
| 대여 DVD 번호 | PK, FK           | PK, FK | DVD |
| 반납 일자     |                  |        |     |

7. **대여**

| 속성명   | 제약조건     | 식별자구분 | 비고  |
| ----- | -------- | ----- | --- |
| 대여 번호 | PK       | PK    |     |
| 대여 일자 |          |       |     |
| 회원 번호 | Not Null | FK    | 회원  |

8. **회원**

| 속성명   | 제약조건 | 식별자구분 | 비고  |
| ----- | ---- | ----- | --- |
| 회원 번호 | PK   | PK    |     |
| 성명    |      |       |     |
| 주소    |      |       |     |

9. **회원 전화번호**

| 속성명   | 제약조건         | 식별자구분        | 비고  |
| ----- | ------------ | ------------ | --- |
| 회원 번호 | PK, FK       | PK, FK       | 회원  |
| 전화 번호 | PK, Not Null | PK, Not Null |     |


___
2. **다음 문제에 대하여 답하시오.**
___
* **Practice Exercise 7.1**
Suppose that we decompose the schema $R = (A, B, C, D, E)$ into
$$
\begin{align}
(A,B,C) \\
(A,D,E)
\end{align}
$$
Show that this decomposition is a lossless decomposition if the following set $F$ of functional dependencies holds:
$$
\begin{align}
A &\rightarrow BC \\
CD &\rightarrow E \\
B &\rightarrow D \\
E &\rightarrow A
\end{align}
$$
___
Recall that decomposition $\{R_{1},R_{2}\}$ is **lossless** when $R_{1}\cap R_{2}\rightarrow R_{1}$ or $R_{1}\cap R_{2} \rightarrow R_{2}$.
Let $R_{1} = (A, B, C), R_{2} = (A, D, E)$. Then, $R_{1}\cap R_{2} = A$.
Since $A$ is a candidate key, $R_{1}\cap R_{2} \rightarrow R_{1}$.(See Exercise 7.6)
___
* **Practice Exercise 7.6**
Compute the closure of the following set $F$ of functional dependencies for relation schema $R = (A, B, C, D, E)$.
$$
\begin{align}
A &\rightarrow BC \\
CD &\rightarrow E \\
B &\rightarrow D \\
E &\rightarrow A
\end{align}
$$
List the candidate keys for $R$.
___
Note that we can find all of $F^{+}$ by applying Armstrong's Axioms.
* If $\beta \subseteq \alpha$, then $\alpha \rightarrow \beta$ (reflexivity)
* If $\alpha \rightarrow \beta$, then $\gamma \alpha \rightarrow\gamma \beta$ (augmentation)
* If $\alpha \rightarrow\beta$ and $\beta \rightarrow\gamma$, then $\alpha \rightarrow \gamma$ (transitivity)
To simplify matters further, we list additional rules.
* If $\alpha \rightarrow \beta$ and $\alpha \rightarrow \gamma$, then $\alpha \rightarrow \beta\gamma$. (Union rule)
* If $\alpha \rightarrow \beta\gamma$, then $\alpha \rightarrow \beta$ and $\alpha \rightarrow \gamma$. (Decomposition rule)
* If $\alpha \rightarrow \beta$ and $\gamma \beta \rightarrow \delta$, then $\alpha \gamma \rightarrow\delta$. (Pseudotransitivity rule)

$A\rightarrow BC$ $\xrightarrow{\text{Decomposition Rule}}$ $A\rightarrow B$ and $A\rightarrow C$
$A\rightarrow B$ and $B \rightarrow D$ $\xrightarrow{\text{transitivity}}$ $A\rightarrow D$
$A\rightarrow C$ and $A \rightarrow D$ $\xrightarrow{\text{Union Rule}}$ $A\rightarrow CD$
$A\rightarrow CD$ and $CD \rightarrow E$ $\xrightarrow{\text{transitivity}}$ $A \rightarrow E$
$A\rightarrow B$ and $A\rightarrow C$ and $A\rightarrow D$ and $A \rightarrow E$ $\xrightarrow{\text{Union Rule}}$ $A \rightarrow ABCDE$
$E \rightarrow A$ and $A \rightarrow ABCDE$ $\xrightarrow{\text{transitivity}}$ $E \rightarrow ABCDE$
$CD \rightarrow E$ and $E \rightarrow ABCDE$ $\xrightarrow{\text{transitivity}}$ $CD \rightarrow ABCDE$
$B\rightarrow D$ $\xrightarrow{\text{augmentation}}$ $BC\rightarrow CD$
$BC \rightarrow CD$ and $CD \rightarrow ABCDE$ $\xrightarrow{\text{transitivity}}$ $BC \rightarrow ABCDE$
$B\rightarrow D$ $\xrightarrow{\text{augmentation}}$ $BD \rightarrow D$
...
We can do this algorithm to compute $F^{+}$. There are so many dependencies to list all.
Here, any functional dependency having $A, E, BC, CD$ on the left side is in $F^{+}$.
In other words, If $\alpha \subseteq (A,B,C,D,E)$, $A^{*}\rightarrow\alpha$, $BC^{*}\rightarrow\alpha$, $CD^{*}\rightarrow\alpha$, $E^{*}\rightarrow\alpha$ where $*$ is the any set of attributes in $R$.
We can use same logic for the candidate keys are $A, BC, CD, E$.

___
* **Exercise 7.21**
Give a lossless decomposition into BCNF of schema $R$ of Exercise 7.1.
___
From Practice Exercise 7.6, we know that $B\rightarrow D$ is non-trivial and $B$ is not a super key.
Use BCNF decomposition algorithm.
*result* := $\{R\}$;
$F^{+} = \{\text{any functional dependency having }A, E, BC, CD\text{ on the left side}\}$.
$R$ is not in BCNF.
$B\rightarrow D$ is non-trivial that highly holds on $R$ and $B\cap D=\varnothing$ and $B\rightarrow ABCDE \not\in F^{+}$.
Therefore, *result* := (*result*-$R$)$\cup$($R-D$)$\cup$($B,D$);
So, $\{(A,B,C,E)\cup(B,D)\}$ are in BCNF of schema $R$.
___
* **Exercise 7.30**
 Consider the following set $F$ of functional dependencies on the relation schema $(A, B, C, D, E, G)$:
$$
\begin{align}
A &\rightarrow BCD \\
BC &\rightarrow DE \\
B &\rightarrow D \\
D &\rightarrow A
\end{align}
$$
a. Compute $B^{+}$.
b. Prove (using Armstrong’s axioms) that $AG$ is a superkey.
e. Give a BCNF decomposition of the given schema using the original set $F$ of functional dependencies.
___
a. Compute $B^{+}$.
We will use an algorithm.
result = $\{B\}$.
First iteration :
$B\rightarrow D$ satiesfy $B \subseteq \{B\}$. result = $\{B,D\}$
$D\rightarrow A$ satiesfy $D \subseteq \{B,D\}$. result = $\{B,D,A\}$
Second iteration:
$A \rightarrow BCD$ satiesfy $A \subseteq \{B,D,A\}$. result = $\{B,D,A,C\}$
$BC \rightarrow DE$ satiesfy $BC \subseteq \{B,D,A,C\}$. result = $\{B,D,A,C,E\}$.
Therefore, $B^{+} = \{B,D,A,C,E\}$.

b. Prove (using Armstrong’s axioms) that $AG$ is a superkey.
$A\rightarrow BCD$ $\xrightarrow{\text{Decomposition Rule}}$ $A\rightarrow BC$
$A\rightarrow BC$ and $BC \rightarrow DE$ $\xrightarrow{\text{transitivity}}$ $A \rightarrow DE$
$A\rightarrow BC$ and $A \rightarrow DE$ $\xrightarrow{\text{Union Rule}}$ $A \rightarrow BCDE$
$A \rightarrow BCDE$ $\xrightarrow{\text{augmentation}}$ $AG \rightarrow ABCDEG$.
Therefore, $AG$ is a superkey.

e. Give a BCNF decomposition of the given schema using the original set $F$ of functional dependencies.

Use BCNF algorithm.
$\{(A,B,C,D)\cup (A,E)\cup(A,F)\}$ are in BCNF.
___
