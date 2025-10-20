### 상관계수와 상관분석의 기초

#### 둘 이상의 변량 사이 관계를 보려면

수험생 30명의 토익 성적과 텝스 성적이 주어져 있을 때, **둘 사이에 상관관계가 존재할까?**
잘하는 놈이 잘 할까?

#### 두 변량의 상관관계는? 상관계수

* Pearson Correlation Coefficient
두 변수 사이에 존재하는 **선형적인 상관관계**를 수치로 나타낸 것.
크기는 -1부터 1사이. 값이 0이면 상관관계가 없다.
부호가 양이면, 양의 상관관계, 음이면 음의 상관관계.
![[Pasted image 20240422093733.png]]

#### DataFrame 내에서의 상관계수 도출

```python
import pandas as pd
df = pd.read_csv('english.csv')
# 데이터를 불러와 DataFrame 생성
df_corr = df.corr(method = 'pearson')
# DataFrame 기반 상관계수 도출
# df_corr 조합 별 상관계수를 출력
```
주어진 데이터 중 결측치가 부분적으로 존재할때 pandas는 어떻게 상관계수를 계산하나?
결측치가 있는 Row를 제외한 데이터에 대한 상관계수를 계산한다.

#### 상관계수 해석에서의 유의점

1. Pearson 상관계수는 **선형적 상관관계**를 나타내는 지표이다.

즉, Pearson 상관계수가 낮다고 해서 상관관계가 없다는 것은 아니다. $y = x^{2}$를 생각해보자. 이건 선형적인 상관관계는 아니지만, 분명 상관관계가 없는 것이 아니다.

제곱관계를 어떻게 파악할 수 있을까?

2. 큰 상관계수가 **인과관계**를 보장하는 것은 아니다.
제곧내
3. 상관계수 $\neq$ 직선의 기울기
제곧내

#### 값이 아닌 순위를 기준으로

```python
import pandas as pd
df = pd.read_csv('english.csv')
# 데이터를 불러와 DataFrame 생성
df_corr = df.corr(method = 'spearman')
# DataFrame 기반 상관계수 도출
# df_corr 조합 별 상관계수를 출력
```

x와 y의 값 대신 <x, y>의 순위를 이용하면?
$y=x^{2}$의 예시면,
x순위 5/4/3/2/1
y순위 5/4/3/2/1
순위 pearson = 1

spearman 상관계수는 순위 상관계수의 일종임.

#### 네가 오르면 나도 오른다, Kendall

$$
\tau = \frac{\text{concordant} - \text{discordant}}{\text{total}}
$$
조화 순서쌍 = 잘하는 놈이 잘하는가


### 선형회귀의 뜻과 실재


