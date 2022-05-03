# ADP 모의고사

## 모의고사 1회

### 1과목 데이터의 이해

#### 1. 데이터베이스의 특징 4가지

-   통합된 데이터, 저장된 데이터, 공용 데이터, 운영 데이터

#### 4.  빅데이터 분석에 경제성을 제공해 준 기술

-   클라우드 컴퓨팅의 보편화는 처리 비용을 획기적으로 낮춰 경제성을 제공했다.

#### 7. 사물인터넷의 의미로 가장 적절한 것

-   모든 것의 데이터화(datafication)



### 2과목 데이터 처리 기술의 이해

#### 12. 데이터베이스 클러스터에 대한 설명

-   MySQL 클러스터는 비공유형으로서 메모리(최근 디스크도 제공) 기반 데이터베이스의 클러스터링을 지원

#### 13.  ETL에 대한 설명 

-   ETL은 배치 프로세스 중심이며, MPP(Massive Parallel Processing)을 지원한다.

#### 14. VMWare 관련 메모리 가상화 기법에 대한 설명

-   Transparent page sharing : 하나의 물리저인 머신에 여러 개의 가상머신이 운영되는 경우, 각 가상머신에 할당된 메모리 중 동일한 내용을 담고 있는 페이지는 물리적인 메모리 영역에 하나만 존재시키고 모든 가상 머신이 공유하도록 하는 것

#### 15. SQL on 하둡

-   하둡 프레임워크의 맵리듀스를 이용하지 않고, 새로운 분산 처리 모델과 프레임워크를 기반으로 구현되어 있다.
-   SQL on 하둡의 한 종류인 샤크(Shark)는 인메모리 기반의 대용량 데이터웨어하우스 시스템이다.
-   실시간 SQL 질의 분석 기술이다
-   클라우데라 임팔라, 아파치 타조는 대표적인 상용 SQL on 하둡 솔루션이다.



#### 16. CDC (Change Data Capture)의 구현 기법에 관한 설명

-   Log scanner on database : 로그에 대한 스캐닝 및 변경 내역에 대한 해석을 통해 CDC 메커니즘을 구현하는 기법으로 데이터베이스 스키마의 변경을 필요로 하진 않는다.
-   Version on Rows : 데이터 변경 여부에 대해 True/False의 논리값으로 표현하는 컬럼을 두는 기법으로, 레코드에 대한 변경 여부는 사람이 직접 판단할 수 없다.
-   Status on Rows : 레코드에 대한 변경 여부를 사람이 직접 판단할 수 있도록 유보하는 업무 규칙을 정할 수 있다.
-   Triggers on Tables : 데이터베이스 트리거를 활용해 사전에 등록된 다수의 대상 시스템에 변경 데이터를 배포하는 형태로 CDC를 구현하는 기법이다.
-   Time / Version / Status on Rows : 정교한 쿼리 생성에 활용할 수 있다.



#### 17. HBase는 하둡 분산파일 시스템을 사용하며, SQL을 지원하지 않는다.



#### 19. MapReduce 절차 : Input > Split > Map > Combine > Shuffle&Sort > Reduce > Output



### 3과목 데이터 분석 기획

#### 23. 하향식 접근법 : 문제탐색 > 문제정의 > 해결방안 탐색 > 타당성 검토로 전개

#### 24. 고객니즈 변화에 대항하는 것 : 고객, 채널, 영향자들에 의해 진행

#### 26. 분석 프로젝트 영역별 주요 관리 항목

-   범위, 시간, 원가, 품질, 통합, 조달, 자원, 리스트, 의사소통, 이해관계자 등

#### 27. 분석과제 관리 프로세스에 대한 설명

-   분석과제 중에 발생된 시사점과 분석 결과물이 풀(pool)로 관리되고 공유
-   확정된 분석과제는 풀(pool)로 관리하지 않는다.



#### 28. 데이터 분석 3가지 조직 구조

