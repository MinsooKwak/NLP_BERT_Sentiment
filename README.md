## NLP | BERT를 통한 한국어 자연어 감성분석 모델

### 요약

무수히 많은 데이터가 실시간으로 형성되고 있다. 그 중 '자연어'가 차지하는 비중이 적지 않다. </br>
자연어의 잠재성을 통해 유의미한 의미를 도출하고 인간 사회와 해결책이 필요한 곳에 해결점을 모색할 수 있다. </br>
자연어를 통한 감성분석을 서비스 제공에 활용할 수 있다는 시나리오를 가지고 서비스를 제공하는 과정에서 감성 분석 모델을 구성했다.</br></br>

또한 자연어처리의 대가라 불리는 BERT 모델을 활용하였다.</br>
문맥을 파악하는 이점을 갖고 있으며 성능 역시 우수하기 때문에 본 모델을 활용하였다.</br>

---------
### 데이터

본 프로젝트는 AI-HUB에서 제공하는 2020년도 감성 대화 말뭉치를 통해 진행했다.
https://aihub.or.kr/aidata/7978

### 본 데이터의 사용 적합성
![성별 분포](https://user-images.githubusercontent.com/89770691/148967490-f2599eba-0f63-423a-aced-5eebbc5a0905.PNG)
![연령 별 분포](https://user-images.githubusercontent.com/89770691/148967517-6d65a44e-32a9-4703-b5ac-f8144dd485bd.PNG)
성별과 연령에서의 분포가 비교적 유사하며, 포함된 감성_대분류의 범주 역시 균일하므로 본 프로젝트를 진행하기에 적합하다 판단했다. </br></br>

### INSIGHT
성별에 따라 두드러지는 감정이 있다. 
![성별에 따른 감정분포](https://user-images.githubusercontent.com/89770691/148967531-c8fe78dd-0139-4a6d-aea8-6c43c29cc4a4.PNG)

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
