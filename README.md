# MLP : 지도학습 개념 (01/30 학습 범위)

# 기본적인 구조
## Input -> Hidden Layer -> Output 으로 구성
## AutoGrad : MLP 의 핵심 기술로 forward propagation과 backward propagation으로 구성되어 파라미터를 학습해나가는 기능 
	- Forward : 행렬곱으로 노드 크기를 맞춤 -> Activation Function로 판단 -> Output 크기에 맞게 행렬곱하여 산출
		#### Activation Function의 종류
			##### sigmoid 함수
				- 0 ~ 1 사이 값으로 변환  
				- Gradient Vanishing 문제 발생 : 층이 깊어질수록 기울기 소실 문제 => 0으로 수렴 
			##### ReLU 함수 : [sigmoid 함수의 문제점] 기울기 소실 문제해결 알고리즘
				- 최솟값 : 0
				- 0 이상의 값 : 그대로 
		#### dropout : [과적합 문제] : 특정 노드를 누락시켜서 일반화 
	- Backward : loss = (y - y_pred).pow(2).sum() 로 loss 함수를 정의하고 loss.backward를 진행한다.  # MSE 의 경우 
		#### 손실함수 : MSE, LASSO, Ridge, ElascitNet
			##### MSE
			##### LASSO
			##### Ridge
			##### ElasticNet 
		#### back propagation = loss.backward() : 오차를 줄이기 위한 방향까지
		#### optimizer = w1 - (w1.grad * lr) : 실제로 움직이는 것
			##### Momentum : 방향성 -> 관성 추가하는 개념 
			##### NAG
			##### RMSProp : 지수평균 활용법
			##### Adagrad : 가보지 않은 곳은 많이 움직이고, 가본 곳은 조금씩 움직이는 방식
			##### Adadelta : gradient 양이 적어지면 움직임이 멈추는 현상 방지 
			##### Adam : RMSProp + Momentum
			##### RAdam : 초반에는 SGD , 중기 이후에는 Adam 방식
		#### gradient 값 초기화 
## 초기 가중치 설정법
	- LeCun Initialization
	- Xavier Initialization
	- He Initialization

## Batch Normalization : Internal Covariance Shift [각 레이어마다 Input 분포에 따라 학습속도가 달라지는 현상]을 해결하기 위해 정규화 => ex) 0이하의 값은 0으로 처리하여 속도 줄일 수 있음.