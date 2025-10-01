---
tags:
  - dictionary
  - math/linear_algebra/matrix
aliases:
  - 가역
  - 가역행렬
---
# Invertible Matrix
> [[Product of Matrix|행렬곱]]에 대한 [[Inverse Matrix|역행렬]]이 존재하는 [[Square Matrix|정사각행렬]]
## 정의
+ ***가역행렬***은 [[Inverse Matrix|역행렬]]이 존재하는 [[Square Matrix|정사각행렬]]
## 성질
+ 가역행렬이면 [[Inverse Matrix|역행렬]]은 유일
+ 가역인 두 행렬 $A$, $B$와 실수 $k$에 대하여 다음이 항상 성립
	+ $$\begin{matrix}
(A^{-1})^{-1} &=& A\\
(AB)^{-1} &=& A^{-1}B^{-1}\\
(kA)^{-1} &=& k^{-1}A^{-1}\\
(A^n)^{-1} &=& (A^n)^{-1} = (A^{-1})^n = A^{-n}\\
(A^T)^{-1} &=& (A^{-1})^T
\end{matrix}$$
	+ 다음 행렬은 모두 가역
		+ $A^{-1}$, $AB$, $kA$, $A^n$, $A^T$
+ 가역행렬은 다음과 동치
	+ 가역행렬은 [[Elementary Row Operation|기본행 연산]]에 대해 다음을 만족
		+ 가역행렬은 [[Identity Matrix|단위행렬]]과 [[Row Equivalent|행동치]]
		+ 가역행렬은 [[Elementary Matrix|기본행렬]]의 곱으로 표현 가능
		+ 다음은 유일한 해를 가짐
			+ $$A\mathbf x = \mathbf 0$$
	+ [[Homogeneous System of Linear Equation|동차선형연립방정식]] $A\mathbf x = \mathbf 0$ 은 유일해 $\mathbf 0$를 가짐
	+ [[System of Linear Equation|선형연립방정식]] $A\mathbf x = \mathbf b$는 유일해를 가짐
	+ [[Matrix|행렬]]의 열[[Vector|벡터]]는 [[Linearly Independent|일차독립]]
	+ [[Matrix|행렬]]의 행[[Vector|벡터]]는 [[Linearly Independent|일차독립]]
+ 가역행렬의 [[Determinant|행렬식]]
	+ [[Determinant|행렬식]]이 0이 아님