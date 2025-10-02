---
tags:
  - dictionary
  - programming_language/python
  - programming_language/python/keyword
aliases:
  - with 문
---
# With Statement
> [[Block|블록]]을 [[Context Manager|컨텍스트 매니저]]의 [[Context|컨텍스트]]안에서 실행하는 [[Statement|문]]

## 사용
+ `with <context_manager>` - 이하 원하는 블럭만큼 [[Indentation|인덴테이션]]
## 특징
+ [[Block|블록]] 의 시작과 종료에 다음 메서드를 실행
	+ 시작 - `<context_manager>.__enter__()`
	+ 종료 - `<context_manager>.__exit__()`
+ [[Scope|스코프]]를 생성하지 않음 
	+ 내부에서 [[Binding|바인딩]]한 [[Identifier|식별자]] 지속
	+ [[Context Manager|컨텍스트 매니저]] 지속 - 내부 [[Context|컨텍스트]] 소멸