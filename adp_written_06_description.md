## 4과목 서술형

### 4장 서술형 문제
#### 1. 서술형 문제란?

- R프로그램으로 분석한 결과를 해석 또는 시각화 자료를 보고 해석하는 문제가 출제됨
- 문제를 풀기 위해서는 분석 결과에 대한 해석, 분석과 관련된 시각자료에 대한 해석 방법을 숙지해야 됨
- 인사이트를 제시하라는 문제를 자주 출제함. 해결책 제시가 중요

#### 2. 탐색적 분석

##### 가. 개요

- R 프로그램에서 데이터에 대한 요약(summary)과 데이터의 일부(head)를 보여 준 뒤, 데이터 분석 방법과 인사이트를 제시하라는 무제가 출제됨
- **분석방법론을 나열**하고, 그 중 **최적의 방법을 선택**하여 데이터로 **분석을 실행하는 과정을 상세하게 기술**해야 한다.
- 그리고 예상되는 **분석 결과를 제시**하고 이러한 결과를 통해 어떤 인사이트를 얻게 될지를 예상해서 기술해야 한다.
- 분석과정에서 예상되는 주의 사항 등을 추가하면 더 좋은 점수를 받을 수 있다.

##### 나. 예상문제

- iris 데이터셋은 붓꽃에 대한 데이터이며, 꽃받침의 길이(Sepal.Length), 꽃받침의 너비 (Sepal.Width), 꽃잎의 길이(Petal.Length), 꽃잎의 너비(Petal,Width), 종류 (Specise / setosa, versicolor, virginica) 총 5개의 변수로 구성되어 있으며, 아래는 iris 데이터의 상위 6개와 기초 통계량이다.

```R
> head(iris)
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa
> summary(iris)
  Sepal.Length    Sepal.Width     Petal.Length    Petal.Width          Species  
 Min.   :4.300   Min.   :2.000   Min.   :1.000   Min.   :0.100   setosa    :50  
 1st Qu.:5.100   1st Qu.:2.800   1st Qu.:1.600   1st Qu.:0.300   versicolor:50  
 Median :5.800   Median :3.000   Median :4.350   Median :1.300   virginica :50  
 Mean   :5.843   Mean   :3.057   Mean   :3.758   Mean   :1.199                  
 3rd Qu.:6.400   3rd Qu.:3.300   3rd Qu.:5.100   3rd Qu.:1.800                  
 Max.   :7.900   Max.   :4.400   Max.   :6.900   Max.   :2.500
```

1) 문제와 해결 방법
   - 문제 : 붓꽃의 종류를 분류하기 위한 방법을 제시하시오. 결과물로 부터 얻을 수 있는 인사이트를 예시를 사용하여 설명하시오.
   - 위 문제 해결을 위해서는 **통계분석과 데이터마이닝 분석 방법론 종류와 적용에 대한 정확한 숙지**가 필요하다.
2) 해석 결과
   - Q. 붓꽃의 종류를 분류하기 위한 방법을 제시하시오
   - A. 
     - 상위 6개의 데이터와 데이터에 대한 기초 통계량을 확인했을 때, Species는 범주형 변수이며, 나머지 Sepal.Length, Sepal.Width, Petal.Length, Petal.Width는 수치형 변수임을 확인할 수 있으며, **종속변수는 Species** 이며, **설명변수는 Sepal.Length, Sepal.Width, Petal.Length, Petal.Width**이다. 붓꽃의 종류인 Species(3가지 종류, setosa, versicolor, virginica)를 분류하기 위해서는 정형 데이터마이닝 중 분류분석을 사용하여 붓꽃의 종류를 분류하여야 한다. 
     - 분류분석의 방법은 **로지스틱 회귀분석, 의사결정나무, 앙상블기법(배깅, 부스팅, 랜덤포레스트), 인공신경망, 나이브 베이지안, KNN(K-Nearest Neighbor), SVM** 등이 있다. 이 중 **의사결정나무** 분석방법을 활용한다면 R 프로그램에서는 `rpart, ctree` 함수 등을 사용해서 모델을 구축한다. 예를들어 `rpart(Species~., data=iris)` 라는 코드로 모델을 구축하는 것은 `iris` 데이터를 사용하여 `종속변수` `Species`에 대해 모든 `설명변수`(`Sepal.Length, Sepal.Width, Petal.Length, Petal.Width`)를 사용하여 모델을 구축한다고 할 수 있다. 분석 결과가 나타난다면 분류할 데이터의 개수는 `n`을 통해 알 수 있고 **1) root를 시작으로 몇 개의 데이터가 몇 개로 분류되는지에 대해 해석**을 진행한다.
     - 의사결정나무의 경우 분석 결과만으로는 해석에 어려움이 있을 수 있으므로 시각화하여 해석을 한다면 쉽게 해석에 접근할 수 있다. 기존의 `plot` 함수를 활용하여도 되지만, `rpart.plot` 라는 라이브러리에서 .... P.151 보고 추가 작업해라





#### 3. 회귀분석 (p.151)

##### 가. 개요

-   회귀분석은 4과목 문제로도 가장 많이 출제되는 파트이다. 회귀뷘석에 대한 R 프로그램 분석 결과 중 **유의한 설명변수 파악, 회귀 모형의 유의성 검토, 결정 계수 해석, 모형 수식 작성** 등에 대한 해석은 정확히 숙지해야 한다.

##### 나. 예상문제 (Cars93)

Q. MASS 패키지의 Cars93 이라는 데이터셋의 가격(price)을 종속변수로 선정하고, 엔지크기, RPM, 무게를 이용해서 다중회귀분석을 실시했다. 아래의 결과를 해석하시오

