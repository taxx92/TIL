# 🔑차원 넘나들기

## 여러 branch 만들어보기

![branches](https://github.com/user-attachments/assets/dd2b83e6-6f51-4868-aa9a-8655408c89a7)

### **branch** : 분기된 가지 (다른 차원)

* 프로젝트를 하나 이상의 모습으로 관리해야 할 때

  * 예) 실배포용, 테스트서버용, 새로운 시도용

* 여러 작업들이 각각 독립되어 진행될 때

  * 예) 신기능 1, 신기능 2, 코드개선, 긴급수정

  * 각각의 차원에서 작업한 뒤 확정된 것을 메인 차원에 통합
 

이 모든 것을 하나의 프로젝트 폴더에서 진행 할 수 있도록

---

### 1. 브랜치 생성 / 이동 / 삭제하기

브랜치 생성

```
git branch (브랜치명)
```

브랜치 목록 확인

```
git branch
```

`tax` 브랜치로 이동

```
git branch tax
```

### 브랜치 생성과 동시에 이동하기

```
git switch -c (브랜치명)
```

### 브랜치 삭제하기

```
git branch -d (삭제할 브랜치명)
```

### 브랜치 이름 바꾸기

```
git branch -m (기존 브랜치명) (새 브랜치명)
```

---
## branch를 합치는 두 가지 방법

### 서로 다른 브랜치를 합치는 두 방식

 * **merge** : 두 브랜치를 한 커밋에 이어 붙인다.

   * 브랜치 사용내역을 남길 필요가 있을 때 적합한 방식

 * **rebase** : 브랜치를 다른 브랜치에 이어 붙인다.

   * 한 줄로 깔끔히 정리된 내역을 유지하기 원할 때 적합

   * 이미 팀원과 공유된 커밋들에 대해서는 사용하지 않는 것이 좋다.   

---
## branch 합치기

### 1. **merge**로 합치기

`tax`브랜치를 `main` 브랜치로 merge

  * `main`브랜치로 이동

  * 아래의 명령어로 병합

```
git merge tax
```

  * `:wq`로 자동입력된 커밋메시지 저장하여 마무리

### `merge`는 `reset`으로 되돌리기 가능

 * `merge`도 하나의 커밋
 * `merge`하기 전 해당 브랜치의 마지막 시점으로

### 병합된 브랜치는 삭제

```
git branch -d tax
```

---

### 2. **rebase**로 합치기

`dev`브랜치를 `main`브랜치로 rebase

  * `dev`브랜치로 이동

    * ✨`merge`때와는 반대
   
  * 아래의 명령어로 병합

```
git rebase main
```

  * `main`브랜치로 이동 후 아래 명령어로 `dev`의 시점으로 **fast-forward**

```
git merge dev
```

  * `dev`브랜치 삭제

---

## 충돌 해결하기

당장 충돌 해결이 어려울 경우 아래 명령어로 중단

```
git merge --abort
```

```
git rebase --abort
```

해결 가능시 충돌 부분을 수정한 뒤 `git add .`

아래 명령어로 계속

```
git rebase --continue
```

---

참고강의 - [얄코(Yalco) <제대로 파는 Git & GitHub>](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)

