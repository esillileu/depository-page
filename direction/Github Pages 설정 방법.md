---
tags:
  - service/github-pages
  - direction
  - service
---
# 제반 사항
- [[Github Pages]] 
	- [[Github]]에서 제공하는 [[Static site|정적 사이트]] 배포 서비스
	- [[Github]] 계정 필요 
	- 댓글 등의 서버 연산 불가
	- 사이트 도메인
		- `https://{github_id}.github.io/{repo_name}` 
		- [[Repsitory|레포]] 이름을 `{github_id}.github.io`로 지정하는 경우 -  `https://{github_id}.github.io`
		- 커스텀 도메인 있을 경우 지정 가능


# 과정 
## 1. [[Github Repository 생성 방법|Github Repository 생성]] 

## 2. 설정(settings) > 우측패널 > Code and automation > pages 
- source
	- deploy from branch - 기본값. Jekyll 기반 마크다운 배포 시
	- Github Action - 기타 정적 사이트 생성기로 배포 시
- branch
	- 배포할 [[Branch|브랜치]] 지정
	- 폴더 지정
		- `/(root)` - 프로젝트 루트를 기반으로 배포 (레포 전체를 배포)
		- `/docs` - docs 폴더를 배포(프로젝트 소개나 설명 등을 배포)
	- 이후 저장(save)

## 3. 잠시 기다리면 사이트 배포
	- Actions 탭에서 진행 사항 확인 가능