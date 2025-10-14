---
tags:
  - dictionary
  - linux
aliases:
  - 쉬뱅
---
# Shebang
> 파일 실행을 위한 인터프리터를 지정하는 문법
## 사용
`#!<interpreter_path> [optional-arg]`
+ `<interpreter_path>` - 인터프리터의 절대 경로 
	+ `/bin/bash`
	+ `/bin/python`
	+ `/usr/bin/env` - 환경 변수에서 추가 인자 명령어 찾기 
+ `[optional-arg]`
	+ 한 개 인자만 안전하게 지원
	+ 각 인터프리터 별 인자 사용