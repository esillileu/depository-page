---
tags:
  - dictionary
  - math/linear_algebra/linear_equation
aliases:
  - 선형연립방정식
---
# System of Linear Equation
> 특정 미지수에 대한 유한개의 [[Linear Equation|선형방정식]]
## 정의 
+ ***선형연립방정식***은 유한개의 [[Linear Equation|선형방정식]] [[Set|집합]]
	+ $$\begin{matrix}
a_{11}x_{11}+a_{12}x_{12}+\cdots+a_{1n}x_{1n} = b_1 \\
a_{21}x_{21}+a_{22}x_{22}+\cdots+a_{2n}x_{2n} = b_2 \\
\vdots \\
a_{m1}x_{m1}+a_{m2}x_{m2}+\cdots+a_{mn}x_{mn} = b_m
\end{matrix}$$
## 표현
+ [[Coefficient Matrix|계수행렬]]을 이용한 표현
	+ $$A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n}\\
a_{21} & a_{22} & \cdots & a_{2n}\\
\vdots & \vdots & \ddots & \vdots&\\
a_{m1} & a_{m2} & \cdots & a_{mn}
\end{bmatrix}, 
\mathbf x = \begin{bmatrix}
x_{1} \\
x_{2}\\
\vdots\\
x_{n}
\end{bmatrix},
\mathbf b = \begin{bmatrix}
b_{1} \\
b_{2}\\
\vdots\\
b_{n}
\end{bmatrix}$$
	+ $$A\mathbf x = \mathbf b$$
## 성질
+ $n$차 [[Invertible Matrix|가역]] [[Square Matrix|정사각행렬]] $A$와 $\mathbb R^n$의 벡터 $\mathbf b$에 대하여 선형연립방정식 $A\mathbf x = \mathbf b$은 항상 다음의 유일한 해를 가짐
	+ $$\mathbf x = A^{-1}\mathbf b$$
	