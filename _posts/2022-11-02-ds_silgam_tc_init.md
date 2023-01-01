---
title: "[실감] 유저의 피드백 내용 자연어 분류"
date: 2022-11-02 17:25:30 +0900
categories: [Data Related, Project-실감]
tags: [실감]     # TAG names should always be lowercase

author: rouxist

---
### 2022.11.02  

&nbsp;&nbsp;실감의 유저들의 실모 기록 데이터가 어제 막 4000개를 돌파했다. 이 데이터로 뭘 할 수 있을까 고민하던 중, 유저들이 업로드하는 실모 기록에서 (보통) 한글로 작성되는 **피드백**들을 내용에 따라 크게 긍정/중립/부정 등으로 분류하고 학습을 시킬 수 있을까 하는 생각이 (어제) 들었다. 정확도 높게 분류가 가능하다면 유저가 실모 기록을 입력한 후에 해당 피드백의 내용을 바로 분류시킬 수 있을텐데, 그럼 그것을 바탕으로 유저에게 다음에 학습할 내용을 추천해주거나, 혹은 다음 모의고사를 실시할 때 각기 다른 안내 메시지를 띄워주는 식으로('이번에도 잘할 수 있을 거에요', '이번에는 조금만 더 힘내봐요' 등.) 섬세한 ux를 만드는 등 다양한 활용 방안이 있을 듯 같다.  
<hr/>
일단 이전에 출력해둔 데이터셋에서 피드백이 없는 데이터는 모두 제거해봤다.

```
import pandas as pd

original_file = pd.read_csv('./exam_records.csv')
original_data = pd.DataFrame(original_file)

# remove rows with empty feedback
original_data = original_data.replace(r'^s*$', float('NaN'), regex = True)
original_data.dropna(inplace = True) 

# sort by : 
sorted_data = original_data.sort_values(by = ['userId', 'timestamp'])

# export to csv
sorted_data.to_csv('./exam_records_with_feedback_grouped_by_userId_timestamp.csv')
```

그랬더니 아래와 같이 약 500개의 데이터가 추려졌는데  
![for_tc_img_blur](/assets/post-img/ds/ds_silgam/ds_silgam_ds_silgam_tc_init/for_tc_img_blur.png){: width="500" height="150"}  
1. 지금 피드백과 함께 그 내용이 긍정적인지 부정적인지까지 수집한 것이 아니어서 사후적으로 일일이 라벨링을 해야 하는 상황이고
2. 데이터 개수로 봤을 때 유의미한 학습이 가능할지..? 일단 지금은 이전에 데이터셋을 출력했을 때보다 데이터의 양이 두 배로 늘어나서 1000개 정도의 데이터가 최대일 것 같다.  
<hr/>

#### 2022.11.08
![spreadsheet_blur](/assets/post-img/ds/ds_silgam/ds_silgam_ds_silgam_tc_init/spreadsheet_blur.png){: width="1000" height="150"}  
선별한 데이터를 구글 스프레드시트로 만들고, 팀원들과 공유해 라벨링을 시작했다.  
<hr/>


