---
tags:
  - dictionary
  - math/statistic/probability
aliases:
  - 라플라스 스무딩
---
# Laplace Smoothing
> 빈도에 상수값을 추가하여 확률이 0이 되는 것을 방지
## 정의
+ ***라플라스 스무딩***은 라플라스 상수 $\alpha$에 대해, 벡터 $X$와 그 가능한 모든 특성 집합 $V$, 집합 $Y$에 대해 조건부 확률을 구할 때, 다음으로 구하는 것 
	+ $$P(x_i|y) = \frac{count(x_i, y) + \alpha}{\sum_{x \in V}count(x, y)+\alpha N_V}$$