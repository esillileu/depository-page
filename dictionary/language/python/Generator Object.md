---
tags:
  - dictionary
  - programming_language/python
aliases:
  - 제너레이터 객체
---
# Generator Object
> 파이썬의 [[Generator|제너레이터]]
## 특징
+ [[Yield Statement|yield]] 키워드가 정의된 함수의 실행으로 생성
+ `__next__`나 `<generator>.send(<value>)`에 의해 다음 [[Yield Statement|yield]] 까지 실행
	+ [[Yield Statement|yield]]를 전달 받은 값으로 환원
	+ 실행 [[Context|컨텍스트]] 저장
	- [[Yield Statement|yield]] 값 반환
- 더 이상 반환할 수 없으면 `StopIteration`에러 [[Raise Statement|raise]]