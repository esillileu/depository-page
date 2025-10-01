---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
  - math/linear_algebra/linear_equation
aliases:
  - 크래머공식
---
# Cramer's Rule
> [[System of Linear Equation|선형연립방정식]]의 [[Argumented Matrix|첨가행렬]]의 [[Determinant|행렬식]]을 이용하여 [[Solution of Linear Equation System|해]]를 구하는 방법
## 정의 
+ ***크래머공식***은 [[Invertible Matrix|가역]]인 n차 [[Coefficient Matrix|계수행렬]] $A$에 대해 [[Determinant|행렬식]]을 이용한 [[System of Linear Equation|선형연립방정식]] $A \mathbf x=\mathbf b$ 의 유일[[Solution of Linear Equation System|해]] $\mathbf x$의 표현
	+ $$\mathbf x = [x_i]^T = \left[\frac{\det A_i}{\det A}\right]^T\;\;for\;\;i = 1, 2 \cdots n$$ 
	+ $A_i$는 $i$번째 열을 $\mathbf b$로 교체한 행렬
 