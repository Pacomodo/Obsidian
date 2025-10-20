### k-최근접 이웃에 기반한 분류

이전에 결측치 대체를 배우면서 k-nearest neighborhood를 배웠었다.
근데 k-nearest는 분류를 위해 태어난 기법임.
#### 가재는 게 편, 솔개는 매 편, 데이터는?
![[Pasted image 20240429151221.png|center|500]]
파란 원을 기준으로 하면, 내 주변에는 보석이 가까움. 즉, 보석으로 분류.
빨간 원을 기준으로 하면, 내 주변에는 폭탄이 더 많다. 즉, 지뢰로 분류.
이전에 결측치 대체에서, 가장 가까운 놈들을 찾아서 평균이나 가중평균을 내서 대체를 했던것을 잘 생각해보자.

#### 이웃 따라 강남 간다, k-NN
k-Nearest neighbor은 새로운 데이터가 주어지면 그때 그때마다 거리 연산을 통한 분류가 이루어지므로, 학습이라고 부르기에는 조금 애매하다.
즉, 학습용 데이터로 학습을 하고 분류를 하는건 아니다.
![[Pasted image 20240429151621.png]]
이 상황인 경우, 모든 데이터를 따지는 것이므로, 보물이 있을 것이라고 예측한다.
k를 어떻게 설정하냐에 따라서 분류하는 것이 달라진다.

#### Python에서의 k-최근접 이웃 분류
```python
import pandas as pd
from sklearn.neighbors import KNeighborsClassifier # K-NN 분류기
from sklearn.model_selection import train_test_split # 데이터 분리
from sklearn.metrics import confusion_matrix  # 혼동 행렬
```
```python
df = pd.read_csv('treasure.csv')
```
```python
# 주어진 데이터에서 입력 변수와 예측 변수를 분리
df_x = df[['horizontal', 'vertical']] # 입력 변수는 가로 및 세로 위치
df_y = df['MineOrTreasure'] # 예측 변수는 지뢰 및 보물 여부
```
```python
x_train, x_test, y_train, y_test = train_test_split(df_x, df_y)
```
```python
kNN = KNeighborsClassifier(n_neighbors = 3, metric = 'euclidean')
kNN.fit(x_train, y_train)
```
```python
y_pred = kNN.predict(x_test)
```
```python
confusion_matrix(y_test, y_pred, labels = ['MINE', 'TREASURE'])
```
실행 결과는 다음과 같다.
```python
[[29 0]
 [ 0 31]]
```
Recall : Confusion matrix 복습
![[Pasted image 20240429153045.png|center|500]]
민감도는 $\frac{20}{24}$, 특이도는 $\frac{36}{41}$

### k-NN, 분류뿐 아니라 회귀도?
![[Pasted image 20240429153213.png|center|500]]
거리에 따른 가중치를 고려할 때와 그렇지 않을 때로 나누어 회귀를 수행할 수 있다.
결측치 대체 때 했던 내용들을 잘 생각해보자.

#### Exercise 1
https://colab.research.google.com/drive/1GSPQ2BcS5kB-v6wMiVnQfEv39P9FdQed?hl=ko#scrollTo=N4TbLkzmlav6

### 사후확률과 Naive Bayes 분류

#### 분류를 위한 또 다른 접근, Naive Bayes
사후확률을 계산하여 분류를 수행하는 방법.
각 독립변수가 확률적으로 상호 독립이라는 가정 하에서 활용.
![[Pasted image 20240429154619.png|center|500]]
#### 데이터로부터 결국 찾고자 하는 것은?
![[Pasted image 20240429154840.png|center|500]]
사후확률 값을 이용하여 어떻게 분류를 수행할 수 있는가?
승리 사후확률과 패배 사후확률을 계산해서 높은 것 채택

#### 직접 얻기는 쉽지가 않다, 그렇다면?
![[Pasted image 20240429160527.png|center|500]]
같지는 않다. 근데 "근사"할 수 있지 않을까
계산을 해보자.
$P(\text{실책}|\text{승리}) = \frac{3}{6}$, $P(\text{선발}|\text{승리}) = \frac{1}{6}$, $P(\text{선취점}|\text{승리}) = \frac{3}{6}$, $P(\text{홈런X}|\text{승리}) = \frac{3}{6}$
$P(\text{승리})=\frac{6}{10}$
따라서, $\frac{3}{5}\times \frac{1}{2}\times \frac{1}{6}\times \frac{1}{2}\times \frac{1}{2}=\frac{1}{80}$과 비례
![[Pasted image 20240429161528.png|center|500]]
#### 계산 과정에서 떠오르는 의문
![[Pasted image 20240429161643.png|center|500]]
#### 실습
https://colab.research.google.com/drive/1GSPQ2BcS5kB-v6wMiVnQfEv39P9FdQed?hl=ko#scrollTo=rtuVV5owvajH
#### 데이터의 형태가 달라진다면?
(BernoulliNB) 입력 변수들이 모두 이진 형태인 경우에 활용
(CategoricalNB) 입력 변수들이 범주형인 경우에 활용

#### Exercise 2
지속적인 스팸 문자 메시지에 시달리던 다원이는 아래 정보를 토대로 Naive Bayes 분류기를 개발했다.
* 전체 문자 메시지 중 스팸 문자 메시지의 비율은 60%
* 어떤 문자 메시지가 스팸일 때, 그 문자 메시지가 '배팅'이라는 낱말을 포함할 확률은 90%
* 어떤 문자 메시지가 스팸이 아닐 때, 그 문자 메시지가 '배팅'이라는 낱말을 포함할 확률은 20%
위 분류기에 따를 때, 다음의 문자 메시지가 스팸으로 분류되는지 여부를 각각 판단하면?
단, 라플라스 보정은 적용하지 않는다.
(가) 안전한★배팅지금.가입하면~마일리지지급www.sportslotto.net
(나) \[공지\]이중전공 선발관련, KUPID 로그인 후 결과 확인바람

(가)를 보면, $60\% \times 90\% = 0.54k$ vs $40\% \times 20\% = 0.08k$ 따라서, (가)는 스팸으로 분류됨.
(나)를 보면, $60\% \times 10\% = 0.06k$ vs $40\% \times 80\% = 0.32k$ 따라서, (나)는 스팸으로 분류되지 않음.

### 로지스틱 회귀의 원리와 그 실제

#### 식은 회귀, 문제는 분류?
![[Pasted image 20240429165502.png|center|500]]

#### 이탈 문제를 회귀로 풀자는 건데
![[Pasted image 20240429165642.png|center|500]]
#### 승산으로 정의하는 로지스틱 회귀

![[Pasted image 20240429165757.png|center|500]]
$p$의 범위는 0~1사이

#### 본질은 해석, 이 고객은 이탈할까?
![[Pasted image 20240429170838.png|center|500]]
로지스틱 회귀식 우변 =
$(-0.8259)+(0.001896\times 50)+(0.71585\times 1)+(0.715\times 1)-(0.0654\times 80) = -4.53225$
즉, 
$$
\begin{align}
\log\left( \frac{p}{1-p} \right) &= -4.53 \\
\frac{p}{1-p} &= e^{-4.53} \\
\frac{1}{p} - 1 &= e^{4.53} \\
p &= \frac{1}{1+e^{4.53}}
\end{align}
$$
