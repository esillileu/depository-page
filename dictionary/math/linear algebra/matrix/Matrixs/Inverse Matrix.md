---
tags:
  - dictionary
  - math/linear_algebra/matrix
aliases:
  - 역행렬
---
# Inverse Matrix
> [[Product of Matrix|행렬곱]] 했을 때 [[Identity Matrix|단위행렬]]이 되는 행렬
## 정의 
+ ***역행렬***은 n차 [[Square Matrix|정사각행렬]] $A$에 대해 다음을 만족하는 n차 [[Square Matrix|정사각행렬]] $B$
+ $$AB = I_n = BA$$
+ $$B = A^{-1}$$
## 성질
+ [[Adjugate|수반행렬]]과 [[Determinant|행렬식]]으로 계산 가능
	+ $$A^{-1} = \frac{\operatorname{adj}{A}}{\det A}$$