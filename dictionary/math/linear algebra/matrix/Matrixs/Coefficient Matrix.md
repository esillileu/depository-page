---
tags:
  - dictionary
  - math/linear_algebra/matrix
  - math/linear_algebra/linear_equation
aliases:
  - 계수행렬
---
# Coefficient Matrix
> [[System of Linear Equation|선형연립방정식]]의 계수를 표현한 행렬
## 정의 
+ ***계수행렬***은 [[System of Linear Equation|선형연립방정식]]의 계수로 만든 [[Matrix|행렬]]
	+ $$\begin{matrix}
a_{11}x_{11}+a_{12}x_{12}+\cdots+a_{1n}x_{1n} = b_1 \\
a_{21}x_{21}+a_{22}x_{22}+\cdots+a_{2n}x_{2n} = b_2 \\
\vdots \\
a_{m1}x_{m1}+a_{m2}x_{m2}+\cdots+a_{mn}x_{mn} = b_m\\
\downarrow \\
A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n}\\
a_{21} & a_{22} & \cdots & a_{2n}\\
\vdots & \vdots & \ddots & \vdots&\\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}
\end{matrix}$$