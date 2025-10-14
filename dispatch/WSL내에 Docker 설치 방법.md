---
tags:
  - dispatch
---
# 서담
- Docker는 가장 널리 사용되는 컨테이너 관리 도구
	- 환경 격리와 재현에 뛰어남
	- 현재는 여러모로 밀려나고 있다는 느낌이 강함
		- 보안이슈
		- 데몬기반 메모리 누수 
- [[Windows Subsystem Linux|wsl]]이 설정되어있어야 함
	- [[WSL 설정 방법]] 참고

# 본담
## 과정
### 1. wsl 실행
```powershell
wsl
```
### 2. 다음 스크립트 실행
```bash
# 패키지 최신화
sudo apt update -y
sudo apt upgrade -y

# 선행 패키지 설치
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

# 도커 파일 다운 및 설정
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# 패키지 업데이트 및 도커 설치
sudo apt update -y
sudo apt install -y docker-ce docker-ce-cli containerd.io

# 권한 부여
sudo usermod -aG docker $USER
sudo service docker start

```


# 종담
- 


# 한담
- 
---
> 다음글 :
