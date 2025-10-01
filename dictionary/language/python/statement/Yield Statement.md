---
tags:
  - dictionary
  - programming_language/python
  - programming_language/python/keyword
aliases:
  - yield
---
# Yield Statement
> [[Generator|제너레이터]]의 값을 반환하거나 받아오는 [[Statement|문]] 
## 상세
+ `yield`가 포함된 함수는 [[Generator Function|제너레이터 함수]]로 정의
+ `yield`는 평가 시작 시에 호출자로 값을 반환하고 [[Context|컨텍스트]]를 저장
+ 재실행시에 이전 `yield`를 주입된 값으로 평가 
## 사용
- `yield <value>` 
	- 현재 실행 [[Context|컨텍스트]]를 저장하고 값을 호출자로 반환 
	- 재실행시 주입받은 값으로 환원
- `yield from <iterator>` - [[Generator|제너레이터]] 위임
	- 현재 실행 [[Context|컨텍스트]]를 저장하고 이터레이터의 `__next__()`값을 호출자로 반환 
	- 이터레이터 종료시 이터레이터의 반환 값으로 환원