```R
> # 회귀분석 (p.152)
> library(MASS)
> head(Cars93)
  Manufacturer   Model    Type Min.Price Price Max.Price MPG.city MPG.highway            AirBags DriveTrain
1        Acura Integra   Small      12.9  15.9      18.8       25          31               None      Front
2        Acura  Legend Midsize      29.2  33.9      38.7       18          25 Driver & Passenger      Front
3         Audi      90 Compact      25.9  29.1      32.3       20          26        Driver only      Front
4         Audi     100 Midsize      30.8  37.7      44.6       19          26 Driver & Passenger      Front
5          BMW    535i Midsize      23.7  30.0      36.2       22          30        Driver only       Rear
6        Buick Century Midsize      14.2  15.7      17.3       22          31        Driver only      Front
  Cylinders EngineSize Horsepower  RPM Rev.per.mile Man.trans.avail Fuel.tank.capacity Passengers Length Wheelbase
1         4        1.8        140 6300         2890             Yes               13.2          5    177       102
2         6        3.2        200 5500         2335             Yes               18.0          5    195       115
3         6        2.8        172 5500         2280             Yes               16.9          5    180       102
4         6        2.8        172 5500         2535             Yes               21.1          6    193       106
5         4        3.5        208 5700         2545             Yes               21.1          4    186       109
6         4        2.2        110 5200         2565              No               16.4          6    189       105
  Width Turn.circle Rear.seat.room Luggage.room Weight  Origin          Make
1    68          37           26.5           11   2705 non-USA Acura Integra
2    71          38           30.0           15   3560 non-USA  Acura Legend
3    67          37           28.0           14   3375 non-USA       Audi 90
4    70          37           31.0           17   3405 non-USA      Audi 100
5    69          39           27.0           13   3640 non-USA      BMW 535i
6    69          41           28.0           16   2880     USA Buick Century
> lm(Price~EngineSize+RPM+Weight, data=Cars93)

Call:
lm(formula = Price ~ EngineSize + RPM + Weight, data = Cars93)

Coefficients:
(Intercept)   EngineSize          RPM       Weight  
 -51.793292     4.305387     0.007096     0.007271 

> attach(Cars93) # 함수 호출 후 모든 코드에서 컬럼들을 직접 전근할 수 있게 해줌

> lm(Price~EngineSize+RPM+Weight, data=Cars93)

Call:
lm(formula = Price ~ EngineSize + RPM + Weight, data = Cars93)

Coefficients:
(Intercept)   EngineSize          RPM       Weight  
 -51.793292     4.305387     0.007096     0.007271  

> summary(lm(Price~EngineSize+RPM+Weight, data = Cars93))

Call:
lm(formula = Price ~ EngineSize + RPM + Weight, data = Cars93)

Residuals:
    Min      1Q  Median      3Q     Max 
-10.511  -3.806  -0.300   1.447  35.255 

Coefficients:
              Estimate Std. Error t value Pr(>|t|)    
(Intercept) -51.793292   9.106309  -5.688 1.62e-07 ***
EngineSize    4.305387   1.324961   3.249  0.00163 ** 
RPM           0.007096   0.001363   5.208 1.22e-06 ***
Weight        0.007271   0.002157   3.372  0.00111 ** 
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 6.504 on 89 degrees of freedom
Multiple R-squared:  0.5614,	Adjusted R-squared:  0.5467 
F-statistic: 37.98 on 3 and 89 DF,  p-value: 6.746e-16

> 
```

1.   해석방법 : 다변량 회귀분석은 아래와 같은 단계로 분석할 수 있다.
     -   1단계: 다변량 모형에 대한 가설검정 실시
     -   2단계: 각 변수의 계수에 대한 가설검정 실시
     -   3단계: 결정계수를 통한 모형에 대한 설명력 확인
     -   4단계: 다중공선성의 확인을 통한 모형의 안정성 확인
     -   5단계: 잔차분석을 통한 다변량 회귀분석의 가정 확인
2.   해석결과
     -   위의 분석은 1~3단계 까지 해석 가능
     -   모형의 구조는 formula를 통해 확인할 수 있으며, 가격(Price)을 종속변수로 예측하기 위해 엔진사이즈(EngineSize), 회전수(RPM), 무게(Weight)라는 3가지 설명변수를 활용하여 모형이 설계되었음을 확인할 수 있다.
     -   1단계 : 다변량 회귀분석에서 종속변수인 가격(Price)에 대한 설명변수들 간의 모형에 대한 통계적 타당성을 가설 검정한다.
         -   귀무가설(H<sub>0</sub>) : EngineSize = RPM = Weight = 0
         -   대립가설(H<sub>1</sub>) : 적어도 하나의 설명변수는 0이 아니다.
         -   F-통계량은 37.98이며 p-value 가 6.746e-16 로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형은 통계적으로 매우 유의함을 알 수 있다.
     -   2단계 : 다변량 회귀분석에 활용된 각 설명변수들의 계수들에 대한 통계적 타당성을 가설 검정한다.
         -   **첫 번째 설명변수인 엔지사이즈(EngineSize)**에 대한 통계적 가설검정을 실시
             -   귀무가설(H<sub>0</sub>) : EngineSize = 0
             -   대립가설(H<sub>1</sub>): EngineSize $\neq$ 0
             -   t-통계량은 3.249 이며 p-value 값이 0.00163이므로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 EngineSize는 통계적으로 유의함을 알 수 있다.
         -   **두 번째 설명변수인 RPM**의 경우, t-통계량은 5.208이며 p-value 가 1.22e-06이므로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다.그러므로 RPM은 통계적으로 유의함을 알 수 있다.
         -   **세 번째 설명변수인 Weigh**t의 경우, t-통계량은 3.372이며 p-value가 0.00111이므로 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형의 모든 설명변수는 통계적으로 유의함을 알 수 있다.
     -   3단계 : 통계적으로 유의성을 확인한 다변량 회귀모형이 전체 데이터를 얼마나 **잘 설명하는지** 확인하기 위해 **결정계수(R<sup>2</sup>)**를 확인한다.
         -   결정계수를 확인하기 위해 Multiple R-squared와 R-squared를 확인결과 0.5614 와 0.5467 로 나타났으며, 이는 전체 데이터를 설계된 다변량 회귀모형이 56.14%, 54.67%를 설명하고 있다고 해석할 수 있다.
     -   최종적으로 결과를 종합해보면 **추정된 다변량 회귀식**은 아래와 같다.
     -   ```Price = -51.79 + 4.31*EngineSize + 0.007*RPM + 0.007*Weight ```
     -   회귀식을 통해 EngineSize, RPM, Weight 가 모두 증가할수록 가격(Price)도 증가하는 것을 확인할 수 있으며, **Price에 가장 영향을 많이 끼치는 변수는 EngineSize이며, 차량의 가격에서 EngineSize를 가장 많이 신경 써야한다고 결론을 도출**할 수 있다.



##### 다. 예상문제 (swiss)

Q. swiss 데이터는 프랑스어를 사용하는 스위스 내 지역의 출산율과 관련된 자료이다. 아래는 각 변수의 내용과 출산율을 농업종사자 비율 등 5개의 변수로 설명하기 위한 모형을 추정한 결과이다. 아래의 결과를 해석하시오

