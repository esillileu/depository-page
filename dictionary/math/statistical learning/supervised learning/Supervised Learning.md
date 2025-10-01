---
tags:
  - dictionary
  - math/statistical_learning/supervised_learning
aliases:
  - 지도학습
---
# Supervised Learning
> [[Ground Truth|실제 분포]]에 대한 최적 [[Function|함수]]의 학습
# 정의 
+ ***지도학습***은 [[Ground Truth|실제 분포]] $P(x, y)$의 최적 [[Function|함수]]를 찾기 위해 샘플링 된 값의 [[Risk|리스크]]를 최소화하는 학습 방법론
	+ $$\begin{matrix}
f=\arg \underset{f\in \mathcal F}\min ​\mathbb E_{(x,y)∼P}​[L(y,f(x))]\\
f : \mathcal X \to \mathcal Y\\
\end{matrix}$$
		+ $\mathcal F$ : 가능한 모든 가설 공간
		+ $\mathcal X$ : 입력 공간
		+ $\mathcal Y$ : 라벨 공간