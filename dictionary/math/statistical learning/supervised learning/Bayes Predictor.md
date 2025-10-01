---
tags:
  - dictionary
  - math/statistical_learning
aliases:
  - 베이즈 예측기
---
# Bayes Predictor
> [[Bayes Risk|베이즈 리스크]]를 가지는 예측기
## 정의
+ ***베이즈 예측기***는 [[Bayes Risk|베이즈 리스크]]를 가지는 예측기
	+ $$f^*(x) \in \underset{\tilde y \in \mathcal Y} {\arg \min}\;\mathbb E_{Y|X} [l(Y, \tilde y) | X=x]$$