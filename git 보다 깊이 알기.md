# git 보다 깊이 알기

## git의 3가지 공간

![image](https://github.com/user-attachments/assets/e1fe7c03-c75b-4089-94ba-6ead55ec2c47)

### Working directory

  * untracked : Add된 적 없는 파일, ignore 된 파일
    
  * tracked : Add된 적 있고 변경내역이 있는 파일

  * `git add` 명령어로 Staging area로 이동

### Staging area

  * 커밋을 위한 준비 단계

  * `git commit` 명령어로 repository로 이동

### Repository

  * `.git directory`라고도 불림

  * 커밋 된 상태

### 파일을 `staging area`에서 `working directory`로

```
git restore --staged (파일명)
```

  * `--staged`를 빼면 `working directory`에서도 제거

### reset의 세 가지 옵션

  * --soft : `repository`에서 `staging area`로 이동

  * --mixed (default) : `repository`에서 `working directory`로 이동

  * --hard : 수정사항 완전히 삭제

---

## HEAD

![image](https://github.com/user-attachments/assets/d125f878-e076-4deb-ae58-b233731b805c)

### Git의 HEAD

현재 속한 브랜치의 가장 최신 커밋

 * switch로 브랜치 이동 가능

`checkout`으로 앞뒤 이동해보기

```
git checkout HEAD^
```

 * `^`또는 `~` : 갯수만큼 이전으로 이동

    * `git checkout HEAD^^^^^`, `git checkout HEAD~5`
  
 * 커밋 해시이용 이동 가능

    * `git checkout (커밋해시)`
  
 * `git checkout - ` : (이동을) 한 단계 되돌리기

### HEAD 사용하여 reset하기

```
git reset HEAD(원하는단계) (옵션)
```

---

## fetch vs pull

### fetch와 pull의 차이

* `fetch` : 원격 저장소의 최신 커밋을 로컬로 가져오기만 함

* `pull` : 원격 저장소의 최신 커밋을 로컬로 가져와 `merge` 또는 `rebase`

  

---

참고강의 - [얄코(Yalco) <제대로 파는 Git & GitHub>](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
