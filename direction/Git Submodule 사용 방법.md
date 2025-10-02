---
tags:
  - dispatch
---
# 제반 사항
- [[Submodule]]
	- [[Repsitory|레포]]안에서 다른 레포의 내용을 가져와서 관리
	- 편의상 다음 용어 사용
		- 부모 레포(`parent_repo`) - 다른 레포를 가져온 레포
		- 서브모듈 레포(`submodule_repo`) - 다른 레포에 포함된 레포
	- 레포 내 특정 경로가 다른 레포의 특정 커밋 해시를 가리키게 함
		- 추가 시 자동으로 최신 커밋 지정
			- 브랜치 지정 없으면 기본 브랜치 최신 커밋
		- 따로 업데이트 하지 않는 한 불변
	- 서브모듈로써 관리하는 정보는 부모 레포의 `.git/config`에 저장


# 초기 설정
## 1. 부모 레포와 자식 [[Github Repository 생성 방법|레포 생성]]
## 2. [[Local Repository|로컬 레포]]로 부모 레포 클론 
```bash
git clone <parent_repo_git_url>
cd <parent_repo>
```
+ [[Github]]에서 `git_url`은 레포 첫 화면의 code 버튼에 있음
	+ https - 로그인된 계정으로 자동으로 토큰 생성
	+ ssh - 별도 ssh 설정 필요
## 3. 서브 모듈 추가 및 [[Remote Repository|원격 레포]]에 반영
```bash
git submodule add [-b <branch_name>] <submodule_repo_url> <submodule_path>
git add .
git commit -m "add submodule content"
git push origin main
```
+ `-b <branch_name>`
	+ 따라갈 브랜치 지정 
	+ 생략 가능 - 생략 시 최신 커밋 해시 따라감
+ `<submodule_path>` - 서브모듈을 등록할 경로
	+ 실행 시 자식 레포의 내용을 해당 경로에 클론


# 사용
## 1. 다른 환경에서 [[Local Repository|로컬 레포]] 시작 시
```bash
git clone <parent_repo_git_url>
cd <parent_repo>

git submodule init     # 서브모듈 정보 등록
git submodule update   # 등록된 정보를 바탕으로 서브모듈 클론
```
+  위 둘을 합쳐 아래 명령어도 가능
```bash
git submodule update --init
```
## 2. 서브 모듈 업데이트
```bash
git submodule update --remote [--merge|--rebase] [--recursive]

# 커밋
git add <submodule_path>
git commit -m "upd submodule"
# 원격으로 푸시
git push origin main
```
+ `--remote` - 지정 브랜치(없으면 기본 브랜치) 최신 커밋으로 업데이트
	+ 병합 옵션 없으면 체크아웃
+ 병합 옵션
	+ `--merge` - 로컬 브랜치에 대해 원격 브랜치를 머지
	+ `--rebase` - 로컬 커밋을 원격 브랜치에 리베이스
+ `--recursive` - 하위 서브 모듈 전부에 대해 업데이트
## 3. 서브모듈 설정 변경

```bash
# 서브모듈 주소 변경 시
git submodule set-url <submodule_path> <new_url>  
# 서브모듈 추적 브랜치 변경시 
git submodule set-branch -b <branch> <submodule_path>

# 이후 반드시 동기화 
git submodule sync

# 커밋
git add <submodule_path>
git commit -m "upd submodule setting"
# 푸시
git push origin main
```

# 서브모듈 레포 업데이트
## 부모 레포 밖에 있는 서브모듈의 [[Local Repository|로컬 레포]] 
+ 스테이징된 작업사항 모두 푸시
	```bash
	git add . 
	git commit -m "add all"
	git push origin main
	```
+ 부모 레포에서 [[Git Submodule 사용 방법#2. 서브 모듈 업데이트|서브모듈 업데이트]] 
## 부모 레포 안에 add/init 으로 시작된 서브모듈 레포 
+ 부모 레포에서 서브모듈 경로로 이동 후 작업
```bash
cd <submodule_path>
```
+ 작업 종료 후는 위와 동일
# 삭제 
```bash
git submodule deinit -f <submodule_path> # 등록 취소
git rm -f <path>                         # git 추적 취소
rm -rf .git/modules/<submodule_path>               # 로컬 메타데이터 삭제

# 커밋
git add <submodule_path>
git commit -m "rm submodule"
# 푸시
git push origin main
```
