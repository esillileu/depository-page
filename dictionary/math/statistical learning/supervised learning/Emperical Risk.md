---
tags:
  - dictionary
  - math/statistical_learning
aliases:
  - 경험 리스크
  - 경험 위험
---
# Emperical Risk
> 주어진 [[Data Set|데이터셋]]에서 [[Hypothesis Function|예측기]]의 [[Risk|리스크]]
## 정의 
+ ***경험 리스크***는 [[Data Set|데이터셋]]에 대한 [[Hypothesis Function|예측기]]의 [[Risk|리스크]] 
	+ $$\hat R (f) =  \mathbb{E}_{(x, y) \sim \mathcal{D}} \left[ \ell(f(x), y) \right] = \frac{1}{n}\sum_{i=1}^n\ell(f(x_i), y_i), \;\;(x_i, y_i)\in \mathcal D$$