![anal-part](https://user-images.githubusercontent.com/291782/161255029-34d00daa-7141-43ba-a159-b2745a087e2f.png)

-   집중구조, 기능구조, 분산구조



#### 29. CRISP-DM 방법론의 모델링 단계에서 수행하는 태스크(task)는?

-   모델링 기법 선택, 모델 테스트 계획 설계, 모델 작성, 모델 평가


### 4과목 데이터 분석

#### 34. 모분산의 추론에 대한 설명

-   F-분포 : 이표본에 의한 분산비 검정은 두 표본의 **분산이 동일한지를 비교**하는 검정
-   모분산이 추론의 대상이 되는 경우는 모집단의 변동성 또는 퍼짐의 정도에 관심이 있을 때이다.
-   모집단이 정규분포를 따르지 않더라도 중심극한 정리를 통해 정규 모집단으로부터의 모분산에 대한 검정을 유사하게 시행할 수 있다.
-   X<sup>2</sup>(카이제곱) : 평균모집단에서 n개를 단순임의 추출한 **표본의 분산**은 자유도가 n-1인 카이제곱 분포를 따른다. **두 집단간의 동질성 검정에 활용**
-   t-분포 : **두 집단의 평균이 동일**한지를 알고자 할 때 검정통계량으로 활용



#### 37. 이산형 확률분포, 연속형 확률분포

##### 가. 이산형 확률분포

- 확률 변수가 가질 수 있는 값이 명확하고 셀 수 있는 경우의 분포, 확률값은 확률질량함수를 이용하여 계산

> $P(X_i) > 0$      $  i=1,2,...,k$      $\displaystyle \sum_{i=1}^kP(X_i)=1$

-   이산형 확류변수 예시 : 동전 2개를 던져서 앞/뒷면이 나오는 경우의 수(H:앞, T:뒤)

    | 표본공간(&Omega;) | HH(사건) | HT   | TH   | TT   | 합계 |
    | ----------------- | -------- | ---- | ---- | ---- | ---- |
    | P(x)              | 1/4      | 1/4  | 1/4  | 1/4  | 1    |

    

###### 1) 베르누이  확률분포(Bernoulli distribution)

- 결과가 2개만 나오는 경우 (ex. 동전 던지기, 시험의 합/불합격 등)

> $P(X=x)=p^x(1-p)^{1-x}$  (x=1 or 0), E(x) = p,  var(x)=p(1-p)
>
> 예) 메이저리거인 추추가 안타를 칠 확률은 베르누이 분포를 따름. (안타를 치는 사건을 x=1이라고 할 때 안타를 칠 확률은 타율로 적용 가능)



###### 2) 이항분포(Binomial distribution)

- 베르누이 시행을 n번 반복했을 때 k번 성공할 확률
- $P(X = k) = _nC_kP^k(1-p)^{n-k}, \quad  _nC_k = \dfrac {n!} {k!(n-k)!}$
- 한 축구 선수가 페널티킥을 차면 5번 중 4번은 성공한다고 한다. 그럼 이 선수가 10번의 페널티킥을 차서 7번 성공할 확률은?
- 5번 중 4번 성공하기에 성공확률은 4/5 = 0.8, 실패확률은 1-0.8 = 0.2
- $이항분포 = \begin{pmatrix} n \\ x \end{pmatrix} p^x(1-p)^{n-x} =  \begin{pmatrix} 10 \\ 7 \end{pmatrix} 0.8^70.2^3$
- $ = \dfrac {10!} {7! \times 3!} 0.8^7 0.2^3 = 0.2013 = 20.13\%$



###### 3) 기하분포(Geometric distribution)

- 성공확률이 p인 베르누이 시행에서 첫번째 성공이 있기까지 x번 실패할 확률
- $p(x) = p(1-p)^{x-1}$
- 어느 야구선수가 홈런을 칠 확률은 0.05라고한다. 이 선수가 6번째 타석에서 홈런을 칠 확률은?
- 성공확률 p=0.05, 실패확률은 1 - 0.05 = 0.95, 6번째 타석에서 성공할 확률이기에 x-1 = 6-1
- $p(1 - p)^{x-1} = 0.05 \times 0.95^{6-1} = 0.0387 = 3.87\%$



###### 4) 다항분포(Multinomial distribution)

- 이항분포를 확장한 것으로 세가지 이상의 결과를 가지는 반복 시행에서 발생하는 확률 분포

- 각 상황의 확률과 각 상황의 횟수를 잘 파악해야 함

- $p(x) = \dfrac {n!} {x_1!x_2! ...x_k!}p1^{x_1}p_2^{x_2}... p_k^{x_k} $

- 국내 인터넷 포털 사이트의 점유율은 아래와 같다.  12명을 임의로 뽑아 사용 사이트를 알아보았을 때, 네이버 7명, 구글 3명, 다음과 ZUM이 각 1명, 기타는 0명이 사용할 확률을 구하시오

    네이버 : 61%, 구글 : 30%, 다음 : 7%, ZUM: 1%, 기타 : 1%

- $\dfrac {12!} {7! \times 3! \times 1! \times 1! \times 0!} \times 0.61^7 \times 0.3^3 \times 0.07^1 \times 0.01^1 \times 0.01^0 = 0.0094$

    

    

###### 5) 포아송분포 (Poisson distribution)

- 시간과 공간 내에서 발생하는 사건의 발생횟수에 대한 확률분포 (예. 가게에 손님이 1시간에 20명씩 방문한다고 할 때, 10분에 손님이 5명씩 방문할 확률)
- 확률을 구하기 위해서는 **평균(&lambda;)과 발생횟수(x)**를 잘 파악해야 함
- $p(x) = \dfrac {e^{-\lambda} \lambda^x} {x!} , \quad e=2.718281...$
- 전공 책 5페이지를 검사했는데, 오타가 총 10개가 발견되었다고 한다. 그럼 이 책에서 어느 한 페이지를 검사하였을 때, 오타가 3개 나올 확률을 구하시오?
- 해설) 포아송 분포는 평균을 잘 구해야함. 문제에 말장난이 섞여 있음. 일단 5페이지에 총 10개의 오타이므로, 1페이지에 평균 2개의 오타가 발견된 셈. 그래서 평균 (&lambda;)=2 이다. 그리고 발생횟수 x=3 이므로...
- $\dfrac {2.718281^{-2} \times 2^3} {3!} = 0.1804$



