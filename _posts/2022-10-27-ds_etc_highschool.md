---
title: "[기타] 고교학생들의 조직 몰입도에 대한 분석"
date: 2022-11-14 12:38:14 +0900
categories: [Data Related, Data-Etc]
tags: [regression]     # TAG names should always be lowercase

author: rouxist

published: false
---
# 주제 선정 과정

&nbsp;&nbsp;3학년의 시작과 동시에 회귀분석으로 분석해볼 이슈가 없을지 머리를 굴리고 있었다. 시간이 흘러 중간고사를 끝내고 찾아온 5월의 연휴, 뜬금없지만 비즈니스 영어 교과의 발표를 준비하면서 조직 몰입(Organizational Commitment)에 대해 조사했다. 관련해서 찾아보던 위키피디아 페이지에 주석이 달려있길래 보게 된 논문 :  
> [리더십 스타일이 조직시민행동에 미치는 영향 : 조직몰입의 매개효과를 중심으로 (김용환, 2014)](http://www.riss.kr/search/detail/DetailView.do?p_mat_type=be54d9b8bc7cdb09&control_no=8ab430d3363221fbffe0bdc3ef48d419&keyword=리더십%20스타일이%20조직시민행동에%20미치는%20영향%20%20%20조직몰입의%20매개효과를%20중심으로)

RISS에서 찾아서 봤는데 지금은 안보인다(..) . 
중소기업 근무자들을 대상으로 구성원들의 조직시민행동에 미치는 요인을 추정하고 검증하는 내용이었다. 일단 이걸 보고, 조직몰입도를 종속변수로 하는 실험을 설계해볼 수 있겠다는 생각이 들었다. 그리고 더 찾아보다가 알게된 두 번째 자료 :  
> [조직몰입 구성개념의 개념화와 타당화: 은행의 정규직 종사자를 중심으로 (안정원, 이순묵)](http://www.riss.kr/search/detail/DetailView.do?p_mat_type=1a0202e37d52c72d&control_no=ab43267adf11f4b84884a65323211ff0&keyword=%EC%A1%B0%EC%A7%81%EB%AA%B0%EC%9E%85%20%EA%B5%AC%EC%84%B1%EA%B0%9C%EB%85%90%EC%9D%98%20%EA%B0%9C%EB%85%90%ED%99%94%EC%99%80%20%ED%83%80%EB%8B%B9%ED%99%94%20%20%EC%9D%80%ED%96%89%EC%9D%98%20%EC%A0%95%EA%B7%9C%EC%A7%81%20%EC%A2%85%EC%82%AC%EC%9E%90%EB%A5%BC%20%EC%A4%91%EC%8B%AC%EC%9C%BC%EB%A1%9C)

비슷하게 조직몰입을 측정하는 내용이 포함된 연구였는데, 이 자료에서는 조직몰입을 측정하기 위해 구체적으로 어떤 질문들을 사용했는지를 알 수 있었기에, 이걸 활용하면 확실히 실험을 설계할 수 있겠다고 생각했다. 그래서 이때부터 종속변수가 조직몰입도인 주제를 구상했다. 그 결과 고른 주제는..  
<div style="text-align: center;font-weight: bold;">
  '학생들이 학교를 좋아하지 않는 이유를 찾아보자'
</div>
이에 대해 구체화를 시작했다.
<hr/>

# 가설 설정

&nbsp;&nbsp;위 주제를 바탕으로 세운 가설은 다음과 같다.  

1. 학교의 복지는 학생의 조직몰입도에 정(+)의 영향을 미칠 것이다

2. 학교의 교육방식은 학생의 조직몰입도에 정(+)의 영향을 미칠 것이다

3. 학교의 시스템은 학생의 조직몰입도에 정(+)의 영향을 미칠 것이다
 

# 탐구 설계

&nbsp;&nbsp;나의 설계와 직접적으로 유사한 통계자료는 있을리가 만무하다 생각하여 1차 자료를 수집하기로 했고, 설문지법을 사용했다. 설문 문항 구성은 :  
![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/1.png){: width="500" height="150"}  

+실행 후 코멘트 :

&nbsp;&nbsp;위에서부터 5개는 조직몰입도를 측정하기 위한 문항들이다. 상기한 연구(조직몰입 구성개념의 개념화와 타당화: 은행의 정규직 종사자를 중심으로)에서 제시된 질문지의 내용을 참고했고, 첫번째 질문의 원작자는 Jaros(2007), 나머지 네 개 질문의 원작자는 Allen&Meyer(1990)라고 한다.
&nbsp;&nbsp;그 외 나머지 문항들은 직접 제작했는데,  
6~9번째는 **학생에 대한 복지**의 영향을 측정하기 위해 조작적으로 정의한 질문들이다. (**Comm**itment)  
10~13번째는 **학교의 교육**의 영향을 측정하기 위해 조작적으로 정의한 질문들이다. (**Educ**ation)  
14~17번째는 **제도적 요소**의 영향을 측정하기 위해 조작적으로 정의한 질문들이다. (**Syst**em)  
 
모든 질문들은 1로 갈 수록 '매우 그렇지 않다', 5로 갈 수록 '매우 그렇다'에 해당하는 리커트 척도(Likert scale)를 사용했다.
 
다음은 수집한 자료를 분석할 방법에 대해 구상했는데,  
1. 가장 먼저 떠올린 것은 p value를 사용한 검정이다. 로지스틱 회귀분석을 실시하고 산출되는 p value를 사용해서 유의미한 관계가 있는 변수들을 걸러내 보기로 했다.  
2. 그리고 조사한 자료 중 아무 독립변수나 뽑아서 조직 몰입도와 비교해볼 수 있는 산점도 그래프도 그려보기로 했다.  
 
# 표본 선정

&nbsp;&nbsp;가설을 설정하기 전, 현실적으로 내가 조사할 수 있는 표본을 정한 후에 그들에게 적합한 가설을 세우는 것이 나을 것 같아서 가장 먼저 조사 대상을 정했다. 당초 계획한 조사범위는 18기 학생 전체였는데, 그 중 2반 학생들의 경우 수업시간을 통해 종이 설문지로 조사하고, 그 외에는 구글 폼을 쓸 계획이었다. 그래서 일단 200여명의 특성들을 모두 생각하며 탐구를 설계하기 시작했다.
&nbsp;그런데, 종이 설문지를 돌려보고 2반만 조사해야겠다고 생각을 바꿨다(..) 반마다 분위기가 다르기도 하고, 어떤 친구에게 구글 폼으로는 조사가 잘 안될거라는 말도 듣고 나서 그냥 2반 표본만을 사용하는 걸로 정했다. (완벽히 **편의 표본 추출**이 되었다.) 
 

# 분석

&nbsp;&nbsp;7월 2일, 기말고사를 끝내고 본격적으로 분석을 시작했다.
먼저 Numbers를 사용해 설문지를 컴퓨터 파일로 옮겼다.  
![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/2.png){: width="500" height="150"}  
**조직몰입도** 5개는 Comm_1~5  
**학생에 대한 복지** 4개는 Welf_1~4  
**학교의 교육** 4개는 Educ_1~4  
**제도적 요소** 4개는 Syst_1~4  
와 같이 변환했고  
<U>질문의 좋고 나쁨이 반대인</U> 질문들은 1~5를 반대로 바꿨다. 그리고 각 분야별 평균을 구해서 Comm_avg, Welf_avg, Educ_avg, Syst_avg를 추가했다. (예 : Welf_Avg = (Welf_1 + Welf_2 + Welf_ + Welf_4)/4) 이 작업은 엑셀 함수를 썼다.  
정규화는 거치지 않았다. 범위가 다 1~5 이하의 자연수밖에 안돼서..  
이렇게 만든 데이터셋을 파이썬으로 분석하기 시작했다.  
<br/> 

## 산점도 그래프 그리기
첫번째로, 이 자료들의 산점도 그래프를 그릴 코드를 짰다.  


```
import pandas as pd
from matplotlib import pyplot as plt

#데이터 불러오기
data = pd.read_csv("Data_inversed.csv")

#그래프 그리기
plt.scatter(data["Syst_avg"], data["Comm_avg"],c="green", alpha=0.3)
plt.xlim(0,5.1)
plt.ylim(0,5.1)
plt.title('System and Commitment')
plt.xlabel('System_average')
plt.ylabel('Commitment_average')
plt.show()
```

친구의 도움을 받아가며 써냈다. 그 결과 나온 산점도 그래프 중 몇가지를 살펴보면..
![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/3.png){: width="400" height="150"}  
<div style="text-align: center; font-style: italic; color: gray;">
  조직몰입도 - 제도 산점도 그래프
</div>  
&nbsp;&nbsp;먼저 평균값들끼리 플롯을 그려봤다. 전반적으로 별 상관관계가 발견되지 않았다(..)
다만 조직몰입도 - 제도(Educ - Syst) 그래프는 그나마 양의 상관관계가 있다고 볼 법한 결과가 나왔다.  
<br/>

그리고, 세 변수들 중 주목할 만한 것들을 하나씩 뽑아봤다.

![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/4.png){: width="400" height="150"}  
의견이 한 쪽으로 몰린 경우도 있었다. Welf_3은 "우리 학교는 체육 시설이 잘 갖춰져 있다."

![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/4.png){: width="400" height="150"}  
안좋은 쪽으로 몰린 사례도 나왔는데, Syst_4는 "우리 학교의 교복 착용 방식에 만족한다."  
당시 생활복 귀가가 허용된지 얼마 안된 시점이었는데도 여론이 부정적이었다.

이상이 산점도 그래프에 대한 분석이었다.

## p-value 산출

&nbsp;&nbsp;다음은 p value값을 통한 검증이다. 먼저 p value를 구하기 위해 로지스틱 회귀분석 모델을 구성했다. 
 
주요 내용 :   
1. 사용한 독립 변수들은 모두 각 항목들의 평균값이다.
2. 로지스틱 회귀분석의 특성상 종속변수는 0또는 1이어야 했기에, Comm_avg 항목의 4~5는 1, 1~3은 0으로 바꾸기도 했다.

```
import pandas as pd

data = pd.read_csv("Data_binomial_y.csv")

features = data[['Welf_avg','Educ_avg','Syst_avg']]
comm = data['Comm_bi']

import statsmodels.api as sm

logit_model = sm.MNLogit(comm,features)
result = logit_model.fit()
print(result.summary())
```
 
&nbsp;&nbsp;첫번째 시도는, 변수들의 긍정/부정 방향을 모두 맞춰서 진행해봤다. Welf_4 항목과 Educ_1~4 항목들만 5로 갈 수록 부정적인 질문이었기 때문에, 숫자들을 반대로 바꿔서 다른 항목들과 맞춰줬다.

![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/6.png){: width="500" height="150"}  
&nbsp;&nbsp;교육(Educ) 쪽 변수의 p value가 0.057로 가장 낮았다. 0.05 이하인 요소가 나왔으면 했지만, 그건 실패..

다만 주목할 건 <U>coef</U>인데, 우선 coef는 양수이면 두 변수에 양의 상관관계가, 음수이면 두 변수에 음의 상관관계가 있음을 의미한다. (계수이므로)
일단 모든 변수들은 5로 갈수록 긍정적, 1로 갈수록 부정적인 방향으로 맞춰져 있었다.  

**Syst_avg**는 coef가 양수이므로, _'학교 제도가 마음에 들수록 조직몰입도가 높다'_ 라는 납득할만한 결과를 도출할 수 있다.  
**Educ_avg**는 coef가 음수이므로 _'학교 교육이 마음에 안들 수록 조직몰입도가 높다'_ 라는 직관에 반하는 결과가 도출된다.  
**Welf_avg**도 coef가 음수이므로, _'학교의 복지가 마음에 안들면 조직몰입도가 높아진다'_ 와 같은 직관에 반하는 결과가 도출된다.  

Educ과 Welf도 당연히 양의 상관관계가 나올거라고 생각하고 만든 문항인데 결과는 내 예상을 따라주지 않았다. 이유는.. 잘 모르겠다.
 
그래서 Educ 변수를 그냥 원래대로, 1로 갈수록 긍정적이고 5로 갈수록 부정적이게 만들어서 두 번째 시도를 해봤다.
이 경우, 의도대로라면 Educ 변수의 coef만 음수가 나와야할 것이다.

![mixpanel-parameter-error](/assets/post-img/ds/ds_etc/highschool/7.png){: width="500" height="150"}  

&nbsp;&nbsp;그 결과, Syst의 coef는 여전히 양수, Educ의 coef는 음수가 나와서 의도대로 되었지만, Welf의 coef는 여전히 음수였다.
심지어 Educ은 말만 음수지 사실상 기울기 0에 가까웠고, 제일 문제는 p value가 형편없었다(..)
이러나 저러나 큰 수확은 없었던 것 같다.

# 결론
## 마케팅적 활용 방안 구성

&nbsp;&nbsp;분석을 통해, 교육적 측면이 학생들의 조직몰입도와 관련이 있다고 볼 수 있다. 이와 관련해 이어서 해볼 수 있을 법한 조치로 다음과 같은 것들을 구상해 봤다.  
* 어떤 유형의 교사가 어떻게 문제인지에 대한 기술조사 시행하기
* 4P의 Product : 기술조사 내용을 기반으로 수업 내용을 개선
* 차별적 마케팅 : 학생 각자가 원하는 과목을 들을 수 있는 환경 갖추기
* 비차별적 마케팅 : 체육관 운영 현행 유지, 전교생에게 체육시설 제공
 
# 탐구의 한계점

* 표본이 적음 (표본평균으로 모평균을 대체하기 위한 기준으로 교과서에 제시된 n>=30도 충족시키지 못함..)
* 요인분석 등을 하지 못한 점
* 질문 구성 중 판정의문문이 있었음 (credit : 친구 김**)


# 참고한 자료

[https://kongdols-room.tistory.com/91](https://kongdols-room.tistory.com/91) : 산포도 그래프 그리기  
[https://mkjjo.github.io/python/2019/01/10/scaler.html](https://mkjjo.github.io/python/2019/01/10/scaler.html) : 정규화의 종류  
[https://www.datasklr.com/logistic-regression/multinomial-logistic-regression](https://www.datasklr.com/logistic-regression/multinomial-logistic-regression) : 로지스틱 회귀  
[https://ordo.tistory.com/100](https://ordo.tistory.com/100) : 상관분석