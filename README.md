# automl-pipeline

## ***0. AutoML***
![image](https://user-images.githubusercontent.com/46089347/68933580-4cbce680-07d8-11ea-9230-190e80ab18f4.png)

인공 신경망을 활용한 연구는 이미지, 비디오, 자연어 기반 태스크의 추론 정확도를 높이는 것에서 더 나아가 신경망 최적화 및 자동 구조화 분야로 그 폭을 넓혀가고 있다. 인공 신경망 기반 데이터 분석 태스크는 **데이터 탐색, 데이터 전처리/정제, 특징 추출, 모델 선택, 모델 훈련 및 최적화의 단계**로 진행된다. 특히 목표 데이터별로 *모델 선정, 훈련 및 최적화 단계*를 수행하기 위해서는 *도메인 전문 지식은 물론 **많은 시간**과 **컴퓨팅 자원***이 요구된다. 

![image](https://user-images.githubusercontent.com/46089347/68935760-7415b280-07dc-11ea-86a4-dde93e33ec79.png)
<출처: ETRI https://ettrends.etri.re.kr/ettrends/178/0905178004/>


로컬 머신에서 학습을 시작한 다음, 클라우드로 확장할 수 있다.

# window 초심자에게 닥친 local의 벽
Jupyter Notebook: 예제 Notebook을 사용하거나 고유한 Notebook을 만들어 기계 학습에서 Python용 Azure SDK 샘플을 활용할 수 있습니다.
여러 시행착오 끝에 예제로 몇 번 돌려보는 것이 좋겠다는 생각을 했음-> local에서 온갖 이유로 error...erroerroerroerorr

# NNI에서 예제가 별다른 문제 없이 성공해 이걸로 할까 했지만 많은 시간을 local notebook에 쏟은 탓에 끝까지 해보기로 했는데..
-window에서 local로 azure를 돌려보신 분의 코드를 찾기가 어려웠음.

-첫번째 quest : 기본중에 기본예제 **MNIST**
## ***1. Training***
GCP를 사용할 때와는 다른 느낌에 로그인을 하지 않고 코드를 쳤다가 실패하는 경우가 있었음.

-기본 중에 기본이지만 Azure가 
*Portal*이 있고 *Studio*가 있다는 것을 초심자분들은 유의..

-로컬에서 돌리니 주피터 환경에 따라 스크립트가 바로 만들어지지 않는 경우가 있었음.

-%%의 경우 인식을 하지 못해 따로 .py로 만들어 해당 경로에 넣어줬더니 제대로 동작

![image](https://user-images.githubusercontent.com/46089347/68934498-1da77480-07da-11ea-85a1-c3cbfc3a4d6a.png)
거의 뻘짓의 연속이었습니다..
![image](https://user-images.githubusercontent.com/46089347/68934638-5f381f80-07da-11ea-9252-5c10abbfb952.png)

## ***2. Deploy***
모델을 register한 후 deploy하는 과정에서도 한 차례 고난이 있었는데..
![image](https://user-images.githubusercontent.com/46089347/68934898-eb4a4700-07da-11ea-9e62-ec189f76ae57.png)
sklearn모델을 불러와서 joblib를 import하는 데서 error가 났다. 

stackoverflow를 뒤진 결과 joblib의 version이 통일되게 쓰이지 않아 그렇다고 해서 **import joblib** 로 바꿨더니 돌아갔다.


