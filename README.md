# automl-pipeline
![image](https://user-images.githubusercontent.com/46089347/68933580-4cbce680-07d8-11ea-9230-190e80ab18f4.png)

로컬 머신에서 학습을 시작한 다음, 클라우드로 확장할 수 있다.

# 되겠지 라는 마음으로 덤볐지만...window 초심자에게 local의 벽이 높았습니다.
Jupyter Notebook: 예제 Notebook을 사용하거나 고유한 Notebook을 만들어 기계 학습에서 Python용 Azure SDK 샘플을 활용할 수 있습니다.
여러 시행착오 끝에 예제로 몇 번 돌려보는 것이 좋겠다는 생각을 했음-> local에서 온갖 이유로 error...erroerroerroerorr

# NNI로 예제를 돌려봤지만 많은 시간을 local notebook에 쏟은 탓에 그만...그 결과..
-window에서 local로 azure를 돌려보신 분의 코드를 찾기가 어려웠음.

-첫번째 quest : 기본중에 기분 MNIST
## ***1. Training***
GCP를 사용할 때와는 다른 느낌에 로그인을 하지 않고 코드를 쳤다가 실패하는 경우가 있었음.

-기본 중에 기본이지만 Azure가 
*Portal*이 있고 *Studio*가 있다는 것을 초심자분들은 유의해주세요.. 저와 같은 실수를 반복하지 마세요..

-로컬에서 돌리니 주피터 환경에 따라 스크립트가 바로 만들어지지 않는 경우가 있었음.

-%%의 경우 인식을 하지 못해 따로 .py로 만들어 해당 경로에 넣어줬더니 제대로 동작

![image](https://user-images.githubusercontent.com/46089347/68934498-1da77480-07da-11ea-85a1-c3cbfc3a4d6a.png)
거의 뻘짓의 연속이었습니다..
![image](https://user-images.githubusercontent.com/46089347/68934638-5f381f80-07da-11ea-9252-5c10abbfb952.png)

모델을 register한 후 deploy하는 과정에서도 한 차례 고난이 있었는데..
![image](https://user-images.githubusercontent.com/46089347/68934898-eb4a4700-07da-11ea-9e62-ec189f76ae57.png)
sklearn모델을 불러와서 joblib를 import하는 데서 error가 났다. 

stackoverflow를 뒤진 결과 joblib의 version이 통일되게 쓰이지 않아 그렇다고 해서 그냥 **import joblib** 로 바꿨더니 기적처럼 돌아갔다.

