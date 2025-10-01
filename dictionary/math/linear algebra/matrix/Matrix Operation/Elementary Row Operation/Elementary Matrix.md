---
tags:
  - dictionary
  - math/linear_algebra/matrix
  - math/linear_algebra/matrix/operation
aliases:
  - 기본행렬
---
# Elementary Matrices
> [[Elementary Row Operation|기본행 연산]]을 [[Product of Matrix|행렬곱]]으로 표현할 수 있게 만든 [[Matrix|행렬]]
## 정의 
+ ***기본행렬***은 [[Identity Matrix|단위행렬]]에 [[Elementary Row Operation|기본행 연산]]을 한번 적용해서 얻은 [[Matrix|행렬]]
	+ $$\begin{matrix}
E1: & R_{ij} &=& I_m + E_{ij}+E_{ji}-E_{ii}-E_{jj}\\
E2: & R_i(c) &=& I_m + (c-1)E_{ii}\\
E3: & R_{ij}(c) &=& I_m + cE_{ij}\\
&E_{ij} &=& e_ie_j^T
\end{matrix}$$
## 성질
+ [[Invertible Matrix|가역]]
	+ 기본행렬의 [[Inverse Matrix|역행렬]]은 기본행렬