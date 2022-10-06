# 2022-OpenSource-Fall
서강대학교 게임&amp;평생교육원 오픈소스개발이해

## 리눅스 커맨드라인 기초
> 모르면 실습이 불가능한 기초 커맨드라인 3가지
1. pwd : print working directory
2. ls : list
3. cd: change directory

## vim 에디터
```bash
vim abc.txt// abc. txt 파일을 vim 에디터로 열기
```

- 파일을 처음에 열면 명령모드로 진입한다
- 입력하려면 I를 눌러 입력모드로 진입하기

- 명령모드 진입은 키보드 esc키 누르기
 - 저장하기(write) --> :w
 - 나오기(quit) --> :q
 - 저장하고 나오기 --> :wq 

### 스왑파일 생성시 해결 방법
#### 스왑파일이 생기는 경우
- Vim Editor로 파일을 열고 지시를 따른다.

## Git
>대표적으로 쓰이는 버전 관리 시스템(Version Control System, VCS)

### Git vs GitHub
- git은 버전 관리 시스템이다.
- GitHub는 git을 기반으로 만든 플랫폼
	- GitHub에서 만들었는데, GitHub을 마이크로소프트가 인수

### 다양한 버전 관리 시스템
- 이름 변경
	- 최종.hwp, 최종1.hwp
- 자동저장 기능
- git 이전 버전 관리 시스템
	- SVN, CVS, Mercurial
- 요즘은 git이 거의 표준이 됨

### git init
- 빈 디렉토리를 만들고 이동해서, 현재 작업 디렉토리를 git 저장소로 만들 수 있음
```bash
mkdir [저장소명]
cd [저장소명]
pwd
git init
```
이런 식으로 git 저장소를 만들 수 있다.

- .git파일을 지워서 커밋 이력을 날려버리고 싶을 때, 지울 수 있다.

### 커밋이란
- 독립된 버전을 나타내는 스냅샷이다.
- 논리적 변경이 있을 때 만든다. 가능하면 작을수록 좋다.
- 커밋 단위가 작고 잘 쪼개져 있으면 장애에 대응하기 쉽다.
- 커밋 이력이 맘에 안 든다면 .git파일을 삭제하여 한 번에 날릴 수 있다.

### gitconfig 확인하기
- 다음과 같이 config 상태를 확인할 수 있다.
```bash
git config --list
```
- 다음처럼 config을 전역으로 수정할 수 있다.
```bash
git config --global user.name "홍길동"
git config --global user.email "email@domain.com"
```
- 다음과 같이 전역 설정된 사용자를 지울 수 있다.
```bash
git config --unset --global user.name
git config --unset --global user.email
```

### git clone [저장소주소]
클론 하기 전, 확인한다.
```bash
git config --global user.name [닉네임]
git config --global user.email [이메일]
git config user.name
git config user.email
```
이렇게 초기 세팅을 하고, 세팅된 내용을 확인할 수 있다.

```bash
git clone [저장소주소]
git status
```
이렇게 저장소를 현재 작업 디렉토리(pwd로 확인)로 클론한다.
현재 디렉토리에 새 폴더가 생성되어 그 안에 클론되므로, 따로 폴더 만들지 않도록 한다.

### git checkout
특정 커밋으로 작업 상태를 되돌리고 싶으면, 다음과 같이 명령한다.
```bash
git checkout [커밋값]
```
이렇게 특정 시점으로 체크아웃하면 detached HEAD 상태가 된다.
확인할 것 확인했다면 뭐 건드리지 말고 다시 메인으로 돌아간다.
```bash
git checkout master
git checkout main
git checkout [브랜치명]
git status //정상적으로 왔는지 확인용
```
이런 식으로 돌아갈 수 있다.

### 커밋 합치기
저장 목적으로 쓸데없는 커밋이 생겼을 때, interactive rebase를 사용해서 둘을 합칠 수 있음

git rebase -i HEAD~2
헤드 기준으로 2개 커밋을 1개로 합침
스쿼시 - 이전 커밋에 다음 커밋을 녹여넣기 옵션 지정 가능

git reset HEAD~1
가장 최신 커밋을 삭제

### 브랜치 만들기
- 어떤 목적을 가지고 코드를 수정할 필요가 있을 때 브랜치를 만들어서 작업한다.
```bash
git branch
git branch SomeIssue
git checkout SomeIssue
git status
```
이런 식으로 브랜치 상태 확인, SomeIssue 브랜치 만들기, 브랜치로 이동까지 할 수 있다.

## GitHub
### Organization
- 팀 작업 할 때 Organization을 구성할 수 있다.
- 다같이 포트폴리오 공유 가능
- 이미 개인으로 만든 리포지토리를 Import할 수도 있다.(Owner를 개인이 아니라 조직으로 변경하면 된다.)

### Project
- 칸반 보드 형태로 이슈관리를 하는 데 쓰인다.
- 개인 계정에서 New Project 하면 개인 프로젝트가 되고, 조직에서 하면 조직의 Project가 된다.

## Google에서 Search
- 구글에 Awesome Unity Game Project를 검색하자.

## README.md 쓰는법
### 팀 프로젝트
- 팀명 / 프로젝트명
- 대표이미지
- 영상 유튜브 링크
- 프로젝트 소개, 배경, 목표
- 팀원
- 개발 / 배포 / 테스트 환경
- 구동 방법
- 참고 자료 / 사용한 에셋
- 참가자 코멘트
- 검색에 나오게 태그 설정하기

## 공부하는 법
### Roadmap
- Game Developer roadmap을 검색하여 참고한다.
### 면접 질문 리스트
- 게임 개발자 면접 질문 리스트를 검색하여 참고한다.
