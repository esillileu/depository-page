---
tags:
  - dictionary
  - programming_language/python/packages
aliases:
---
# pip
> [[Python|파이썬]] 패키지 관리자
## 특징
- pip는 파이썬 패키지
	- 인터프리터에 종속적
	- 각 가상환경마다 pip 존재 가능
- 의존성 검사 및 빌드
	- 메타데이터 확인
	- 의존성 충돌 검사 
	- 빌드
- 파이썬 패키지 설치 
	- 등록된 인덱스에서 패키지 이름을 검색
		- 기본 값 PyPI
		- 다른 인덱스 등록 가능
	- pip가 실행된 파이썬 인터프리터 경로의 site-packages에 패키지 설치
## 문제점
- 설치하려는 패키지에 맞춰 현재 패키지를 덮어 씀
	- 기존 패키지와의 의존성 충돌 