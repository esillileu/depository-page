---
tags:
  - dictionary
  - math/statistical_learning/supervised_learning
aliases:
  - 리스크
  - 위험
---
# Risk
> [[Ground Truth|실제 분포]]에서 [[Hypothesis Function|예측기]]에 대한 [[Loss Function|손실 함수]]의 [[Expectation|기댓값]]
## 정의
+ ***지도학습의 리스크***는 [[Ground Truth|실제 분포]]에서 [[Hypothesis Function|예측기]] $f$의 예측에 대한 [[Loss Function|손실 함수]]에 대한 [[Expectation|기댓값]]
	+ $$R(f) :=\mathbb E_{X, Y}[l(Y, f(X))] = \int_{\mathcal X, \mathcal Y} l(y, f(x))dp(x, y) $$
	+ under Law of Total Expectation
		+ $$R(f):=\mathbb E_X[\mathbb E_{Y|X} [l(Y, f(x)|X=x]]$$
