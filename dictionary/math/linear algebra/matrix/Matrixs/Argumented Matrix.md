---
tags:
  - dictionary
  - math/linear_algebra
aliases:
  - 첨가행렬
---
# Argumented Matrix
> [[Coefficient Matrix|계수행렬]]에 상수항을 첨가한 행렬
## 정의
+ ***첨가행렬***은 [[Coefficient Matrix|계수행렬]]에 [[System of Linear Equation|선형연립방정식]]의 상수항을 첨가해서 만든 행렬
	+ $$\begin{matrix}
a_{11}x_{11}+a_{12}x_{12}+\cdots+a_{1n}x_{1n} = b_1 \\
a_{21}x_{21}+a_{22}x_{22}+\cdots+a_{2n}x_{2n} = b_2 \\
\vdots \\
a_{m1}x_{m1}+a_{m2}x_{m2}+\cdots+a_{mn}x_{mn} = b_m\\
\downarrow \\
[A|\mathbf b] = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} & | &b_1\\
a_{21} & a_{22} & \cdots & a_{2n}&  | &b_2\\
\vdots & \vdots & \ddots & \vdots&  \vdots &\vdots\\
a_{m1} & a_{m2} & \cdots & a_{mn}&  | &b_1
\end{bmatrix}
\end{matrix}$$
