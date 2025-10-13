---
tags:
  - dictionary
  - programming_language/python
aliases:
---
# LEGB
> [[Python|파이썬]]의 [[Scope|스코프]]지정 규칙
## 특징
+ 파이썬의 [[Identifier|식별자]]는 다음 순서로 검색된다
	+ Local - 현재 실행중인 함수 내의 스코프
	+ Enclosing - 바로 바깥 함수들의 스코프
	+ Global - 모듈 전체의 스코프
	+ Built-in - 파이썬 내장 식별자
+ 하위 스코프에서 상위 스코프의 식별자 사용 시 [[Name Shadowing|섀도잉]] 발생