### MLP : 지도학습 개념 (01/30 학습 범위)

# 기본적인 구조
	- Input -> Hidden Layer -> Output 으로 구성
	- AutoGrad : MLP 의 핵심 기술로 forward propagation과 backward propagation으로 구성된다. 
		- Forward : 행렬곱으로 노드 크기를 맞춤 -> Activation Function로 판단 -> Output 크기에 맞게 행렬곱하여 산출
			- Activation Function의 종류
				- 
		- Backward : 이후 loss = (y - y_pred).pow(2).sum() 로 loss 함수를 정의하고 loss.backward를 진행한다.  # MSE 의 경우 