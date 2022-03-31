## NLP | BERT를 통한 한국어 자연어 감성분석 모델

### 0. 요약

무수히 많은 데이터가 실시간으로 형성되고 있다. 그 중 '자연어'가 차지하는 비중이 적지 않다. </br>
자연어가 포함하는 가치들을 도출하고 인간 사회와 해결책이 필요한 곳에 해결점을 모색할 수 있다. </br>
본 프로젝트는 자연어를 통한 감성분석을 서비스 제공에 활용할 수 있다는 시나리오를 가지고</br>
서비스를 제공하는 과정에서 감성 분석 모델을 구성했다.</br></br>

### 1. 시나리오
코로나라는 시대 상황에 Tea 회사는 매출이 떨어졌으며, 새로운 전략이 필요했다. </br>
이에 코로나라는 위기상황이 회사에 새로운 전환점이 될 수 있으며, 사람들에 대해서도 새로운 전환점이 될 수 있다 생각했다. </br></br>
코로나 이후 사람들은 관계의 '단절'을 경험하며 기계에 익숙해지고, 자신의 마음을 쉽게 털어놓는 것에 거리감을 느끼게 되었다. </br>
이러한 상황을 고려하여 사람들이 자신의 감정과 상황을 자연어(인간의 언어)로 Text로 작성하면 </br>
작성자의 감성을 예측해 Tea를 추천해주는 서비스를 제공해 줄 수 있다 생각했다. </br>
이를 위해 감성대화 텍스트를 통한 감성 예측 모델을 구축했다.

----

### 2. 활용 모델
또한 자연어처리의 대가라 불리는 BERT 모델을 활용하였다.</br></br>
<b> 모델 선택 이유</b></br>
- 문맥을 파악하는 이점
- 사전 학습 모델
- 성능이 우수함</br>

---------
### 3. 데이터

본 프로젝트는 AI-HUB에서 제공하는 2020년도 감성 대화 말뭉치를 통해 진행했다. </br>
https://aihub.or.kr/aidata/7978 </br></br>

<b>1) 본 데이터의 사용 적합성</b> </br>
- SQL을 통해 Metabase Dashboard 시각화 과정을 거쳐 데이터의 사용이 적합한지 확인했다.  </br></br>
![성별 분포](https://user-images.githubusercontent.com/89770691/148967490-f2599eba-0f63-423a-aced-5eebbc5a0905.PNG)
![연령 별 분포](https://user-images.githubusercontent.com/89770691/148967517-6d65a44e-32a9-4703-b5ac-f8144dd485bd.PNG) </br></br>
-> 성별과 연령에서의 분포가 비교적 유사하며, 포함된 감성_대분류의 범주 역시 균일하므로 본 프로젝트를 진행하기에 적합하다 판단했다. </br></br>

<b>2) 분석 과정에서의 가설: </b> </br>
- 가설1: 성별에 따라 두드러지는 감정이 있다. </br></br>
  - 결과: 귀무가설 만족 (성별에 따라 두드러지는 감정이 있다) </br></br>
  -> 성별에 따라 다른 전략을 도출할 수 있다.

![성별에 따른 감정분포](https://user-images.githubusercontent.com/89770691/148967531-c8fe78dd-0139-4a6d-aea8-6c43c29cc4a4.PNG)</br>

- 가설2: 연령에 따라 감정 분포가 다르다.</br></br>
  - 결과: 귀무가설 만족 (연령에 따라 감정 분포가 다르다.) </br></br>
  -> 연령에 따라서도 다른 전략을 도출 할 수 있다.</br>
![TSENT_-감성-분석-프로젝트-015 (1)](https://user-images.githubusercontent.com/89770691/160983282-13b86c67-932e-4609-a761-3795c4ed0870.jpg) </br></br>

### 4. 과정
- 본 데이터에 포함되어 있는 감정 소분류는 약 60개의 카테고리를 갖고 있어 너무 많은 범주로 구성되기 때문에 6개의 감정 대분류가 적합함
- 6개의 감정 분류: 기쁨, 슬픔, 당황, 상처, 불안, 분노

### 5. 결과
- 본 모델의 감정 카테고리는 6개이기 때문에 CHANCE LEVEL은 100/6인 16.66% 즉, 0.16을 상회해야 함
- 모델 학습의 결과 검증 정확도는 0.25로 CHANCE LEVEL인 0.16을 상회했음
- 테스트 정확도 역시 0.25로 CHANCE LEVEL인 0.16을 상회함 

### 6. 프로젝트 과정에서 느낀점 
- 본 데이터에는 감정의 카테고리가 긍정적인 부분과 부정적인 부분의 불균형이 있었음
- 감정의 카테고리 배분을 균형감있게 구성한다면 더 좋은 모델이 될 것이라 생각함
- 그러나 현재 Tea 상품 추천을 목적으로한 자연어 감성 예측 모델이기 때문에 본 과제와 상충되지는 않음

### 7. 추후 발전 과제
- 상품에 적합한 감성 분류
- Text 기반 감성 도출에 기반한 상품 추천 시스템을 구축

--------

### 참고자료:

seoungtaemoon, Sentiment Analysis with BERT, (2021), GitHub repository,
https://github.com/seungtaemoon/Portfolio/tree/master/Sentiment%20Analysis%20with%20BERT

BERT 설명 자료:
https://www.quantumdl.com/entry/12%EC%A3%BC%EC%B0%A82-BERT-Pre-training-of-Deep-Bidirectional-Transformers-for-Language-Understanding

BERT로 네이버 영화 리뷰데이터 분류하기
http://yonghee.io/bert_binary_classification_naver/

[4] 포털 댓글 감성 분석_2. BERT_2. 모델링 및 예측
https://projectlog-eraser.tistory.com/26?category=767763

나만의 언어모델 만들기 - BERT Pretrained Language Model (Masked Language Model) 만들기
https://velog.io/@nawnoes/%EB%82%98%EB%A7%8C%EC%9D%98-%EC%96%B8%EC%96%B4%EB%AA%A8%EB%8D%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0-Masked-Language-Model-%ED%95%99%EC%8A%B5

이미지를 텐서(Tensor)로 변환하기
https://anweh.tistory.com/10

PyTorch Dataset 정리
https://hulk89.github.io/pytorch/2019/09/30/pytorch_dataset/

PyTorch의 Dataset과 DataLoader를 이용하여 학습 효율성 향상시키기
http://www.gisdeveloper.co.kr/?p=8615

-------

저작권:
© 2022 MinsooKwak <estherpd@naver.com MinsooKwak>
