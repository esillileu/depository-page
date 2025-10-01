---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
---
# Cofactor Expansion
> 특정 행이나 열의 원소와 [[Cofactor|여인자]]를 통해 [[Determinant|행렬식]]을 구하는 방법
## 정의 
+ ***여인자 전개***는 n차 [[Square Matrix|정사각행렬]] $A$의 임의의 행이나 열의 원소 $a_{ij}$와 대응하는 [[Cofactor|여인자]] $A_{ij}$의 곱들의 합
	+ $$\det A = \sum_{k=1}^{n}a_{ik}\cdot A_{ik} = \sum_{k=1}^{n}a_{kj}\cdot A_{kj}$$