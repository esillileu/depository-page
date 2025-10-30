---
tags:
  - dispatch
  - programming_language/python
---
# 제반 사항
- 파이썬 네이티브 환경 관리 툴의 단점
	- 패키지 관리 도구의 파편화 
		- 패키지 설치: [[pip]]
		- 패키지 빌드: setuptools
		- 패키지 배포 표준: wheel
		- 가상환경 관리: venv
	- 기존 [[pip]]의 단점
		- 부실한 의존성 관리로 충돌 위험이 높음
		- 느린 설치 속도
- 이를 통합하는 다른 외부 도구의 단점
	- conda - 무겁고 일부 패키지 호환 안됨, 의존성 해결 시 오류 존재
	- poetry - 무겁고 표준에서 일부 벗어남
	- pyenv - 파이썬 버전 관리만 지원, os의존
- 이상의 내용이 해결된 일원화된 프로젝트 관리 도구로 uv 제시
	- 기존 파이썬 네이티브 환경 관리 툴과 호환
		- [[pyproject.toml]]을 기반으로하는 의존성계산 및 고정으로 충돌 방지
	- rust 구현으로 빠른 설치 속도


# 과정 
## 1. 설치
- 리눅스/맥
	```bash 
	curl -LsSf https://astral.sh/uv/install.sh | sh
	# or
	wget -qO- https://astral.sh/uv/install.sh | sh
```
- 윈도우
	```bash
	powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
	```
- 설치 확인 
	```
	uv --version
	```
## 2. 사용
- 프로젝트 초기화
	- 루트 디렉토리에 [[Git]], [[pyproject.toml]], main.py, README.md, .python-version를 생성
	- `uv init [option] [path]`
		- `[option]`
			- `-p`: 파이썬 버전
			- `--package` : 추가 설치 패키지
		- `[path]`
			- 기본 값은 현재 디렉토리
- 패키지 추가 
	- [[pyproject.toml]]에 사용할 패키지 추가
	- `uv add [package-name]`
		- `[package][=<>][version]`: 패키지 버전 지정
			- `numpy>=1.4`
			- `pandas==1.2`
- 의존성 고정
	- [[pyproject.toml]]의 의존성을 기반으로 `uv.lock` 파일에 패키지 버전과 빌드 정고정
	- `uv lock`
- `uv.lock`을 기반으로 가상환경 생성
	- .venv에 가상환경 생성
	- `uv sync`
- 가상환경 활성화 
	- mac/linux - `source .venv/bin/activate`
	- window - `.venv/Scripts/activate`