##### 나. 연속형 확률분포

- 확률 변수가 가질 수 있는 값이 연속적인 실수여서 셀 수 없는 경우의 분포이며, 확률값은 확률밀도함수를 이용하여 계산한다.

###### 1) 균일분포 (일양분포, Uniform distribution)

- 모든 확률변수 X가 균일한 확률을 가지는 확률분포 (다트의 확률분포)



###### 2) 정규분포 (Normal distribution)

- 평균이 &mu;이고, 표준편차가 &sigma;인 X의 확률밀도함수
- 표준편차가 클 경우 퍼져보이는 그래프가 나타난다.



###### 3) 지수분포 (Exponential distribution)

- 어떤 사건이 발생할 때까지 경과한 시간에 대한 연속확률분포이다. (예. 전자렌지의 수명시간, 은행에 고객이 내방하는데 걸리는 시간, 정류소에서 버스가 올 때까지의 시간)



###### 4) t-분포 (t-distiribution)

- 표준정규분포와 같이 평균이 0을 중심으로 좌우가 동일한 분포를 따른다.
- 표본의 크기가 적을때는 표준정규분포를 위에서 눌러 놓은 것과 같은 형태를 보이지만 표본이 커져서(30개 이상) 자유도가 증가하면 표준정규분포와 거의 같은 분포가 된다.
- 데이터가 연속형일 경우 활용한다.
- **두 집단의 평균이 동일**한지 알고자 할 때 검정통계량으로 활용된다.
- 표준정규분포와 같이 평균 값이 0이며, 자유도에 따라 분포의 모양이 변화한다.
- 자유도가 30미만인 경우, 표준정규분포에 비해 양쪽 끝이 평평하고 두터운 꼬리 모양을 가진다.



###### 5) X<sup>2</sup>-분포 (X<sup>2</sup>-distribution) (카이제곱분포)

- 모평균과 모분산이 알려지지 않은 모집단의 모분산에 대한 가설 검정에 사용되는 분포이다.
- **두 집단 간의 동질성 검정에 활용**된다.
- 확률변수 X가 표준정규분포(Z)를 따를 때, 자유도가 k인 카이제곱분포를 따른다. 자유도는 표본 자료 중 모집단에 대한 정보를 주는 독립적인 표본 자료의 수와 같으며, 분할표에서의 행과 열의 개수를 통해 구할 수 있다. (자유도(df) = (r-1)(c-1), r=행의 개수, c=열의 개수)



###### 6) F-분포 (F-distribution)

- **두 집단간 분산의 동일성 검정**에 사용되는 검정 통계량의 분포이다.
- 확률변수는 항상 양의 값만을 갖고 카이제곱분포와 달리 자유도를 2개 가지고 있으며 자유도가 커질수록 정규분포에 가까워진다.



### 5과목 데이터 시각화

#### 71. 시각화 인사이트 프로세스는?

-   탐색(1단계) > 분석(2단계) > 활용(3단계)

#### 72. 데이터클라우드(워들) 사용하는 단계에 대한 설명

-   데이터클라우드는 탐색 단계에서 비정형 데이터(텍스트 데이터) 측정값에서 관계를 탐색하기 위해 사용하는 시각화이다.



#### 75. 벤프라이(Ben Fry) 7단계

-   정보획득, 분석(분해), 선별, 마이닝, 표현, 정제, 상호작용



#### 76. facet_grid : 집단별 구분

-   facet_grid(Type ~.) # 가로 (라벨이 오른쪽에 존재)
-   facet_grid(. ~ Type) # 세로 (라벨이 위쪽에 존재)
-   facet_grid(Type ~ Origin) # Type은 오른쪽, Origin은 윗쪽에 라벨 존재



#### 78. D3 라이브러리

-   d3.layout.pie() : 이렇게 만드는건 파이 차트만
-   d3.scale.linear() : 막대차트, 스캐터플롯



#### 80. 시각화를 위한 그래픽 디자인 기본 원리

1.   아이소타이프 (ISOTYPE, International System Of TYpographic Picture Education)

     -   많은 양의 데이터를 쉽게 지각할 수 있도록 도와주는 시각표현 방법

     -   정보, 자료, 개념, 의미 등을 나타내기 위해 문자와 숫자 대신 상징적 도형이나 정해진 기호를 조합해 시각적이고 집접적으로 나타내는 방식

     -   ![isotype](https://user-images.githubusercontent.com/291782/158065420-24a0c418-cf69-453e-879c-1b9f758b8b1f.png)

2.   타이포그래피
     -   가장 어려운 일이 서체를 선택하는 것

