---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
  - 전치
---
# Transpose
> [[Matrix|행렬]]의 행과 열을 교환하는 연산
## 정의
+ ***전치***는 [[Matrix|행렬]] A 에 대해 다음을 시행하는 [[Unary Operation|단항연산]]
	+ $$A = [a_{ij}]_{m\times n}$$
	+ $$A^T = [a_{ji}]_{n\times m}$$
## 성질
+ 두 행렬 $A$, $B$와 실수 $k$에 대해 다음이 항상 성립함
	+ $$\begin{matrix} 
(A^T)^T &=& A\\
(A+B)^T &=& A^T+B^T\\
(AB)^T &=& A^TB^T\\
(kA)^T &=& kA^T
\end{matrix}$$
