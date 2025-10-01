---
tags:
  - dictionary
  - math/statistical_learning/supervised_learning
aliases:
  - 베이즈 리스크
  - 베이즈 위험
---
# Bayes Risk
> [[Risk|리스크]]의 하한선
## 정의
+ ***베이즈 리스크***는 [[Risk|리스크]]의 이론적 최솟값
	+ $$R^* := \mathbb E_X[\underset{\tilde y \in \mathcal Y}\inf\mathbb E_{Y|X} [l(Y, \tilde y)|X=x]] $$