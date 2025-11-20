---
tags:
  - dispatch
---
> 이전글 : [[00 AICE Associate]]
---
# 서담
- [[EDA]]는 데이터를 다각도에서 관찰하여 이해를 높이고 분석 아이디어를 잡는 과정임
	- 메타데이터, 통계값, 샘플링, 시각화를 통해 데이터 확인
		- 메타데이터는 데이터에 포함되어있지 않은 경우가 많음 - 데이터 소스에서 확인해야함
			- 컬럼 정보, 값 의미, 단위 등
- AICE에서는 다음 과정을 지칭함
	- 분석 준비
		- 라이브러리 설치 및 임포트
		- tabular 데이터 로드
	- 데이터 탐색
		- 구성 확인 
		- 상관 분석
	- 시각화 


# 본담
## 준비
### 라이브러리 설치 및 임포트
```python
import numpy as np 
import pandas as pd 
import sklearn as sk # !pip install scikit-learn
import seaborn as sns # !pip install seaborn 
import matplotlib.pyplot as plt
```
### 데이터 로드
```python
df = pd.read_csv('') 
df = pd.read_excel('') # openpyxl 필요할 수 있음
dj = pd.read_json('') 
dx = pd.read_xml('')
```

## 데이터 탐색
### 구성 확인인
```python
# 데이터 확인 
df.index      # 인덱스 값을 Index 객체로 반환
df.colums     # 컬럼명을 Index 객체로반환 
df.values     # 모든 인스턴스 값을 2차원 array로 반환 

# 인덱스 샘플링
df.head(n)    # 맨 앞 n개의 인스턴스를 DataFrame으로 반환 
df.tail(n)    # 맨 뒤 n개의 인스턴스를 DataFrame으로 반환

# 컬럼 샘플링
df.select_dtype(include = 'object') # 특정 타입의 컬럼만 DataFrame으로 반환 
df.select_dtype(exclude = 'object') # 특정 타입의 컬럼 제외 DataFrame으로 반환

df.info()     # 반환 없음 - 데이터셋에 대한 요약 정보 출력
```
### 통계값 확인
```python
df.max()      # 컬럼별 최댓값을 Series로 반환
df.min()      # 컬럼별 최솟값을 Series로 반환

df.mean()     # 컬럼별 평균값을 Series로 반환
df.std()      # 컬럼별 표준편차값을 Series로 반환

df.describe() # 주요 통계값을 DataFrame으로 반환
```
### 인덱싱 & 슬라이싱
```python
df['a'] # 컬럼 인덱싱

df.loc[index, column] # 라벨 기반 인덱싱
df.loc[i1:i2, c1:c2]  # 라벨 기반 슬라이싱

df.iloc[1, 2]         # 정수 기반 위치 인덱싱
df.iloc[1:2, 2:3]     # 정수 기반 위치 슬라이싱

df[df['A']>3]         # 불리언 인덱싱 - TF 시리즈 기반 T인 행만 반환 

df.loc[[1, 2], ['A', 'B']] # 팬시 인덱싱 - 전달한 이터러블 객체 값에 해당하는 인덱스를 가지는 행/열 슬라이싱
```
### 개수와 빈도 확인
```python
# 데이터 프레임 전체에 적용하면, 모든 속성이 같을 때만 카운트함
df['A'].value_count()
df['B'].value_count(normalized = True) # 비율로 표시
```
### 결측치 확인 
```python
# 완전히 동일하게 기능
# 모든 인스턴스의 값을 TF 로 변경
# sum으로 컬럼별 합산 
df.isna().sum()
df.isnull().sum()
```

## 시각화 
### seaborn
```python
sns.histplot(x='', hue='', data=df) # 지정 컬럼명으로 히스토그램 작성
sns.kdeplot(df['A']) # kde 플롯 작성
sns.countplot(x='', data=df) # 빈도 플롯
sns.boxplot(x='', y='', data=df) # 박스플롯
```
### DataFrame 내장
- 인덱스에 대한 수치형 데이터 표현
```python
df.plot() # 선그래프 
df.plot(kind='bar') # 막대 그래프
df.plot(kind='hist') # 히스토그램
df.plot(kind='box') # 박스 그래프
df.plot(kind='scatter', x='', y='') # 산점도
```
# 종담
- 인덱싱과 슬라이싱은 이후 과정에서도 기본으로 사용
- 시각화 목적에 따른 그래프 선택법 숙달 필요


# 한담
- 
---
> 다음글 : [[02 Preprocess]]
