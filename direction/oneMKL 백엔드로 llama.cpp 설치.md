---
tags:
  - dispatch
---
# 제반 사항
- llama.cpp
	- cpu에서 언어 모델을 구동하기 위해서는 llama.cpp를 로컬에 설치 해함 
		- 다른 오픈소스 프레임워크가 있었던거 같은데 기억이 안남
	- llama.cpp는 c, c++ 로 구성되어있어 인텔 cpu 최적
	- 추가적인 성능 개선을 위해 BLAS를 고려할 수 있음
		- 여기서는 인텔의 oneMKL의 BLAS를 이용해 intel cpu 최적으빌드하고자 함
- oneMKL
	- 인텔의 oneAPI Base Toolkit 내의 수치 연산 라이브러리
	- BLAS 포함
	- 인텔 cpu에서 BLAS를 이용한 최적 연산 가능
	- 정적 빌드 제한됨 - 의존 부분 복사해올 필요 있음
- docker
	- oneAPI Base Toolkit 의 설치 및 설정이 번거로우므로, 도커 컨테이너를 사용하여 정적으로 llama.cpp을 빌드 하고자 함 
	- 도커가 설치되어있어야 함. 
		- 윈도우의 경우, wsl 설정이 되어있어야 함
		- wsl 내에서 도커를 설치하는 경우 - [[WSL내에 Docker 설치 방법]] 참조
# 과정 
## 1. 레포지토리 클론 및 이동
```bash
git clone https://github.com/ggml-org/llama.cpp.git
```
## 2. 도커 컨테이너 실행 
- llama.cpp 디렉토리를 workspace 볼륨으로 마운트
```bash
image=intel/oneapi-basekit 
docker pull "$image"
docker run -it --rm -v $(llama.cpp):/workspace intel/oneapi-basekit bash
```
## 3. curl 설치
```bash
apt update -y && apt upgrade -y && apt install libcurl4-openssl-dev
```
