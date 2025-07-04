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

참고강의 - [얄코(Yalco) <제대로 파는 Git & GitHub>](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
