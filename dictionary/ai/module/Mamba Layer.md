---
tags:
  - dictionary
  - ai/module
aliases:
  - 맘바
---
# Mamba
> [[State Space Model|ssm]]기반 [[Attention Layer|어텐션]] 대체 모듈
## 정의 
- ***맘바***는 입력 $x_t$를 이산화한 [[State Space Model|ssm]]과 gating으로 나누어 처리하고 출력을 계산하는 레이어 
	- 조건
		- $$
\begin{aligned}
&x_t, o_t \in \mathbb{R}^d,\quad u_t \in \mathbb{R}^D\\
&h_t \in \mathbb{R}^{D\times N}, \quad W_u, W_g \in \mathbb{R}^{D\times d} \quad W_{\text{out}} \in \mathbb{R}^{d\times D} \quad W_B, W_C \in \mathbb{R}^{N\times D} \\
&W_{dt} \in \mathbb{R}^{r\times D}, \quad W_\Delta \in \mathbb{R}^{N\times r} \\
& A = -\exp(A_{\log}) \in \mathbb R ^N\\
\end{aligned}
$$
	- 입력 투사 
		- $$
\begin{aligned}
&x_t^{\text{conv}} = W_u x_t, \quad z_t = W_g x_t,\quad \to \quad  W_{in} = \begin{bmatrix} W_u \\ W_g \end{bmatrix}\\
&\alpha_t = \sigma(z_t) \\
&u_t = \phi\!\left(\sum_{k=0}^{w-1} \text{conv\_w}[:,k]\odot x_{t-k}^{\text{conv}} + b_{\text{conv}}\right)\\
\end{aligned}$$
		- $$\begin{aligned}
&\tilde\Delta_t = W_{dt} u_t \in \mathbb{R}^r, \quad B_t = W_B u_t \in \mathbb{R}^N, \quad C_t = W_C u_t \in \mathbb{R}^N \\
&\to \quad W_{proj} = \begin{bmatrix} W_{dt} \\ W_B \\ W_C \end{bmatrix}\\
&\Delta_t = \operatorname{softplus}(W_\Delta\, \tilde\Delta_t)\in\mathbb{R}^N\\
\end{aligned}$$
	- 이산화
		- $$
\begin{aligned}
&\bar A_t = \exp(A\odot\Delta_t)\in \mathbb R^N\\
&\bar B_t = B_t\odot \frac{\exp(A\odot\Delta_t) - 1}{A}\in \mathbb R^N\\
\end{aligned}$$
	- [[State Space Model|ssm]] 상태 업데이트
		- $$\begin{aligned}
&h_{t+1}[j,n] = \bar A_t[n]\;h_t[j,n] + \bar B_t[n]\;u_t[j]\in \mathbb R^{D\times N}\\
&\tilde y_t[j] = \sum_{n=1}^{N} C_t[n]\, h_{t+1}[j,n]\in \mathbb R^{D\times N}\\
\end{aligned}$$
	- 블럭 출력
		- $$\begin{aligned}
&y_t = \alpha_t \odot \tilde y_t\\
&o_t = W_{\text{out}}\, y_t + x_t\\
\end{aligned}
$$
## 구조
- 입력을 투사 후 게이팅과 ssm 입력으로 분해
	- 게이팅은 시그모이드로 활성화
	- ssm 입력은 1D 컨볼루션 이후 활성화
		- 컨볼루션 과정에서 줄어든 부분은 선형 투사 값 그대로 사용
		- 디코딩 시에는 슬라이딩 윈도우로 이전 입력에 대해서만 계산 - L 개념 없음
- ssm 입력은 $\Delta$, $B$, $C$로 투사
- 이산화 후 ssm 상태 업데이트
	- 업데이트 과정에서 브로드캐스팅
## 특징
- 상태를 별개의 1차 ssm으로 분해
- 입력에 따라 $B$, $C$가 동적으로 바뀜
	- 입력에 대해 레이어 놈/rms 놈 적용
	- $B$는 $\Delta$ 기반 스케일링
	- 모든 파라미터에 대해 재매개변수화 
- prefix-scan으로 병렬화 가능
	- $$h_t = (α_t A)(α_{t−1} A) ... (α₁ A) h₀  +  \left(\sum α_t α_{t−1} ... α_{k+1} A^{(t−k)}\right) (B_k u_k)$$
		- $\alpha_t$, $B_t$, $C_t$, $u_t$는 병렬 계산 가능
		- $h_0 = 0$ 으로 전이행렬 누적은 계산 불필요
		- prefix-scan 으로 누적합 병렬화 - 업스윕만 사용
- $\Delta$에 대한 안정화 - softplus