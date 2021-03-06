# 일반화와 과적합
## 한계점
- 데이터의 한계가 있고 언제나 발생할 수 있는 데이터이기 때문에 rmse나 R스퀘어로 평가하는 것은 위험
> 목표는 실제 세계의 데이터 
---
## 모형의 유형성
- 모델에서 가정하는 차수가 커질수록
  - 모델의 유연성이 커진다
  - 더 복잡한 패턴이 표현 가능하다
  - `학습데이터`에 대한 정확도가 높아진다
- 유연성이 클수록 좋은 모델인가? -> X
- 모델의 유연성이 높을수록 rmse r2 높아짐
### overfitting (과적합)
- 관측된 데이터에 대해서만 너무 정확도가 높음, 실제 데이터(학습 안 된 testing data)에 대한 일반화 실패
- 학습(training)데이터에 대해 너무 지나치게 충실하게 표현

### underfitting (과소적합)
- 지나치게 단순한 표현
---
## 일반화 측면에서 모델의 비교
- 관측된 데이터에 대한 성능이 아닌, 실제 데이터에 대한 성능이 좋아야함
- 일반화 능력이 좋은 모델을 선택해야함

## 분류문제에서의 과적합
- label의 경계선이 울퉁불퉁할수록 유연한 모델
---
## 모델의 일반화 능력 측정 방법
### 대안
- 관측된 데이터를 일부는 훈련데이터와 일부는 테스트데이터로 나눔
  - 훈련데이터 : 모델의 학습에 사용
  - 테스트데이터 : 모델의 일반화 능력 검증에 사용

### step
1. 확보한 데이터를 훈련데이터와 테스트 데이터로 나눔
2. 훈련데이터로 모델 학습
3. 테스트데이터로 모델 정확도 측정
   1. 테스트데이터를 넣고 실제 값과 일반화 능력 측정
   2. 훈련데이터를 통한 rmse 와 r2 - 훈련데이터를 얼마나 잘 표현
   3. 테스트데이터를 통한 rmse 와 r2 측정 - 테스트 데이터를 얼마나 잘 표현

### 모델에 따른 훈련 정확도
- 훈련데이터는 모델의 유연성이 높으면 높을수록 에러가 줄어듦
- 테스트데이터는 모델의 유연성이 낮거나 높을 때 에러가 올라갈 수 있음
  - overfitting : training data의 정확도는 높을 수 있음
    - high variance : 예측값들 사이의 편차가 큼 (선이 구불구불하다는 것은 예측값이 그만큼 서로 멀리 떨어져있다고 볼 수 있음)
  - underfitting : 둘 다 정확도 떨어짐
    - high bias : 예측값과 정답값 간의 차이가 큼