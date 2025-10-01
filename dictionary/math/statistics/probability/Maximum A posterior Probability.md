---
tags:
  - dictionary
  - math/statistic/probability/bayes_theorem
aliases:
  - MAP
---
# Maximum A posterior Probability
> [[Bayes' Theorem|베이즈 정리]]에서 사후 확률 최대화를 통한 확률 추정
## 정의
+ ***MAP***는 확률변수 $X$ 와 모수 $\theta$에 대한 다음 알고리즘
	+ $$\theta_{MAP} = \underset{\theta}{\arg\max}P(\theta|X) = \underset{\theta}{\arg\max}P(\theta)P(X|\theta)$$