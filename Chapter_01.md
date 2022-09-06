Step 1 딥러닝이란?
- DL은 인공지능의 거대한 학문의 일부
- DL은 ML의 여러 기법 중 하나
- AI(1950s)>ML(1980s)>DL(2010s)

Step 2 딥러닝의 원리
- ML의 정의 
  - 주어진 데이터나 과거 용례를 통하여 문제에 대한 해결 성능을 최대화 하는것
- Role of Statistics
  - 샘플을 통해 문제해결
- Role of Computer Science :
  - 최적화 문제 해결 : 어떻게하면 오답을 내지않고 정답을 잘 찾을 수 있을까?
  - 추론을 위한 모델을 구성하고 평가
- 해결하고 싶은 문제 예제 : 사람이 그린 8이라는 숫자(inputs)를 어떻게 컴퓨터(computation)가 8이라고 결과(output)를 낼 수 있을까
  - 일반 프로그래밍의 경우 (딥러닝아님) : 규칙을 코딩함 --> 매우 복잡하게 if문 구성해서 해결하는것처럼 보일 수 있음
  - 딥러닝의 경우 : 숫자8의 그림을 딥러닝모델을 거쳐 8이라고 학습하고, 필기체를 인지해 8이 디지털 8로 나오게 됨.
  - ![KakaoTalk_20220906_134648422](https://user-images.githubusercontent.com/109457820/188549577-31800f03-a6ce-4bd7-8a4f-5cb68ef536a1.png)


Step 3 딥러닝이 주로 다루는 문제들

1)
- 1950s후반에 뉴럴네트워크(퍼셉트론)이 나타남. 인간의 뇌를 표현할 수 있다고 생각함. 실패함
- 1980s초반에 Decision Tree : 효과적으로 if문을 사용하는 방법, 중반에 다시 뉴럴네트워크가 등장함 : MLP--> 원래 해결하지 못하던 문제들을 해결함 
- 1990s중반에 Support Vector Machine : 선형대수기반 방법
- 2000s중반에 Logistic Regression

2)
- Association Rule Mining : 추천시스템
- Supervised Learning : 지도학습, 대부분 산업계의 문제들 해결, 문제와 정답이 주어짐
  - Classification : 분류 eg.뉴스 종류
  - Regression : 연속적인 값들 eg.집값
- Unsupervised Learning : 정답활용 x, 문제만을 보고 무언가 해내기
  - Clustering
  - Feature Extraction : 문제를 해결하는 핵심요소 추출
  - Dimensionality Reduction : 큰 문제를 효과적으로 줄이는 방법
- Reinforcement Learning : 잘한것에 +, 못한것에 -하도록 만듬. 잘한것을 점점 늘림 eg. 알파고

3)
- Supervised Learning 
  - 학습셋 주어짐
  - 학습셋은 정답이 labelled 되어있음
  - 주어진 학습셋을 근거로 학습
  - 새로운 데이터가 들어오면 정답을 예측

- Unsupervised Learning
  - 데이터가 주어짐
  - 학습셋은 정답이 있을수도 없을 수도 있음
  - 주어진 데이터의 정보를 활용, 패턴을 추출하거나 관계를 구성
  - 명확하게 정해진 정답은 없음
  - eg. K-means Clustering
- 
