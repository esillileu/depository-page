---
tags:
  - dictionary
  - math/statistical_learning/supervised_learning
aliases:
  - 최소최대위험
---
# Minimax Risk
> 최악 분포일때 최소 [[Risk|리스크]]
## 정의 
+ ***최소최대리스크***는 [[Execss Risk|초과리스크]]의 [[Expectation|기댓값]]을 최대화하는 샘플링에서 [[Risk|리스크]]의 최솟값
	+ $$\underset {\mathcal A} \inf \underset{p \in \mathcal P} \sup \{\mathbb E[R_p(\mathcal A(\mathcal D_n(p))) -R^*_p]\}$$