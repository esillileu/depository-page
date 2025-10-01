---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
  - 행렬곱
---
# Product of Matrix
> [[Matrix|행렬]]에서 정의되는 곱셈
## 정의
+ ***행렬곱***은 다음 두 [[Matrix|행렬]] $A$, $B$에 대하여 다음을 연산하는 [[Function|함수]]
	+ $$\begin{matrix}
A = [a_{ij}]_{m\times p} \\
B = [b_{ij}]_{p\times n} \\
\end{matrix}$$
	+ $$AB = [\sum_{k=1}^p a_{ip}b_{pj}]_{m\times n}$$
+ 또는 앞 [[Matrix|행렬]] $A$의 행 [[Vector|벡터]] $A_{(i)}$와 뒤 [[Matrix|행렬]] $B$의 열 [[Vector|벡터]] $B^{(j)}$의 내적을 [[Component|성분]]으로하는 [[Matrix|행렬]]을 구하는 [[Function|함수]]
	+ $$\begin{matrix}
A = \begin{bmatrix} A_{(1)} \\ A_{(2)}\\ \vdots \\ A_{(m)} \end{bmatrix} \\
B = \begin{bmatrix} B_{(1)} & B_{(2)}& \dots & B_{(n)} \end{bmatrix} \\
\end{matrix}$$
	+ $$AB = [A_{(i)} \cdot B^{(j)}]$$ 
## 성질
+ [[Commutativity|교환법칙]]은 만족하지 않음
+ [[Associativity|결합법칙]] 만족
	+ [[Scalar Multiplication of Matrix|스칼라배]]에 대핸 [[Associativity|결합법칙]] 만족
+ [[Sum of Matrix|행렬합]]에 대한 [[Commutativity|교환법칙]] 만족