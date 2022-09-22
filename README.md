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

###git clone [저장소주소]
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
```
이렇게 저장소를 현재 작업 디렉토리(pwd로 확인)로 클론한다.
현재 디렉토리에 새 폴더가 생성되어 그 안에 클론되므로, 따로 폴더 만들지 않도록 한다.

## GitHub
###Organization
- 팀 작업 할 때 Organization을 구성할 수 있다.
- 다같이 포트폴리오 공유 가능
###Project
- 칸반 보드 형태로 이슈관리를 하는 데 쓰인다.
개인 계정에서 New Project 하면 개인 프로젝트가 되고, 조직에서 하면 조직의 Project가 된다.
