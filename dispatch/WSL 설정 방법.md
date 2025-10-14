---
tags:
  - dispatch
---
# 서담
- 윈도우 사용과 리눅스 기반 개발 환경을 동시에 갖추기 어려움
	- 멀티 부팅 등의 대안이 있으나, 처음부터 리눅스 사용이 아니라면 어려움
- 윈도우에서 [[Hypervisor|하이퍼바이저]]를 이용해 지원하는 [[Windows Subsystem Linux|wsl]]을 사용하는것이 유용함

# 본담
## 과정
### 1. windows 기능 켜기/끄기`에서 다음 체크 후 재시작
- `Hyper-V`
- `Linux용 Windows 하위 시스템`
- `Virtual Machine Platform`

 ## 2. wsl 및 배포판 설치
- 터미널에서 다음 실행 
	```powershell
	wsl --update
	wsl --list --online 
	wsl --install [release_name]
	```

### 3. wsl 실행
- 원하는 디렉토리에서 다음을 실행
```powershell
wsl
```

# 종담
- wsl은 마운트를 통해 윈도우 드라이브의 파일에도 접근 가능하다. 보통 [[ln|심볼릭 링크]]를 통해 간단히 접근하도록 설정한다. 
- 환경 분리에 매우 유용하다. 여차하면 `wsl --unregister`로 통째로 날리고 다시 해도 된다. 단, 이경우 리눅스 내 모든 파일 날아가니 주의 

# 한담
- 모든 작업환경 세팅이전에 wsl을 설정하는 편이다. 파이썬도 그렇고 리눅스환경이 더 편하기 때문에.