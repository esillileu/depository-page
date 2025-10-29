---
tags:
  - dictionary
  - programming_language/python
aliases:
  - 파이프로젝트
---
# pyproject.toml
> [[Python|파이썬]]의 프로젝트 정보 관리 표준
## 특징
- 프로젝트 메타 정보를 섹션에 따라 저장
	- `[build-system]:`빌드 시스템 정의
		- `requires `: 빌드 시 필요 패키지
		- `build-backend`: 빌드 백엔드
	- `[project]:프로젝트 메타 데이터
		- `name`
		- `version`
		- `description`
		- `dependencies`:의존성
	- `[tool.*]`:툴 설정