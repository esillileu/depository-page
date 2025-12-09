---
tags:
  - dictionary
  - ai/module
aliases:
  - ssm
---
# State Space Model
> [[Markov Chain|마르코프 연쇄]] 기반 상태 공간 모형
## 정의 
- ***상태 공간 모형***은 입력 $u$을 상태 $x$에 누적하고 이를 기반으로 출력 $y$를 생성하는 모델 
	- $$\begin{matrix}
&\dot x(t) = Ax(t) + Bu(t)\\
&y(t) = Cx(t)
\end{matrix}$$
- 샘플링 간격 $\Delta$에 대한 이산화 
	- $$\begin{matrix}
\dot x_{t+1} = \bar Ax_t + \bar Bu_t\\
y_t = Cx_t\\
\bar A = e^{A\Delta}\\\bar B = \int^\Delta_0e^{A(\Delta-\tau)}Bd\tau
\end{matrix}$$
## 특징
- 신호처리, 통계, 딥러닝에서 모두 사용하는 개념
- $A$, $B$로 상태 누적, $C$로 필터링
- 안정성
	- 입력이 없을 때 상태가 0으로 수렴
		- $$\dot x(t) = Ax(t) \to x(t) = e^{At}x(0)$$
	- $A$의 모든 고유 값의 실수부가 음수 
		- $$\operatorname {Re}(\lambda_i(A))<0$$
	- 안정성 보장 없을 때 단계 증가에 따라 상태 폭주
- 컨볼루션화 가능
	- 연속
		- $$y(t) = Ce^{At}x(0) + \int^t_0{h(t-\tau)u(\tau)d\tau} = (h*u)(t) $$$$h(t) = Ce^{A(t)}B$$
	- 이산
		- $$y_t = \sum^t_{k=0}{h_{t-k}u_k} = h*u$$
		- $$h_i = C\bar A^i\bar B$$
## 이산화 유도
- $$x(t+\Delta) = e^{A\Delta}x(t)+\left(\int^\Delta_0{e^{A(\Delta-\tau)}Bu(t+\tau)d\tau}\right) = \bar A x(t) + \bar B u(t)$$
- ZOH 적용
	- 
	- $$\bar B = \int^\Delta_0e^{A(\Delta-\tau)}d\tau$$
	- $$$$