```R
> # 서술형 회귀분석 (swiss 데이터 p.154)
> # 설명변수 : Agriculture : 농업, Infant.Mortality (영아사망률)
> # 종속변수 : Fertility 출산
> summary(step(lm(Fertility~1, data=swiss),
+             scope = list(lower = ~1, upper=~Agriculture+Examination+Education
+                           +Catholic+Infant.Mortality),
+             direction="both"))
Start:  AIC=238.35
Fertility ~ 1

                   Df Sum of Sq    RSS    AIC
+ Education         1    3162.7 4015.2 213.04
+ Examination       1    2994.4 4183.6 214.97
+ Catholic          1    1543.3 5634.7 228.97
+ Infant.Mortality  1    1245.5 5932.4 231.39
+ Agriculture       1     894.8 6283.1 234.09
<none>                          7178.0 238.34

Step:  AIC=213.04
Fertility ~ Education

                   Df Sum of Sq    RSS    AIC
+ Catholic          1     961.1 3054.2 202.18
+ Infant.Mortality  1     891.2 3124.0 203.25
+ Examination       1     465.6 3549.6 209.25
<none>                          4015.2 213.04
+ Agriculture       1      62.0 3953.3 214.31
- Education         1    3162.7 7178.0 238.34

Step:  AIC=202.18
Fertility ~ Education + Catholic

                   Df Sum of Sq    RSS    AIC
+ Infant.Mortality  1    631.92 2422.2 193.29
+ Agriculture       1    486.28 2567.9 196.03
<none>                          3054.2 202.18
+ Examination       1      2.46 3051.7 204.15
- Catholic          1    961.07 4015.2 213.04
- Education         1   2580.50 5634.7 228.97

Step:  AIC=193.29
Fertility ~ Education + Catholic + Infant.Mortality

                   Df Sum of Sq    RSS    AIC
+ Agriculture       1    264.18 2158.1 189.86
<none>                          2422.2 193.29
+ Examination       1      9.49 2412.8 195.10
- Infant.Mortality  1    631.92 3054.2 202.18
- Catholic          1    701.74 3124.0 203.25
- Education         1   2380.38 4802.6 223.46

Step:  AIC=189.86
Fertility ~ Education + Catholic + Infant.Mortality + Agriculture

                   Df Sum of Sq    RSS    AIC
<none>                          2158.1 189.86
+ Examination       1     53.03 2105.0 190.69
- Agriculture       1    264.18 2422.2 193.29
- Infant.Mortality  1    409.81 2567.9 196.03
- Catholic          1    956.57 3114.6 205.10
- Education         1   2249.97 4408.0 221.43

Call:
lm(formula = Fertility ~ Education + Catholic + Infant.Mortality + 
    Agriculture, data = swiss)

Residuals:
     Min       1Q   Median       3Q      Max 
-14.6765  -6.0522   0.7514   3.1664  16.1422 

Coefficients:
                 Estimate Std. Error t value Pr(>|t|)    
(Intercept)      62.10131    9.60489   6.466 8.49e-08 ***
Education        -0.98026    0.14814  -6.617 5.14e-08 ***
Catholic          0.12467    0.02889   4.315 9.50e-05 ***
Infant.Mortality  1.07844    0.38187   2.824  0.00722 ** 
Agriculture      -0.15462    0.06819  -2.267  0.02857 *  
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 7.168 on 42 degrees of freedom
Multiple R-squared:  0.6993,	Adjusted R-squared:  0.6707 
F-statistic: 24.42 on 4 and 42 DF,  p-value: 1.717e-10
```

1.   해석 방법

     -   벌점화 방식(AIC)의 변수선택법을 활용한 다변량 회귀분석은 아래와 같은 단계로 분석할 수 있다.
     -   1단계 : 변수선택법을 결정하고, 초기모형을 세팅
     -   2단계 : 선택된 최적 모형의 AIC를 계산
     -   3단계 : 선택된 모형에서 변수를 추가/삭제 할 경우의 각 모형에서 AIC를 계산
     -   4단계 : 각 모형에서 최소의 AIC 모형을 선택하여 최적 모형으로 선정
     -   5단계 : 2 ~ 4단계를 반복하고 AIC가 더 이상 줄어들지 않을 때 최종모형을 최적모형으로 선정
     -   6단계 : 다변량 모형에 대한 F-test를 통해 가설검정 실시
     -   7단계 : 각 변수의 계수에 대한 t-test를 통해 가설검정 실시
     -   8단계 : 결정계수를 통한 모형에 대한 설명력 확인
     -   9단계 : 다중공선성의 확인을 통한 모형의 안정성 확인
     -   10단계 : 잔차분석을 통한 다변량 회귀분석의 가정 확인

