---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
  - 역행렬연산
---
# Matrix Inversion
> [[Inverse Matrix|역행렬]]을 구하는 [[Unary Operation|단항연산]]
## 정의
+ ***[[Invertible Matrix|가역행렬]] $A$에 대한 역행렬연산 $A^{-1}$*** 은 $A$의 역행렬을 구하는 단항연산
	+ $$AA^{-1} = I$$
## 계산
+ [[Matrix|행렬]] $A$에 대해 [[Identity Matrix|단위행렬]]을 첨가한 [[Argumented Matrix|첨가행렬]]에 대해 [[Gauss-Jordan Elimination|가우스-조던 소거법]]을 적용하여 [[Reduced Row Echelon Form|RREF]]를 계산
	+ $${RREF}([A:I_n]) = [C:D]$$
+ [[Argumented Matrix|첨가행렬]] $[C:D]$의 [[Matrix|행렬]] $C$, $D$에 대해 다음을 만족
	+ $C = I_n$일 때, $A$는 [[Invertible Matrix|가역]]이고 $D = A^{-1}$
	+ $C \not = I_n$일 때, $A$는 비[[Invertible Matrix|가역]]
