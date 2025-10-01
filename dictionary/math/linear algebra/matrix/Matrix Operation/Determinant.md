---
tags:
  - dictionary
  - math/linear_algebra/matrix/operation
aliases:
  - 행렬식
---
# Determinant
> [[Square Matrix|정사각행렬]]의 #추가필요 
## 정의 
+ ***행렬식***은 [[Square Matrix|정사각행렬]] $A$의 가능한 모든 행-열 선택을 고려하여 [[Signature Function|부호화함수]]를 적용한 원소들의 곱들의 합
	+ $$\det(A) = \sum_{\sigma \in S_n} \operatorname{sgn}(\sigma) \prod_{i=1}^{n} a_{i, \sigma(i)}$$
# 성질
+ [[Transpose|전치]]는 행렬식에 영향 없음
	+ $\det(A)=\det(A^T)$
+ 행렬식의 곱셈법칙
	+ $\det(AB) = \det(A)\cdot\det(B)$
+ [[Invertible Matrix|가역행렬]] A에 대해
	+ $\det(A) = 0$
	+ $\det A^{-1} = \frac 1 {\det (A)}$
+ [[Elementary Row Operation|ERO]] 적용 시
	+ $$\det(EA) = \det(E)\det(A)$$
	+ [[Elementary Row Operation|E1]] 한 번 적용시 행렬식의 부호변경
		+ $\det(A) = -\det(\operatorname{E_1}(A))$
	+ [[Elementary Row Operation|E2]] 적용시 행렬식은 스칼라배
		+ $c\cdot\det(A) = \det(\operatorname{E_2}(A))$
	+ [[Elementary Row Operation|E3]] 적용 시 행렬식은 변화 없음
		+ $\det(A)=\det(E_3(A))$
+ 행렬의 행이나 열이 
	+ 중복되면 행렬식은 0
	+ 비례하면 행렬식은 0
	+ 성분이 모두 0이면 행렬식은 0
+ [[Triangular Matrix|삼각행렬]]의 행렬식은 [[Main Diagonal Entries|주대각성분]]의 곱