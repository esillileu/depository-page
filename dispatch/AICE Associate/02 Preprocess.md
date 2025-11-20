---
tags:
  - dispatch
---
> 이전글 : [[01 EDA]]
---
# 서담
- 데이터 전처리는 원본 데이터를 학습에 적합한 형태로 변환하는 과정임
	- 데이터 정리 
	- 결측치 및 이상치의 처리
	- 범주형 데이터 처리 - 라벨 및 원핫 인코딩 
	- 단위 변환 - 열 단위 계산으로 처리
	- 데이터 정제 - 문자열 등의 복합 데이터 처리 
	- 정규화 
- AICE에서는 다음 과정을 지칭함
	- X,Y 데이터 분리 - 분류상 학습에서 다룸
	- 데이터 결측치 처리 
	- 인코딩 - 라벨, 원핫 
	- 데이터 정규화, 표준화
# 본담
## 데이터 정리 
### 컬럼명 & 인덱스명 정리
```python
df.rename(columns={'old': 'new'}, inplace=True) # 컬럼명 수정
df.rename(index={0: 10}, inplace=True) # 인덱스 수정

df.columns = ['a', 'b', 'c']
df.index = ['x', 'y', 'z']

df.index.name = 'a' # 인덱스 컬럼명 이름 지정
```
### 열/행 삭제
```python
# drop은 변경된 데이터 프레임을 반환함
# - 원본 데이터 프레임 변경하지 않음
# - 단계마다 다른 식별자에 바인딩하는걸 권장
# 지정 축의 Index 객체에서 값을 검색하여 제거 
df = df.drop([a, b, c]) # 특정 행 삭제 - axis = 0 기본
df.drop(['A', 'B', 'C'], axis = 1) # 특정 열 삭제  - 컬럼 명으로만 가능
df.drop(['A', 'B', 'C'], inplace = True) # 원본 변경
```
### 타입 변환 
```python
df['A'] = df['A'].astype('int')       # 정수 컬럼 - 8, 16, 32, 64
df['A'] = df['A'].astype('float')     # 실수 컬럼 - 16, 32, 64
df['A'] = df['A'].astype('bool')      # 부울 컬럼
# 이하 컬럼은 학습에 사용 불가하므로 변환 필요 - 검증 및 최적화용
df['A'] = df['A'].astype('object')    # 객체 컬럼
df['A'] = df['A'].astype('string')    # 문자열 컬럼
df['A'] = df['A'].astype('category')  # 카테고리 컬럼
df['A'] = df['A'].astype('datetime[ns, <tz>]')  # 시각 컬럼
df['A'] = df['A'].astype('interval')  # 시간 간겯컬럼
df['A'] = df['A'].astype('period[<freq>]')    # 주기 컬럼
df['A'] = df['A'].astype('Sparse')    # 희소 컬럼
```
## 이상치 / 결측치 처리 
### 결측치 채우기
```python
df.fillna(value, method, axis, inplace, limtit)
# value - {'컬럼명':'채울 값'} 또는 그냥 값으로 전체 채움
# method - 'ffill'로 전 값, 'bfill'로 후 값으로 채움 - value와 같이 못씀
# axis - 채울 방향 
# limit - 연속 결측치중 최대 몇개만 채울지
```
### 이상치 클리핑
```python
df['A'] = df['A'].clip(lower_bound, upper_bound)
```
### 값 변경
```python
df.replace('prev', 'post') # inplace 적용 가능
df.replace({'prev1':'post1', 'prev2':'post2'}) # 딕셔너리 가능
```
## 범주형 데이터 처리 
```python
# pandas 네이티브
df['col'].map({'A': 0, 'B': 1}) # 라벨 인코딩
df_dummy = pd.get_dummies(df, columns=cols) # 원핫 인코딩
# 원핫인코딩 컬럼을 추가한 DataFrame 반환  

# sklearn
from sklearn.preprocessing import LabelEncoder, OneHotEncoder

# 라벨 인코딩
# 라벨을 인덱스 순서대로 탐색하며 0부터 순서대로 부여
label_encoder = LabelEncoder()
df['C'] = label_encoder.fit_transform(df['C']) 

# 원핫 인코딩
# 인코딩 결과를 ndarray로 반환 
onehot_encoder = OneHotEncoder(sparse=False) # True 일때는 SparseMatrix 반환 
encoded = onehot_encoder.fit_transform(df[['D']]) # 입력은 2차원이여야함
feature_names = onehot_encoder.get_feature_names_out(['D'])
df_en = pd.DataFrame(encoded, columns = feature_names) 
```

## 표준화, 정규화 
- 표준화 - 표준 정규분포로 값 제한 
- 정규화 - 특정 범위로 값 제한
	- minmax - `[0, 1]`
	- maxabs - `[-1, 1]`
```python
# pandas 네이티브
# 수치 데이터 열만 골라서 해야함 
df = (df - df.mean()) / df.std() # 표준화 
df = (df - df.min()) / (df.max() - df.min()) # 정규화 - minmax 스케일링

# sklearn
from sklearn.preprocessing import MinMaxScaler, MaxAbsScale, StandardScaler
# .fit_transform - fit과 transform 동시 적용 : 스케일러 업데이트
# .transform - 스케일러에 저장된 기준에 따라 transform 적용
# 스케일러 입력은 모두 2D

# minmax scaling - normalization
minmax_scaler = MinMaxScaler() 
x_train_minmax = minmax_scaler.fit_transform(X_train)
x_test_minmax = minmax_scaler.transform(X_test) 

# max abs scaler - normalization
maxabs_scaler = MaxAbsScale() 
x_train_maxabs = maxabs_scaler.fit_transform(X_train) 
x_test_maxabs = maxabs_scaler.transform(X_test) 

# standard scaling - standardization
std_scaler = StandardScaler() 
x_train_std = std_scaler.fit_transform(X_train) 
x_test_std = std_scaler.transform(X_test)

```

# 종담
- 


# 한담
- 


---
> 다음글 :
