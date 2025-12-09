---
tags:
  - dictionary
  - ai/module
aliases:
  - fc
  - ffn
  - dnn
  - mlp
---
# Fully Connected Layer
> 퍼셉트론 레이어
## 정의 
- ***FC 레이어***는 입력 $X$에 대해 가중합과 활성화 함수를 적용한 출력 $Y$를 생성하는 레이어  
	- $$\begin{matrix}
Y = \operatorname{activation}(WX+B)\\
X\in \mathbb R ^ n, \;\;Y \in \mathbb R^m\\
W \in \mathbb R ^{m\times n}, \;\; B \in \mathbb R^M
\end{matrix}$$
## 특징
- 선형변환 이후 활성화 함수를 통해 비선형성 확보
- 출력의 모든 값은 각각 입력의 모든 값을 참조
- 