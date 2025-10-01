---
tags:
  - dictionary
  - math/statistic/probability
aliases:
  - 베이즈 정리
---
# Bayes' Theorem
> 서로 배반하는 두 원인 중 한 원인일 확률을 구하는 방법
## 정의
+ 베이즈 정리는 서로 배반인 사건 $A, B$에 대하여 다음을 만족하는 상태
	+ $$P(B|A) = \frac{P(A|B)\cdot P(B)}{P(A)} = \frac{P(A\cap B)}{P(A)}$$ 
## 추정
+ 베이즈 정리를 이용하여 확률을 추정할 때, 다음과 같은 관점을 사용한다
	+ $P(B|A)$ : 사후 확률
	+ $P(A|B)$ : [[Likelihood|우도]]
	+ $P(B)$ : 사전 확률
	+ $P(A)$ : 데이터 자체의 분포 - 상수
+ 방법
	+ [[Maximum A posterior Probability]] - 사후 확률의 최대화 
	+ [[Maximum Likelihood Estimation]] - 우도 최대화
