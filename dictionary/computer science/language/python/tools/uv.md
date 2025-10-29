---
tags:
  - dictionary
  - programming_language/python
aliases:
---
# uv
> 러스트로 구현된 파이썬 패키지 관리자
## 특징
- 러스트로 구현
	- 매우 빠른 속도
- 파이썬 네이티브 환경 관리 도구 사용
	- [[pyproject.toml]]
	- [[venv]]
	- [[pip]]
## 사용 흐름
- 프로젝트 시작 - `uv init`
- [[pyproject.toml]]에 의존성 추가
	- `uv add`
	- 직접 작성 가능
- 프로젝트 의존성 계산 및 고정 
	- `uv lock`
	- `uv.lock` 파일 생성
- `uv.lock`을 기반으로 가상환경 생성 및 업데이트
	- `uv sync`
	- 하드링크를 통해 중복 저장 방지 