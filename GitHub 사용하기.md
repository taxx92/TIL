# GitHub 사용하기

## 원격 저장소 사용하기

### 1. 로컬에 원격 저장소 추가 후 푸시

### GitHub 레포지토리 생성 후 복붙 명령어

```
git remote add origin (원격저장소 주소)
```

  * 로컬의 git 저장소에 원격 저장소로의 연결 추가

    * 원격 저장소 이름을 흔히 `origin` 사용. 다른 것으로 수정 가능
   
```
git branch -M main
```

  * GitHub 권장 - 기본 브랜치명을 `main`으로

```
git push -u origin main
```

  * 로컬 저장소의 커밋 내역들 원격으로 `push`(업로드)

    * `-u`또는 `--set-upstream` :현재 브랜치와 명시된 원격 브랜치 기본 연결

원격 목록 보기

```
git remote
```

  * 자세히 보기 : `git remote -v`

원격 지우기(로컬 프로젝트와의 연결만 없애는 것. GitHub의 레포지토리는 지워지지 않음)

```
git remote remove (origin 등 원격 이름)
```

---

### 2. GitHub에서 프로젝트 다운받기

  * download zip : 파일들만 다운받음, Git 관리내역 제외
  * Git clone : Git 관리내역 포함 다운로드

터미널이나 git bash에서 대상 폴더 이동 후

```
git clone (원격 저장소 주소)
```

---

## push와 pull

### 1. 원격으로 커밋 밀어올리기(push)

아래 명령어로 push

```
git push
```

 * 이미 `git push -u origin main`으로 대상 원격 브랜치가 지정되었기 때문에 가능

GitHub 페이지에서 파일들과 커밋내역 확인

### 2. 원격의 커밋 당겨오기(pull)

아래 명령어로 pull

```
git pull
```

로컬에서 파일과 로그 살펴보기

### 3. pull 할 것이 있을 때, push를 하면?

 * 원격에 먼저 적용된 새 버전이 있으므로 적용 불가
 * pull 해서 원격의 버전을 받아온 다음 push 가능

 * push 할 것이 있을 시 pull 하는 두 가지 방법

   * `git pull --no-rebase` - merge 방식
  
   * `git pull --rebase` - rebase 방식
  
### 4. 로컬의 내역 강제 push 해보기

아래 명령어로 원격에 강제 적용

```
git push --force
```

---

## 원격의 브랜치 다루기

### 1. 로컬에서 브랜치 만들어 원격에 push 해보기

1. `from-local` 브랜치 만들기

2. 아래 명령어로 원격에 push

```
git push -u origin from-local
```

3. 브랜치 목록 살펴보기

   * 아래 명령어로 로컬과 원격의 브랜치들 확인

     ```
     git branch --all
     ```

 ### 2. 원격의 브랜치 로컬에 받아오기

 1. GitHub에서 `reom-remote` 브랜치 만들기

     * `git branch -a`에서 현재는 보이지 않음
   
 2. 아래 명령어로 원격의 변경사항 확인

    ```
    git fetch
    ```

3. 아래 명령어로 로컬에 같은 이름의 브랜치를 생성하여 연결하고 switch

   ```
   git switch -t origin/from-remote
   ```

### 3. 원격의 브랜치 삭제

```
git push (원격이름) --delete (원격의 브랜치명)
```




---

참고강의 - [얄코(Yalco) <제대로 파는 Git & GitHub>](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
