---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
  - 행렬의 거듭제곱
---
o## Power of Matrix
> [[Square Matrix|정사각행렬]]에 대한 거듭제곱
## 정의
+ ***행렬의 거듭제곱***은 n차 [[Square Matrix|정사각행렬]] $S$에 대해 다음을 시행하는 연산
	+ $$S^0 = I_n,\;\;S^k = \underbrace {SS\cdots S}_k, \;\; k \in \mathbb N $$
	+ 지수가 음수일 때는 [[Inverse Matrix|역행렬]] 연산 
## 성질
+ 정수 $k$, $l$에 대해 다음을 항상 만족
	+ 지수법칙 만족
		+ $$S^kS^l = S^{k+l}$$
		+ $$(S^k)^l = S^{kl}$$