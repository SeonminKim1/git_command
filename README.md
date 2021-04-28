## Git 기본
- Linus Torvalds 가 만듬. (Distributed Version Control System) - DVCS
- GIT 은 총 3개의 나무로 구성되어있음.
  - 첫번째 나무 : 작업 디렉토리(Working Directory)는 로컬(실제) 파일들로 이루어짐.
  - 두번째 나무 : 인덱스(Index)는 준비 영역(Staging area)의 역할을 함.
  - 세번째 나무 : git Repository

## Git 저장소 만들기
- .git이라는 파일이 생성되고 정보 관리됨
```
git init
```

## Git에 파일올리기
1. git config --global user.names "SeonminKim1"로 내 정보설정
2. git remote add <별명> <url주소> : git 원격 저장소 주소 지정
3. git pull <별명> <원하는 branch> : 현재 Branch로 파일 동기화
4. git add <파일> : 파일 작업 디렉토리에 추가
5. git commit -m <메시지> : 파일 commit 
6. git push <별명> HEAD : 원격 저장소로 HEAD 내용을 push

## Git Remove
- 깃 폴더 삭제 (원격저장소 & 로컬저장소)
```
git rm -rf '폴더명' 
git rm -rf '파일명'
git commit -m "파일삭제"
```

## Git pull 시 덮어쓰기
- local 저장소와 remote 저장소가 서로 git 내용이 다를 때
```
git pull algo master --allow-unrelated-histories : 내 master에 덮어쓰기
```

## Git add, commit 취소
- Staging 내용 취소
```
git reset HEAD
```

## Git 대용량
```
git lfs install : lfs 파일 설치
git lfs track *.exe : 대용량 파일 형식자 등록
git add
git commit
```

## Git commit 내용 변경
```
git commit --amend : commit 내용 수정
```

## Git fetch 
- 원격 저장소의 데이터를 로컬에 가져옴.
- pull : 원격 저장소의 내용을 가져와 자동으로 merge 작업을 실행
- pull = fetch + merge

## Git attributes 언어 change
- 단 언어 2개 이상표출은안됨
- * linguist-vendored
- *.py linguist-vendored=false

## Git config
```
git config --global -> 이 버전을 작업한 사람이 누구이고, 
git config --global user.name "seonmin_git"
git config --global user.email "email"
git config --list : git config 
```

## Git log vs git status
- git status는 add후에 commit 하기위해 그전에 보는것0
- git log는 전체적인 commit branch를 보는 것

## Git status
- unstaged (in Working Tree)
- staged (In Staging Area or Index or Cache)
- committed (in local repo object database)

## Git branch & checkout
- 작업이 분기되는 상황을 branch화 된다라고 함. 
```
git branch exp : exp라는 branch가 생김
git checkout exp : 해당 branch 로 들어가기
```

## Git log --branches --decorate --graph
- git commit log 보는 방법 (보다 시각화적으로)

## git merge
- main branch에서 다른 branch 들을 합침

```
git checkout master 
git merge exp 
git branch -d exp : 기존 branch 삭제
git log --reverse : 맨 처음꺼 보여주기
```

## vi .gitignore file
- *.class 란 파일을 다 무시하겠다.
- temp/ 란 파일을 다 무시하겠다.
- *.[oa] -> .o나 .a인 파일을 무시하라는 것.

```
nano .gitignore : 파일을 만듬
git add .gitignore : 하면 등록
```


