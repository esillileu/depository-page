---
tags:
  - dictionary
  - math/linear_algebra
aliases:
  - 일차독립
  - 선형독립
---
# Linearly Independent
> [[Linear Combination|일차결합]]으로 표현되지 않는 관계
## 정의
+ ***일차독립***은 [[Subspace|부분공간]] $S$의 원소 $\mathbf x_i$와 그 [[Field|체]] $F$위의 원소 $k$에 대해 다음을 만족하는 $\mathbf x_i$사이의 관계
	+ 다음 방정식에 대한 자명하지 않은 해가 존재하지 않음
		+ $$k_1\mathbf x_1+k_2\mathbf x_2+\cdots+k_n\mathbf x_n= \mathbf 0$$
	+ 자명한 해
		+ $$c_1=c_2=\cdots=c_n = 0$$
## 성질
+ 일차독립이면 [[Linearly Dependent|일차종속]]이 아님
+ [[Standard Unit Vector|기본 단위 벡터]]는 일차독립
+ $\mathbb R^n$에 대해 일차독립일 수 있는 벡터는 최대 $n$개