---
tags:
  - dictionary
aliases:
---
# Submodule
> 현재 저장소 안에 포함된 다른 [[Repsitory|레포]]
## 특징
- 독립 레포이기에 버전 고정 가능
- 부모 레포와 별개 관리
- 커밋 해시로 고정 - 브랜치 기반 접근이 아님
## 사용
```bash
git submodule add <repo_url> <path>
```