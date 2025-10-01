---
tags:
  - dictionary
  - math/linear_algebra/matrix
aliases:
  - 대각행렬
---
# Diagonal Matrix
> [[Main Diagonal Entries|주대각성분]]이외의 모든 [[Component|성분]]이 0인 [[Square Matrix|정사각행렬]]
## 정의
+ ***대각행렬***은 [[Main Diagonal Entries|주대각성분]] 이외의 모든 [[Component|성분]]이 0인 [[Square Matrix|정사각행렬]]
	+ $${diag}(a_{11}, a_{22}, \cdots, a_{nn}) = \begin{bmatrix}a_{11}&&&\\ &a_{22}&& \\ && \ddots & \\ &&&a_{nn}\end{bmatrix}$$
## 성질
+ 대각행렬의 거듭제곱은 [[Main Diagonal Entries|주대각성분]]을 [[Power of Matrix|거듭제곱]]한 대각행렬과 동일
	+ $$\begin{matrix}D = {diag}(a_{11}, a_{22}, \cdots, a_{nn})\\z\in Z\end{matrix}$$
	+ $$D^{z} = {diag}(a_{11}^z, a_{22}^z, \cdots, a_{nn}^z)$$
