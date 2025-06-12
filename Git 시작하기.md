# 🔥Git 시작하기

## Git을 배워야 하는 이유
  1. Git은 프로젝트의 **시간**과 **차원**을 넘나들수 있게 해준다.
     
     * 시간 - 프로젝트의 버전을 과거로 되돌리거나 특정 내역을 취소 할 수 있다.
     * 차원 - 프로젝트의 여러 모드를 쉽게 전환하고 관리 할 수 있다.
       
  2. Git은 여러 사람들이 프로젝트에서 협업 할 수 있도록 도와준다.


---

## 설치와 세팅(윈도우)

### 1. Git 설치

 * https://git-scm.com/ 로 이동해서 Git을 다운로드
 * 설치과정에서 **Git Bash**를 반드시 포함하기
   * Git 사용에 적합한 터미널
   * 리눅스/맥(유닉스)에서 사용되는 CLI 명령어들을 윈도우에서 사용 가능 - 타 프로그래밍에도 유용


#### 아래 명령어 한 번 입력하기
```
git config --global core.autocrlf true 
```
 * 협업시 윈도우와 맥에서 엔터 방식 차이로 인한 오류를 방지할 수 있음

### 2. SourceTree 설치
* https://www.sourcetreeapp.com/ - Git을 GUI로 다룰 수 있도록 해주는 툴

### 3. VS Code 설치
* https://code.visualstudio.com/ - 가장 인기있는 코드 에디터 중 하나

### 4. VS Code의 기본 터미널을 Git Bash로 설정
* VS Code에서 ``ctrl`` + ``shift`` + ``p``
* ``Select Default Profile`` 검색하여 선택
* **Git Bash** 선택

---

## CLI VS GUI
### Git을 사용하는 방법은 둘로 나뉜다
  * 터미널에 명령어를 이용하는 CLI 방식
  * 소스트리 등의 프로그램을 사용하는 GUI 방식

---

## Git설정 & 프로젝트 관리 시작하기

### 1. Git 최초 설정
#### Git 전역으로 사용자 이름과 이메일 주소를 설정
  * GitHub 계정과는 별개

Git Bash에서 아래 명령어 실행

```
git config --global user.name "(본인 이름)"
```

```
git config --global user.email "(본인 이메일)"
```

아래의 명령어들로 확인하기

```
git config --global user.name
```

```
git config --global user.email
```

### 2. 프로젝트 생성 & Git 관리 시작

적당한 위치에 원하는 이름으로 폴더를 생성하고 **VS Code**로 열람

해당 폴더에서(VS Code 터미널 기본) 아래 명령어 입력

```
git init
```

폴더에 숨김모드로 **.git** 폴더 생성 확인
  * 이 폴더를 지우면 Git 관리내역이 삭제된다.


---

출처 - [얄코의 Git 강의](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-%EA%B9%83/dashboard)
