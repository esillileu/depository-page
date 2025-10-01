---
tags:
  - dictionary
  - math/linear_algebra/matrix/property
aliases:
  - 행렬의 대칭행렬 표현
---
# Symmetric Matrix Expression
> [[Matrix|행렬]]을 [[Symmetric Matrix|대칭행렬]]과 [[Skew-Symmetric Matrix|반대칭행렬]]로 표현할 수 있음
## property
+ 임의의 [[Square Matrix|정사각행렬]] $A$에 대해 다음을 항상 만족함
	+ $A+A^T$는 [[Symmetric Matrix|대칭행렬]]
	+ $A-A^T$는 [[Skew-Symmetric Matrix|반대칭행렬]]
	+ $A$는 항상 [[Symmetric Matrix|대칭행렬]]과 [[Skew-Symmetric Matrix|반대칭행렬]]의 합으로 표현 가능
		+ $$A = \frac{A+A^T}{2}+\frac{A-A^T}{2}$$