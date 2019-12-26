# Git

> Git은 분산버전관리시스템(DVCS)이다.  cf)객체지향프로그램?파이썬
>
> 소스코드의 버전 및 이력을 관리할 수 있다. 

## 준비하기

윈도우에서  git을 활용하기 위해서 [git bahs](https://gitforwindwos) 를 설치한다.

git을 활용하기 위해서  GUI 툴인 `source tree` ,`git hub`, `dest top`등을 활용할 수 있다.

초기 설치를 완료한 이후에 컴퓨터에 `author`정보를 입력한다. 이메일 정보를  git hub에 가입된 이메일로 일치시켜야 커밋 입출력이 관리된다.

```bash
$ git config --global user.name hui-yeon
$ git config --global user.email huiyeon27@gmail.com
```

# 로컬 저장소(repository) 활용하기

### 1. 저장소 초기화

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/
(master) $
```

* `.git`폴더가 생성되며, 여기에 git과 관련된 모든 정보가 저장된다. 

* git bahs에 `(master)`라고 표현되는데, 이를 `master`브랜치에 있다는 뜻이다. 

### 2. add

`working directory`, 즉 작업 공간에서 변경된 사항을 이력으로 저장하기 위해서는 반드시 `staging area`를 거쳐야 한다.

```bash
$ git add markdown.md #특정 파일
$ git add images/ # 특정 폴더
$ git add . #현재 디렉토리
```

* `add`전 상태

  ```bash
  $ git status
  On branch master
  
  No commits yet
  
  # 트래킹 되고 있지 않는 파일들
  # => commit 이력에 한번도 담기지 않은 파일들
  Untracked files:
  # 커밋될 것들에 포함시키려면 add 명령어를 사용 해
    (use "git add <file>..." to include in what will be committed)
          git.md
          images/
          markdown.md
  
  # 아직 커밀 될 것들은 없지만, 
  #untracked files은 존재한다. 
  nothing added to commit but untracked files present (use "git add" to track)
  ```

* `add` 후 상태

  ```bash
  $ git add images/
  $ git status
  On branch master
  
  No commits yet
  # 커밋될 변화들
  # => staging area에 있는 파일들
  Changes to be committed:
    (use "git rm --cached <file>..." to unstage)
          new file:   images/test.png
  
  Untracked files:
    (use "git add <file>..." to include in what will be committed)
          git.md
          markdown.md
  
  ```

### 3. `commit`

commit은 이력을 확정짓는 명령어로, 해당 시점의 스냅샷을 기록한다. 

커밋시에는 반드시 메세지를 작성 해야하며, 메세지는 변경사항을 알 수 있도록 명확하게 작성한다. 

```bash
$ git commit -m '마크다운 및 git 정리'

[master (root-commit) 02dcc38] 마크다운 및 git  정리
 4 files changed, 100 insertions(+)
 create mode 100644 git.md
 create mode 100644 images/test.png
 create mode 100644 markdown.md

```

커밋 이후에는 아래의 명령어를 통해 지금까지 작성된 이력을 확인하자.

```bash
$ git log
commit 02dcc384d229e4ee503dad7c0a0d2ce51be2e80f (HEAD -> master)
Author: hui-yeon <huiyeon27@gamil.com>
Date:   Thu Dec 26 14:35:34 2019 +0900

    마크다운 및 git  정리

student@M50418 MINGW64 ~/Desktop/TIL (master)
$ git log --oneline
02dcc38 (HEAD -> master) 마크다운 및 git  정리
$ git log -1
```

커밋은 해시코드를 바탕으로 구분된다. 

## 원격 저장소(remote repository) 활용하기


원격 저장소 기능을 제공하는 다양한 서비스 중에  github을 기준으로 설명한다. 

### 0. 준비사항

* Github에 repository 생성

### 1. 원격 저장소 등록

```bash
$ git remote add origin 깃허브url
```

* 원격저장소(`remote`)로 `origin`이라는 이름으로 `깃허브url`등록(`add`)한다. 

* 등록된 원격 저장소 목록을 보기 위해서는 아래의 명령어를 활용한다. 

  ```bash
  $ git remote -v
  origin  https://github.com/hui-yeon/TIL.git (fetch)
  origin  https://github.com/hui-yeon/TIL.git (push)
  ```

### 2. `push` - 원격 저장소 업로드

```bash
$ git push origin master
```

`origin` 으로 설정된 원격저장소에 `master`브랜치로 업로드(`push`)

이후 변경사항이 생일 때마다, `add`-`commit`, `push`를 반복하면 된다.

그리고, 항상 모든 명령어 이후에 연관된 상태를 확인하자.

`status`,`log`,`remote -v`