2.   해석 결과

     -   위의 분석 결과는 해석방법 10단계 중 1~8단계까지 해석이 가능. 모형의 구조는 formula를 통해 확인 가능하며, step 함수를 통해 종속변수에 대해 설명변수가 없을 경우부터 모든 설명변수가 포함될 때의 회귀모형을 비교해 최적의 회귀방정식을 도출할 수 있다. 또, direction에서 ```both```는 단계적 선택법, ```forward```는 전진선택법, ```backward```는 후진제거법을 의미

     -   출산율(Fertility)을 종속변수로 설정하고, 설명변수가 없을 때 부터 최대 모든 설명변수가 포함된 회귀식까지 설정하여 최적의 회귀식을 도출한다

     -   1단계 : 변수선택법을 결정하고, 초기 모형을 설정

         위의 분석결과에서 direction이 ```both```로 설정되어 변수선택법을 단계적 선택법으로 선정했음을 확인할 수 있다. 또, 초기 모형은 ```Fertility~1``` 로 설명변수가 하나도 없는 상태에서부터 시작함을 의미한다.```scope```의 경우 모형 선정 중 최소 설명변수가 아무것도 없는것부터 설명변수가 모두 있는 것까지를 비교하여 모형을 선정한다는 것이다.

     -   2단계 : 선택된 최적 모형의 AIC를 계산

         분석 결과에서 시작 모혀은 ```Fertility~1```이 **최적모형**로 설정되어 있으며 start에서 **AIC 값이 238.35**로 계산되어 있다.

     -   3단계 : 선택된 모형에서 변수를 추가/삭제 할 경우의 각 모형의 AIC를 계산한다.

         ```Fertility~1``` 모형에 대해 설명변수 5개에 대한 각각의 AIC값을 계산하여 자유도 등과 함께 나타낸다. **Education의 AIC 값이 213.04, Examination의 AIC 값은 214.97등으로 나타나 있다.**

     -   4단계 : 각 모형에서 최소의 AIC 모형을 선택하여 최적 모형으로 선정한다.

         계산된 AIC 값을 비교하여 가장 작은 설명변수인 **Education을 추가하여 최적 모형으로 선정**한다.

     -   5단계 : 2 ~ 4단계를 반복하여 AIC가 더 이상 줄어들지 않을 때 최종모형을 최적의 모형으로 선정한다.

         위의 과정을 반복하여 ```Fertility~Education + Catholic + Infant.Mortality + Agriculture```이 최적의 모형으로 선정되고 마지막 **Step에서 AIC가 189.86으로 계산되고 추가되지 않은 설명변수 Examination의 AIC 값이 190.96**로 나타나 해당 변수를 모형에 추가하지 않고 **최적의 모형을 ```Fertility~Education + Catholic + Infant.Mortality + Agriculture```으로 선정**했다.

     -   6단계 : 다변량 회귀분석에서 종속변수인 출산율(Fertility)에 대한 설명변수들 간의 모형에 대한 통계적 타당성을 가설 검정한다.

         귀무가설 (H<sub>0</sub>) : Education = Catholic = Infant.Mortality = Agriculture = 0

         대립가설 (H<sub>1</sub>) : 적어도 하나의 설명변수는 0이 아니다.

         F-통계량은 24.42이며 p-value 값이 1.717e-10로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형은 통계적으로 매우 유의함을 알 수 있다.

     -   7단계 : 다변량 회귀분석에서 활용된 각 설명변수들의 계수들에 대한 통계적 타당성을 가설 검정한다.

         -   **첫 번째 설명변수인 Education에 대한 통계적 가설검정을 실시**한다.

             귀무가설 (H<sub>0</sub>) : Education = 0

             대립가설 (H<sub>1</sub>) : Education $\neq$ 0 

             t-통계량은 -6.617이며 p-value 값이 5.14e-08 이므로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형의 첫 번째 설명변수인 Education은 통계적으로 유의함을 알 수 있다.

         -   **두 번째 설명변수인 Catholic의 경우,** t-통계량은 4.315 이며 p-value 값이 9.50e-05이므로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형의 두 번째 설명변수인 Catholic은 통계적으로 유의함을 알 수 있다.

         -   **세 번째 설명변수인 Weight의 경우**, t-통계량은 2.824 이며, p-value 값이 0.00722 이므로 유의수준 5%하에서 대립가설을 채택하고, **네번째 설명변수인 Agriculture의 경우**, t-통계량은 -2.267이며, p-value 값이 0.02857 이므로 유의수준 5%하에서 대립가설을 채택하게된다. 그러므로 모든 설명변수는 통계적으로 유의함을 알 수 있다.

     -   8단계 : 통계적으로 유의성을 확인한 다변량 회귀모형이 전체 데이터를 얼마나 잘 설명하는지 확인하기 위해 결정계수 (R<sup>2</sup>)를 확인한다.

         결정계수를 확인하기 위해 Multiple R-squared:  0.6993,	Adjusted R-squared:  0.6707 로 나타났으며, 이는 전체 데이터를 설계된 다변량 회귀모형이 69.93%, 67.07%를 설명하고 있다고 해석할 수 있다.

     -   최종적으로 다변량 회귀분석 결과를 종합해 보면 추정된 다변량 회귀식은 Fertility = 62.1 - 0.98*Education + 0.13 * Catholic  + 1.08 * Infant.Mortality - 0.16 * Agriculture 이다. **Fertility 에 가장 영향을 많이 끼치는 변수는 Infant.Mortality이며 , 출산율에서 Infant.Mortality 를 가장 많이 신경 써야한다고 결론을 도출** 할 수 있다.

     

     #### 4. 주성분 분석(p.158)

     ##### 가. 개요

     -   주성분 분석은 주성분의 선택과 관련하여 출제가 되는 파트로 주성분 분석에 대한 R 프로그램 결과 중 **주성분 분석의 누적 기여율(cumulative proportion)과 시각화 자료인 scree plot, biplot에 대한 해석**은 정확히 숙지

     

     ##### 나. 예상문제 (USArrests)

     USArrests 데이터는 미국 50개 주에서 폭행, 살인 및 강간에 대한 10만명의 주민에 대한 체포 통계 포함하는 여러개의 변수가 있다. 아래의 결과를 해석하시오

     ```R
     > # pca
     > # install.packages("factoextra")
     > # install.packages("FactoMineR")
     > library(factoextra)
     > library(FactoMineR)
     
     > pca_rslt = PCA(USArrests, graph = FALSE)
     > summary(pca_rslt)
     
     Call:
     PCA(X = USArrests, graph = FALSE) 
     
     
     Eigenvalues
                            Dim.1   Dim.2   Dim.3   Dim.4
     Variance               2.480   0.990   0.357   0.173
     % of var.             62.006  24.744   8.914   4.336
     Cumulative % of var.  62.006  86.750  95.664 100.000
     
     Individuals (the 10 first)
                     Dist    Dim.1    ctr   cos2    Dim.2    ctr   cos2    Dim.3    ctr   cos2  
     Alabama     |  1.574 |  0.986  0.783  0.392 | -1.133  2.596  0.518 |  0.444  1.107  0.080 |
     Alaska      |  3.051 |  1.950  3.067  0.409 | -1.073  2.327  0.124 | -2.040 23.343  0.447 |
     Arizona     |  2.089 |  1.763  2.507  0.712 |  0.746  1.124  0.127 | -0.055  0.017  0.001 |
     Arkansas    |  1.149 | -0.141  0.016  0.015 | -1.120  2.534  0.950 | -0.115  0.074  0.010 |
     California  |  3.037 |  2.524  5.137  0.690 |  1.543  4.811  0.258 | -0.599  2.010  0.039 |
     Colorado    |  2.114 |  1.515  1.850  0.513 |  0.988  1.971  0.218 | -1.095  6.726  0.268 |
     Connecticut |  1.860 | -1.359  1.489  0.534 |  1.089  2.396  0.343 |  0.643  2.321  0.120 |
     Delaware    |  1.184 |  0.048  0.002  0.002 |  0.325  0.214  0.075 |  0.719  2.897  0.368 |
     Florida     |  3.070 |  3.013  7.321  0.964 | -0.039  0.003  0.000 |  0.577  1.866  0.035 |
     Georgia     |  2.366 |  1.639  2.167  0.480 | -1.279  3.305  0.292 |  0.342  0.658  0.021 |
     
     Variables
                    Dim.1    ctr   cos2    Dim.2    ctr   cos2    Dim.3    ctr   cos2  
     Murder      |  0.844 28.719  0.712 | -0.416 17.488  0.173 |  0.204 11.644  0.042 |
     Assault     |  0.918 34.010  0.844 | -0.187  3.534  0.035 |  0.160  7.190  0.026 |
     UrbanPop    |  0.438  7.739  0.192 |  0.868 76.179  0.754 |  0.226 14.290  0.051 |
     Rape        |  0.856 29.532  0.732 |  0.166  2.800  0.028 | -0.488 66.876  0.238 |
     > # scree plot 
     > fviz_screeplot(pca_rslt, addlabels = TRUE, ylim = c(0,80))
     ```

     ![scree-plot](https://user-images.githubusercontent.com/291782/164728563-68df7929-d200-427e-a6a8-d8f9c07f96ca.png)

     

     ##### 다. 해석결과

     -   Proportion of Variance (% of var.)는 분산 비율로서 각 주성분이 차지하는 비율을 말하므로 클수록 영향도가 높다는 것을 의미
     -   Cumulative Proportion (Cumulative % of var.)는 분산의 누적합계이며, 누적기여율이 **85% 이상이면 주성분의 수로 결정**할 수 있다.
     -   위의 분석결과에서 누적기여율이 85% 이상인 **Comp.2 의 누적기여율이 87%이므로 4차원을 2차원으로 축소**할 수 있다.

     

     ##### 라. Scree Plot 해석방법

     -   scree plot이란 2차원 그래프에서 x축에는 주성분의 개수, y축에는 분산이나 고유값(eigenvalue)을 두어 **주성분 분석에서 요인의 수를 결정하기 위해 사용**된다. 이 외에도 군집분석 등의 분석에서 최적의 군집 설정 등에 사용할 수 있다. 해석방법은 y축의 값이 수평을 유지하기 전 단계로 주성분 개수를 선택한다.
     -   위의 그래프로 보면 주성분 3개째에서 그래프의 기울기가 줄어드는 형태를 보이므로 한 개를 뺀 **(3-1=2) 2개 주성분이 적합**하다.

     

     ##### 마. biplot  해석방법

     ```R
     fviz_pca_biplot(pca_rslt, reple=FALSE)
     ```

     

     ![pca-biplot](https://user-images.githubusercontent.com/291782/164730920-6e145901-c1a9-485c-b701-29e0364a4b2b.png)

     -   biplot 은 원 변수와 성분 (Comp1, 2) 간의 관계를 그래프로 표현한 것으로 그래프를 통해 각 주성분의 의미를 해석하고 각 객체들의 특성을 파악할 수 있다.
     -   **화살표는 원 변수와 Comp의 상관계수를 의미**하며, **화살표가 Comp와 평행할수록 상관관계가 크므로** 해당 **Comp에 큰 영향**을 끼친다. 그리고 **화살표가 같은 방향으로 인접해 있을수록 같은 주성분으로 생성될 수도 있음**을 알 수 있다.
     -   위의 biplot 에서 Comp1(가로축)을 기준으로 **Murder, Assault, Rape는 같은 방향으로 인접**해 있는 것을 확인할 수 있꼬, Comp2(세로축)을 기준으로 **Urbanpop은 다른 3개와 방향이 다르므로 상관 관계가 낮다.**

     -   여기서 이상치는 **Vermont, West Virginia 등은 변수 방향, 상관관계가 동떨어져 이상치**로 판정될 수 있는 데이터이다.
     -   이상치의 특성을 파악하라는 문제가 출제된다면, 위 결과에서 이상치라고 판단되는 값들 중 West Virginia는 **범죄율과 도시인구비율이 적으므로 '범죄가 없는 시골'이라고 해석하여 분석 결과를 본 미국 시민들이 그 도시로 몰릴 수**도 있다고 판단할 수 있다.

     

     #### 5. 시계열분석 (p.161)

     ##### 가. 개요

     -   시계열 분석에 대한 R 프로그램 분석 결과 중 **자기상관함수(ACF), 편자기상관함수(PACF)에 따른 모형 선택방법에 대한 해석은 정확히 숙지**해야 된다.

     

     ##### 나. 예상문제 (king)

     -   king 데이터는 영국왕 42명의 사망 시 나이 예제의 데이터로 비계절성을 띄는 시계열 자료이며, 트렌드 요소, 불규칙 요소로 구성되어 있다.

     ```R
     > # 시계열분석
     > king <- scan("http://robjhyndman.com/tsdldata/misc/kings.dat", skip=3)
     Read 42 items
     > head(king)
     [1] 60 43 67 50 56 42
     > summary(king)
        Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
       13.00   44.00   56.00   55.29   67.75   86.00 
     > # ts를 이용하여 king 데이터를 시계열 데이터로 변환 후 king.ts 에 저장
     > king.ts <- ts(king)
     > # diff 함수를 활용해 king 데이터를 1차 차분하여 분석에 사용
     > king.ff1 <- diff(king.ts, differences = 1)
     > # acf 함수에서 
     > # lag.max는 최대 lag를 몇까지 나타낼 것인가를 지정하는 옵션
     > # plot은 ACF 그래프를 나타낼 것인가를 묻는 옵션
     > # 분석 결과에서 각 시점의 자기상관계수 값을 확인 가능
     > # ACF 그래프로 절단점과 모형을 선정 가능
     > king.acf <- acf(king.ff1, lag.max = 20, plot=TRUE)
     > king.acf
     
     Autocorrelations of series ‘king.ff1’, by lag
     
          0      1      2      3      4      5      6      7      8      9     10     11     12     13 
      1.000 -0.360 -0.162 -0.050  0.227 -0.042 -0.181  0.095  0.064 -0.116 -0.071  0.206 -0.017 -0.212 
         14     15     16     17     18     19     20 
      0.130  0.114 -0.009 -0.192  0.072  0.113 -0.093 
     ```

     ![ts-acf](https://user-images.githubusercontent.com/291782/164735304-1ee76849-4633-427e-8782-846e0abe3d85.png)

     

     ##### 다. 해석결과

     -   ACF 그래프는 자기상관함수로 계산된 시차 (1, 2, 3..)에서 **자기상관값과 시차 상관그림**을 함께 그린것으로 **이동평균(MA)모형을 선정**하기 위해 사용하는 그래프이다.
     -   ACF 그래프 확인결과, **lag 1인 지점까지는 점선 구간을 초과**하고 나머지는 점선 구간 안에 있으므로 **lag2에서 절단점**을 가지므로 **MA(1) 모형을 생성**할 수 있다.

     

     ##### 라. 예상문제 (king pacf)

     -   PACF를 통한 적합한 ARIMA 모델 결정을 위한 시계열 분석을 시행한 결과이다. 아래 결과를 해석하시오

     ```R
     > # PACF 결과해석
     > king.pacf <- pacf(king.ff1, lag.max = 20, plot=TRUE)
     > king.pacf
     
     Partial autocorrelations of series ‘king.ff1’, by lag
     
          1      2      3      4      5      6      7      8      9     10     11     12     13     14 
     -0.360 -0.335 -0.321  0.005  0.025 -0.144 -0.022 -0.007 -0.143 -0.167  0.065  0.034 -0.161  0.036 
         15     16     17     18     19     20 
      0.066  0.081 -0.005 -0.027 -0.006 -0.037 
     ```

     ![ts-pacf](https://user-images.githubusercontent.com/291782/164737335-25596406-7d9f-453f-bb35-200b79223990.png)

     

     ##### 마. 해석결과

     -   pacf 분석 결과에서 **각 시점의 편자기상관계수**(Partial autocorrelations) 값을 확인할 수 있고 PACF 그래프로 **절단점과 모형을 선정**할 수 있다.
     -   PACF 그래프는 서로 다른 두 시점 사이의 관계를 분석할 때 중간에 존재하는 값을 제외하고 나타낸 상관계수를 구하여 그린것으로 **자기회귀(AR)모형을 선정하기 위해 사용하는 그래프**이다.
     -   PACF 그래프 확인 결과, lag 3 지점까지 점선을 초과하고 나머지는 점선안에 있으므로, **lag 4에서 절단점**을 가지므로 **AR(3) 모형을 생성**할 수 있다.

     

     ##### 바. 예상문제 (king auto.arima)

     -   아래 결과를 해석하시오

         ```R
         > # auto.arima
         > # install.packages("forecast")
         > library(forecast)
         
         # auto.arima 함수 활용 시 자동으로 ARIMA 모형선정 해줌
         > auto.arima(king.ts)
         Series: king.ts 
         ARIMA(0,1,1) 
         
         Coefficients:
                   ma1
               -0.7218
         s.e.   0.1208
         
         sigma^2 = 236.2:  log likelihood = -170.06
         AIC=344.13   AICc=344.44   BIC=347.56
         
         
         > king.arima <- arima(king, order=c(0, 1, 1))
         > king.forecasts <- forecast(king.arima)
         > king.forecasts
            Point Forecast    Lo 80    Hi 80    Lo 95     Hi 95
         43       67.75063 48.29647 87.20479 37.99806  97.50319
         44       67.75063 47.55748 87.94377 36.86788  98.63338
         45       67.75063 46.84460 88.65665 35.77762  99.72363
         46       67.75063 46.15524 89.34601 34.72333 100.77792
         47       67.75063 45.48722 90.01404 33.70168 101.79958
         48       67.75063 44.83866 90.66260 32.70979 102.79146
         49       67.75063 44.20796 91.29330 31.74523 103.75603
         50       67.75063 43.59372 91.90753 30.80583 104.69543
         51       67.75063 42.99472 92.50653 29.88974 105.61152
         52       67.75063 42.40988 93.09138 28.99529 106.50596
         ```

     

     ##### 사. 해석결과

     -   1단계 auto.arima 결과 해석
         -   auto.arima 분석결과 모형이 ARIMA(0, 1, 1)이 선정되었음
         -   시계열 모형식은 Z<sub>t</sub> = &alpha;<sub>t</sub> + 0.7218 &alpha;<sub>t-1</sub>  이다.
     -   2단계 : forecast 함수 결과 예측
         -   ARIMA(0, 1, 1) 모형 예측했을 때, 43번 ~ 52번째 왕의 사망 시 나이 예측결과는 67.75살로 추정
         -   신뢰구간은 80 ~ 95% 사이
         -   h 인자는 예측하고자 하는 개수를 'h=5' 처럼 5개로 정할 수 있다. ```forecast(king.arima, h=5)```
     -   최종적으로 분석 결과를 종합하면
         -   ACF 그래프를 통해 MA(1) 모형 생성
         -   PCAF 그래프를 통해 **AR(3) 모형** 생성
         -   auto.arima 활용하여 **ARIMA(0, 1, 1) 모형 선정**
         -   ARIMA(0, 1, 1)로 예측 결과, **43 ~ 52번째 왕의 사망 시 나이는 67.65살로 예측한다는 결론을 도출**

     

### 2절  정형 데이터마이닝

#### 1. 로지스틱 회귀분석 (p.165)

##### 가. 개요

-   유의한 설명변수 파악, 회귀 모형의 유의함, 결정 계수 해석, 모형 수식 작성, 오즈비를 이용한 해석 등에 대한 해석은 정확히 숙지해야 함



##### 나. 예상문제 (Default)

-   10,000명의 신용캌드 고객의 체납 여부 (default)와 학생여부(student), 카드잔고(balance), 연봉(income)을 포함하고 있다. 체납 여부를 예측하기 위해 로지스틱 회귀분석을 실시한다. 아래 결과를 해석하시오

```R
> # 로지스틱 회귀분석
> # default 데이터
> # install.packages("ISLR") # Credit Card Default dataset install
> library(ISLR)
> summary(step(glm(default ~ 1, data=Default, family = binomial),
+              scope = list(lower=~1, upper=~student + balance + income),
+              direction="both"))
Start:  AIC=2922.65
default ~ 1

          Df Deviance    AIC
+ balance  1   1596.5 1600.5
+ student  1   2908.7 2912.7
+ income   1   2916.7 2920.7
<none>         2920.7 2922.7

Step:  AIC=1600.45
default ~ balance

          Df Deviance    AIC
+ student  1   1571.7 1577.7
+ income   1   1579.0 1585.0
<none>         1596.5 1600.5
- balance  1   2920.7 2922.7

Step:  AIC=1577.68
default ~ balance + student

          Df Deviance    AIC
<none>         1571.7 1577.7
+ income   1   1571.5 1579.5
- student  1   1596.5 1600.5
- balance  1   2908.7 2912.7

Call:
glm(formula = default ~ balance + student, family = binomial, 
    data = Default)

Deviance Residuals: 
    Min       1Q   Median       3Q      Max  
-2.4578  -0.1422  -0.0559  -0.0203   3.7435  

Coefficients:
              Estimate Std. Error z value Pr(>|z|)    
(Intercept) -1.075e+01  3.692e-01 -29.116  < 2e-16 ***
balance      5.738e-03  2.318e-04  24.750  < 2e-16 ***
studentYes  -7.149e-01  1.475e-01  -4.846 1.26e-06 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

(Dispersion parameter for binomial family taken to be 1)

    Null deviance: 2920.6  on 9999  degrees of freedom
Residual deviance: 1571.7  on 9997  degrees of freedom
AIC: 1577.7

Number of Fisher Scoring iterations: 8
```

-   해석방법

    -   벌점화 방식(AIC)의 변수선택법을 활용한 로지스틱 회귀분석은 아래와 같은 단계로 분석할 수 있다.
    -   1단계 : 변수선택법을 결정하고, 초기 모형을 세팅
    -   2단계 : 선택된 최적 모형의 AIC를 계산
    -   3단계 : 선택된 모형에서 변수를 추가 / 삭제 할 경우의 각 모형에서 AIC를 계산
    -   4단계 : 각 모형에서 최소의 AIC 모형을 선택하여 최적 모형으로 선정
    -   5단계 : 2단계에서 4단계를 반복하고 AIC가 더 이상 줄어들지 않을 때 최종모형을 최적 모형으로 선정
    -   6단계 : 각 변수의 계수에 대한 가설검정 실시

-   해석결과

    -   위 분석결과는 6단계 해석이 모두 가능. 분석에 앞서 모형의 구조는 formula를 통해 확인 할 수 있고, step 함수를 통해 종속변수에 대해 설명변수가 없을 경우부터 모든 설명변수가 포함될 때의 회귀모형을 비교해 최적의 회귀방정식을 도출할 수 있다. 또, direction에서 'both'는 단계적 선택법, 'forward'는 전진선택법, 'backward'는 후진제거법을 의미한다.

    -   Default를 종속변수로 설정, 설명변수가 없을 때부터 최대 모든 설명변수가 포함된 회귀식까지 설정하여 최적의 회귀식을 도출

    -   1단계 : 변수 선택법을 결정하고, 초기 모형을 설정한다.

        -   위의 분석결과에서 direction이 both로 설정되어 변수선택법을 단계적 선택법으로 선정
        -   초기 모형은 default ~ 1로 설명변수가 하나도 없는 상태에서 부터 모두 있는 것까지를 비교를 의미

    -   2단계 : 선택된 최적 모형의 AIC를 계산

        -   분석 결과에서 시작 모형은 **default~1이 최적모형**으로 설정되어 있으며 start에서 **AIC 값이 2922.65**로 계산

    -   3단계 : 선택된 모형에서 변수를 추가 / 삭제 할 경우의 각 모형의 AIC를 계산한다.

        -   default~1 모형에 대해 설명변수 3개에 대한 각각의 AIC 값을 계산하여 자유도 등과 함께 나타낸다. **balance의 AIC 값이 1600.5, student 의 AIC 값은 2912.7, income의 AIC 값은 2920.7**로 나타나있다.

    -   4단계 : 각 모형에서 최소의 AIC 모형을 선택하여 최적 모형으로 선정한다.

        -   계산된 AIC 값을 비교하여 가장 작은 설명변수인 **balance를 추가하여 최적 모형으로 선정**한다.

    -   5단계 : 2~4단계를 반복하여 AIC가 더 이상 줄어들지 않을 때 최종모형을 최적의 모형으로 선정한다

        -   위의 과정을 반복하여 default ~ balance + student이 최적의 모형으로 선정되고 마지막 **step 에서 AIC가 1577.68로 계산되고 추가되지 않은 설명변수 income의 AIC 값이 1579.5**로 나타나 해당 변수를 모형에 추가하지 않고 **최적의 모형을 default~balance + student로 선정**했다.

    -   6단계 : 로지스틱 회귀분석에 활용된 각 설명변수들의 계수들에 대한 통계적 타당성을 가설 검정한다.

        -   첫 번째 설명변수인 balance에 대한 통계적 가설검정을 실시한다.
            -   귀무가설 (H<sub>0</sub>) : balance = 0
            -   대립가설 (H<sub>1</sub>) : balance $\neq$ 0
            -   z-통계량은 24.75 이며 p-value 값이 < 2e-16 이므로 귀무가설의 기각역인 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 책택하게 된다ㅏ. 그러므로 추정된 회귀 모형의 첫 번째 설명변수인 balance는 통계적으로 유의함을 알 수 있다.
            -   두 번째 설명변수인 studentYes의 경우 , z-통계량은 -4.846 이며 p-value 값이  1.26e-06 이므로 0.05보다 작게 나타남에 따라 유의수준 5%하에서 대립가설을 채택하게 된다. 그러므로 추정된 회귀모형의 두 번째 설명변수인 studentYes는 통계적으로 유의함을 알수 있다. 그러므로 추정된 회귀모형의 모든 설명변수는 통계적으로 유의함을 알 수 있다.

    -   최종적으로 로지스틱 회귀분석 결과를 종합해 보면 추정된 로지스틱 회귀식은

        $P(X) = \dfrac {1} {1 + exp(-(-10.75 + 0.005738*balance - 0.7149*studentYes))}$

        또 다른 설명변수의 조건이 동일할 떄, studentYes이 1 증가할수록 졸업할 확률이 exp(-0.715) = 0.49배 증가, 즉 학생일수록 체납확률이 낮아딘다고 할 수 있다. 회귀식을 통해 balance가 증가할수록 default는 증가하고, studentYes가 증가할수록 default는 감소한다. default에 가장 영향을 많이 끼치는 변수는 studentYes 이다.

##### 다. 예상문제 (Crabs)

- crabs 데이터는 참게 중 암참게에 붙어사는 숫참게에 대한 데이터이다. 암참게가 부수체를 갖는지 여부에 영향을 미치는 요인을 조사했으며, 암참게가 한 마리 이상의 부수체를 가지면 y=1로 정의, 그렇지 않으면 y=0으로 정의했다. 아래는 부수체(y) 예측에 너비(width)를 이용한 로지스틱회귀모형을 적합했다. 아래의 물음에 답하시오

    ```R
    # > install.packages("glmbb")
    > library(glmbb)
    > head(crabs)
       color spine width satell weight y
    1 medium   bad  28.3      8   3050 1
    2   dark   bad  22.5      0   1550 0
    3  light  good  26.0      9   2300 1
    4   dark   bad  24.8      0   2100 0
    5   dark   bad  26.0      4   2600 1
    6 medium   bad  23.8      0   2100 0
    
    > glm(formula = crabs$y~crabs$width, family=binomial, data=crabs)
    
    Call:  glm(formula = crabs$y ~ crabs$width, family = binomial, data = crabs)
    
    Coefficients:
    (Intercept)  crabs$width  
       -12.3508       0.4972  
    
    Degrees of Freedom: 172 Total (i.e. Null);  171 Residual
    Null Deviance:	    225.8 
    Residual Deviance: 194.5 	AIC: 198.5
    ```

- 해석결과

    1. 너비 x에 대한 부수체의 예측 확률을 구하는 식을 작성하시오

    - 예측확률을 구하는 식은 로지스틱 회귀식을 작성하면 됨
    - 회귀식은 $\dfrac {1} {1 + exp^{12.3508 - 0.4972width}}$ 이다.

    2. 로지스틱 회귀모형은 오즈 (odds)를 이용하여 해석가능. x가 한 단위 증가함에 따라 오즈는 (a) 증가한다. 그러므로 암참게 자료에 대하여 부수체의 오즈는 너비가 1cm 증가함에 따라 (a)=1.64배 증가하는 것으로 추정된다.
        - x가 한 단위 증가함에 따라 오즈는 exp(0.4972) 만큼 증가한다. 또한 x+1에서의 오즈는 x일때의 오즈와 동일하므로 exp(0.4972) 만큼 증가한다. 그러므로 1cm 증가함에 따라 exp(0.4972)=1.64배 증가
    3. 평균 너비값이 x=26.3인 경우에는 부수체의 확률이 0.671로 예측되고 오즈는 (b)=2.07이다. x=27.3(=26.3+1) 일 때의 예측확률은 0.773이고 이데 대한 오즈는 (c)=3.40 임을 확인할 수 있다.
        - x=26.3 일때 (1)에서 구한 로지스틱 회귀식으로 확률을 구하면 0.671이 나타나게 되고 오즈는 $\dfrac {0.671} {1-0.671} = 2.07$로 나타난다. 또한 x=27.3 일 때의 예측확률도 (1)에서 구한 로지스틱 회귀식으로 확률을 구하면 0.773이 나타나게 되고 오즈는 $\dfrac {0.773} {1-0.773} = 3.40$으로 나타난다.



#### 2. 의사결정나무 (p.169)

##### 가. 개요

-   의사결정나무 모델링 결과, 교차타당성오차에 대한 해석을 정확히 숙지



##### 나. 예상문제 (iris)

-   iris 데이터 셋

    ```R
    > library(rpart)
    > head(iris)
      Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    1          5.1         3.5          1.4         0.2  setosa
    2          4.9         3.0          1.4         0.2  setosa
    3          4.7         3.2          1.3         0.2  setosa
    4          4.6         3.1          1.5         0.2  setosa
    5          5.0         3.6          1.4         0.2  setosa
    6          5.4         3.9          1.7         0.4  setosa
    
    > tree <- rpart(Species~., data = iris)
    > tree
    n= 150 
    
    node), split, n, loss, yval, (yprob)
          * denotes terminal node
    
    1) root 150 100 setosa (0.33333333 0.33333333 0.33333333)  
      2) Petal.Length< 2.45 50   0 setosa (1.00000000 0.00000000 0.00000000) *
      3) Petal.Length>=2.45 100  50 versicolor (0.00000000 0.50000000 0.50000000)  
        6) Petal.Width< 1.75 54   5 versicolor (0.00000000 0.90740741 0.09259259) *
        7) Petal.Width>=1.75 46   1 virginica (0.00000000 0.02173913 0.97826087) *
    
    > # install.packages("rpart.plot")
    > library(rpart.plot)
    > prp(tree, type=4, extra=2)
    ```

-   ![dt-iris](https://user-images.githubusercontent.com/291782/165328365-c87729fd-0b86-4d39-b34f-bbfb2bbc0461.png)



-   해석방법
    -   1단계: rpart 함수 설명
    -   2단계 : rpart 결과에서 조건에 따른 분류에 대해 파악
    -   3단계 : 시각화 결과에 대하여 해석하고 인사이트 도출
-   해석결과
    -   1단계 : 의사결정나무 다양한 패키지 중 rpart 패키지에 내장되어 있는 rpart 함수를 사용한다.  rpart 패키지는 CART (classification and Regression Tree)의 아이디어를 구현한 패키지이며, rpart(formula, data)의 기본 형태로 의사결정나무 모형을 구축할 수 있다. 또, rpart 함수 내에 모형의 적합을 위해 control 인자의 rpart.control 등의 명령어를 추가로 활용할 수 있다.
    -   2단계 : 위의 결과에서 n=150은 데이터의 개수가 150개를 의미하고 1) root 부터 해석을 진행한다. 총 150개의 데이터 중 50개를 setosa로 분류하는데, 조건은 **2) Petal.Length < 2.45의 경우 모두 setosa로 분류**한다. 또, 100개 중 50개를 versicolor로 분류하는데 **Petal.Length >= 2.45 이며 Petal.Width < 1.75인 54개를 versicolor로 분류하고, Petal.Length >= 2.45이며 Petal.Width >= 1.75인 46개를 virginica로 분류**했다.
    -   3단계 : rpart 함수 결과와 동일하지만, 시각화 결과만 보여주고 해석 문제 출제될 수 있으니 숙지 필요함. 그래프를 보면 **150개 중 50개는 Petal.Length < 2.5일 때, setosa 분류, Petal.Length >= 2.5이고, Petal.Width < 1.8인 54개 중 49개는 versicolor로, Petal.Width >= 1.8 인 46개 중 45개를 virginica로 분류**했다.
    -   만약 3가지 꽃 종류 중 versicolor 의 판매가가 높다는 정보가 있다면, 도출된 결과를 바탕으로 '**Petal.Length >= 2.5 , Petal.Width < 1.8인 꽃만 추출해 판매한다**' 고 인사이트를 제시해 낼 수 있다.



-   예상문제
    -   아래 결과는 위의 의사결정나무 모형의 교차타당성오차에 대한 결과와 그래프이다. 아래의 결과를 해석하시오

 ```R
> tree$cptable
    CP nsplit rel error xerror       xstd
1 0.50      0      1.00   1.11 0.05372150
2 0.44      1      0.50   0.56 0.05923963
3 0.01      2      0.06   0.10 0.03055050

> opt <- which.min(tree$cptable[, "xerror"])
> cp <- tree$cptable[opt, "CP"]
> prune.c <- prune(tree, cp=cp)
> plotcp(tree)
 ```

![plotcp](https://user-images.githubusercontent.com/291782/165335460-023406d4-59fe-4cc6-bd0c-9cb062c1f509.png)



-   해석방법
    -   1단계 : 함수에 포함된 기능에 대해 설명
    -   2단계 : 분석결과가 의미하는 바를 파악
    -   3단계 : 시각화 결과에 대하여 해석하고 인사이트를 도출
-   해석결과 (p.172)
    -   1단계 : 



