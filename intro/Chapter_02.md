*Chapter 02. 딥러닝의 원리

regression->딥러닝 모델의 한 퍼셉트론의 과정과 비슷하다고 보면 됨.

Step 1. 딥러닝의 구조 - 집값모델
- Supervised Learning
  - Labelled 학습셋이 주어짐
- 학습셋
  - x= [면적], y = [집값]이라고 할 때
 ![image](https://user-images.githubusercontent.com/109457820/188553168-2af8fbbd-c790-4697-ad58-b9e9f70ef79b.png)
  - 다음에 면적을 주면 집값을 예측하게 만들고 싶음

- 1. 때려맞추기 : 1차함수로 만들어보기 y=ax+b , a->세타1, b->세타0
  - 세타0, 세타1에 아무숫자나 넣어보고 그래프의 점들과 맞는지 보기 --> 계속 시도
  - 언제까지 해야할지 모름 --> 악순환
- 딥러닝 : 노가다의 끝 
  - 언제계산을 멈출 수 있나요 : 무한한 h(x)중 무엇이 좋은 함수인가?
   >나쁨/틀림을 정의, wrongness를 minimize 시키는 전략
  - Cost/Loss function 사용
   >h(x)의 예측 y'와 주어진 학습셋의 y의 차이를 최소화

Step 2. 딥러닝의 구조 - 비용함수

- J(θ) - cost function
    - θ =[θ0 θ1]
- 즉 J(θ0,θ1)
    ![image](https://user-images.githubusercontent.com/109457820/190376872-4e370308-00b7-41f0-90d1-b9528438bcb6.png)
    
- 과정
![image](https://user-images.githubusercontent.com/109457820/190376835-c714deb6-5f02-47f5-b21d-7f22fe1cf1f7.png)

