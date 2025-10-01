---
tags:
  - dictionary
  - math/statistical_learning/supervised_learning
aliases:
  - 일관성
  - 학습 알고리즘의 일관성
---
# Consistency
> [[Learning Algorithm|학습 알고리즘]]의 [[Data Set|데이터셋]] 증가에 대한 [[Bayes Risk|베이즈 리스크]] 수렴성
## 정의 
+ ***학습 알고리즘의 일관성***은 [[Data Set|데이터셋]] 크기 증가에 대해 [[Expected Error|기대 오차]]가 [[Bayes Risk|베이즈 리스크]]로 수렴하는 [[Learning Algorithm|학습 알고리즘]]의 성질 
	+ $$\lim_{n\to\infty} \mathbb E[R_p(\mathcal A(\mathcal D_n(p))] = R^*_p$$
+ 또는 [[Expectation of Excess Risk|기대 초과 리스크]]가 0으로 수렴하는 [[Learning Algorithm|학습 알고리즘]]의 성질
	+ $$\lim_{n\to\infty} \mathbb E[R_p(\mathcal A(\mathcal D_n(p))] - R^*_p = 0$$