# 2022-OpenSource-Fall
> 서강대학교 게임&amp;평생교육원 2022-2학기 오픈소스개발이해
- - -

## 게임 개발자 공부하는 법
1. 검색(구글링)
- __awesome (찾을 내용) github__ 을 검색한다. 괜찮은 오픈소스 코드를 찾을 가능성이 있다.
- Game developer roadmap을 검색하여 참고한다.
- 게임 개발자 면접 질문 리스트를 검색하여 참고한다.
2. TIL(Today I Learned)
- 깃헙이나 노션, 블로그 등에 공부한 내용을 꾸준히 정리하여 업로드한다.

## 리눅스 터미널(bash) 커맨드라인 기초
> 모르면 실습이 불가능한 기초 커맨드라인 3가지(pwd, ls, cd)와 그 외 기타
- pwd : print working directory
- ls : list
- cd: change directory
- clear : 화면 청소
- code : visual studio code 열기
```bash
pwd # print working directory
ls # list
ls -a # 모든 파일(숨김 파일 포함) list
ls -l # 파일 속성을 자세히 보여주는 list
ls -al # 모든 파일 자세히 list
cd <디렉토리명> # 현재 작업 디렉토리 기준 해당 상대경로로 이동
cd </드라이브/.../디렉토리명/디렉토리명> # 해당 절대경로로 이동
cd .. # 상위 디렉토리로 이동(.은 현재 디렉토리, ..은 상위 디렉토리를 의미)
clear # 터미널 화면 깨끗히 정리
code . # 현재 작업 디렉토리를 visual studio code로 열기
```
## vim 에디터
> 리눅스 터미널에서 기본으로 사용하는 텍스트 에디터
### vim 에디터로 파일 편집하기
1. 터미널에서 vim 진입
```bash
vim abc.txt #abc.txt 파일을 vim 에디터로 열기
```
2. 명령 모드와 입력 모드
> 명령 모드 : 명령어를 입력할 수 있는 상태
> 입력 모드 : 텍스트를 편집할 수 있는 상태
- 파일을 vim으로 열게 되면 처음에는 명령 모드로 진입한다.
- I를 눌러 명령 모드 -> 입력 모드 전환
- ESC를 눌러 입력 모드 -> 명령 모드 전환

3. 명령 모드에서 명령하기
- 저장하기(write) -> :w
- 나오기(quit) -> :q
- 저장하고 나오기 -> :wq
- 강제 종료 -> :wq!

### swp파일 생성시 해결 방법
> vim으로 작업하다가 정상적으로 종료하지 않았거나 다른 사용자가 이미 작업하고 있을 때 생성된다.
- 별 거 없다면 지워버리기 -> swp파일을 삭제한다.
- 작업하던 내용 복원하고 싶다면 -> vim으로 파일을 열고 :recover 를 입력하여 마지막 작업 중이던 상태로 복원한다.

## Git
> 대표적으로 쓰이는 버전 관리 시스템(Version Control System, VCS)
### git 이해하기
1. git vs GitHub
> git은 시스템, GitHub은 플랫폼
- git은 라이너스 토르발즈(리눅스 제작자)가 만든 버전 관리 시스템.
- GitHub는 마이크로소프트가 인수한 git을 기반으로 만든 플랫폼. 코드 공유와 협업에 사용한다.
2. 다양한 버전 관리 시스템
> 다양한 버전 관리 시스템이 있으나, 요즘은 git이 거의 표준이다.
- 이름 변경하여 저장(최종.hwp, 최종1.hwp)
- 자동 저장 기능
- git 이전에 사용하던 버전 관리 시스템(SVN, CVS, Mercurial)
### git 명령어 모음
1. git 시작하기
```bash
git init # .git 파일의 생성으로 현재 디렉토리를 저장소로 만듦
git clone <저장소주소> # 현재 디렉토리에서 새 디렉토리를 만들어, 그곳에 모든 원격 저장소 내용을 복제
```
2. 상황 파악하기
```bash
git status # 현재 상태 확인
git log # 커밋 이력 확인
git config --list # 설정 확인
git branch # 브랜치 목록 및 현재 브랜치 확인
git remote -v # 현재 연결된 원격 저장소 url 확인
```
3. 커밋하기
```bash
git add <파일명> # 해당 파일 스테이징
git add . # 디렉토리 전체 스테이징(gitignore로 무시되는 파일 제외)
git commit -m "커밋메시지" # 해당 커밋메시지로 스테이징된 내용을 커밋
```
4. 브랜치 만들기
```bash
git branch <브랜치명> # 브랜치 만들기
```
5. 브랜치 병합하기
```bash
git merge <브랜치명> # 해당 브랜치를 현재 브랜치로 병합하기(반대로 하면 안 됨)
```
6. 버전 탐색하기
```bash
git checkout <커밋 해쉬> # 해당 커밋으로 상태를 되돌림. detached HEAD 상태가 됨(왠만하면 만지지 말기)
git diff <커밋 해쉬1> <커밋 해쉬2> # 두 커밋 간 차이를 확인하기
git checkout <브랜치명> # 해당 브랜치 HEAD로 체크아웃. detached HEAD 상태에서 원래대로 돌아갈 때도 유용함
git switch <브랜치명> # git checkout <브랜치명>과 완전히 동일한 명령어(직관적인 이름으로 새로 추가되었음)
```
7. 원격 저장소 등록하기
```bash
git remote add origin https://github.com/<계정명>/<리포지토리이름>.git # origin 원격 저장소의 주소를 해당 URL로 설정
git remote remove origin # origin 원격 저장소의 연결을 제거
``` 
8. 원격 저장소에 파일 올리기, 내려받기
```bash
git push origin main # origin 저장소의 main 브랜치에 푸쉬
git fetch origin # origin 저장소에 반영된 내용 모두 가져오기
git merge origin/main # 현재 main 브랜치에 있다고 할 때, origin/main브랜치를 main 브랜치로 병합
git pull origin main # origin 저장소의 main브랜치 내용을 fetch + merge까지 한 번에 진행
```
9. git 설정하기
```bash
git config --list # config 내용 확인
git config --global user.name "홍길동" # 최초 사용자 이름 전역 설정
git config --global user.email "email@domain.com" # 최초 사용자 이메일 전역 설정
git config --unset --global user.name # 전역 설정된 사용자 이름 제거
git config --unset --global user.email # 전역 설정된 사용자 이메일 제거
```
### git 시작하기
1. 현재 작업 디렉토리를 저장소로 만들어 시작하고, 초기 세팅
```bash
pwd # 리포지토리들이 모여 있는 원하는 디렉토리에서 시작(정확히 확인)
mkdir <저장소명> # 원하는 이름으로 새 디렉토리 만듦
cd <저장소명> # 저장소가 될 폴더로 이동
git init # .git 파일의 추가로 디렉토리를 저장소로 만듦
git config --global user.name "홍길동" # 최초 사용자 이름 지정
git config --global user.email "email@domain.com" # 최초 사용자 이메일 지정
git config user.name # 설정된 user.name을 확인
git config user.email # 설정된 user.email을 확인
```
### 원격 저장소 클론받아 시작하기
```bash
pwd # 현재 리포지토리들이 모여 있는 디렉토리에서 시작(클론할 때 새 폴더가 만들어지므로, 따로 폴더 만들 필요 없음)
git clone <저장소주소> # 원격 저장소의 이름으로 새 폴더가 만들어지고, 모든 내용이 복제되어 컴퓨터에 저장됨
```
### 커밋이란
- 독립된 버전을 나타내는 스냅샷이다.
- 논리적 변경이 있을 때 만든다. 가능하면 작을수록 좋다.
- 커밋 단위가 작고 잘 쪼개져 있으면 장애에 대응하기 쉽다.
- 커밋 이력이 맘에 안 든다면 .git파일을 삭제하여 한 번에 날릴 수 있다.
### 커밋 합치기
> 단순 백업 목적으로 쓸데없는 커밋이 생겼을 때, interactive rebase를 사용해서 둘을 합칠 수 있다.
1. 커밋 수정 명령
```bash
git rebase -i HEAD~3 # 3개의 커밋을 interactive rebase
```
2. vim editor로 커밋 수정 시작하기
- 상태를 확인해 보면, 다음과 같이 커밋들이 pick 되어 있는 상태가 보일 것
```bash
pick <커밋1 해쉬> first
pick <커밋2 해쉬> second
pick <커밋3 해쉬> third
```
- 먼저 I키를 눌러 입력 모드로 전환하기
- 제일 위에 것은 pick으로 두고, 나머지 아래 커밋들을 s(squash)로 바꿔준다.
```bash
pick <커밋1 해쉬> first
s <커밋2 해쉬> second
s <커밋3 해쉬> third
```
- 명령창에 :wq로 저장하고 빠져나온다. 그러면 자동으로 새로운 vim 창이 열린다.
3. 새 커밋 메시지 작성
```bash
# This is a combination of 3 commits.
<새 커밋 메시지> # 이 부분에 작성하면 된다.
```
- :wq로 빠져나오면 최종적으로 여러 개 커밋을 1개로 합치게 된다.
4. 원격 저장소에 강제로 푸쉬
```bash
git push -f origin main # -f는 --force와 같다. origin main에 강제로 푸쉬
```
이런 식으로 커밋을 합친 후 강제 푸쉬하면 커밋이 합쳐진 게 원격 저장소에 반영된다.(-f 옵션은 --force와 같은 뜻이다.)
5. 만약 잘못 rebase했다면?
```bash
git rebase --abort # rebase중인 내용 중단
```
### 커밋 삭제하기
```bash
git reset HEAD~1 # 가장 최신 커밋을 삭제
```
### 커밋 체크아웃
> 예전에 커밋된 작업 상태를 확인하고 싶을 때, 그 시점으로 체크아웃하여 살펴본다.
```bash
git checkout <커밋 해쉬> # 특정 커밋으로 작업 상태를 되돌리고 싶으면, 다음과 같이 명령한다.
git checkout HEAD~1 # HEAD 기준으로 한 단계 과거로 되돌린다.
git checkout main # 원래 브랜치명을 적어주면, 다시 돌아올 수 있다.
```
이렇게 특정 시점으로 체크아웃하면 detached HEAD 상태가 된다.
확인할 것 확인했다면 되도록 뭔가 건드리지 말고 다시 메인으로 돌아간다.
### 브랜치
- 어떤 목적을 가지고 코드를 수정할 필요가 있을 때 브랜치를 만들어서 작업한다.
```bash
git branch # 브랜치 상태 확인
git branch <이슈명> # <이슈명> 브랜치 생성
git checkout <이슈명> # <이슈명> 브랜치로 이동
git status # 제대로 이동했는지 확인
```
> checkout vs switch
> 체크아웃은 스위치와 완전 동일한 명령어이다. 예전에는 체크아웃뿐이었는데, 스위치라는 명령어가 더 직관적이니 추가된 것.
## GitHub
> git 기반 협업 플랫폼
### Organization
> 조직
- 팀 작업 할 때 Organization을 구성할 수 있다.
- 다같이 포트폴리오 공유 가능하다는 장점이 있음
- 이미 개인으로 만든 리포지토리를 Import할 수도 있다.(Owner를 개인이 아니라 조직으로 변경하면 된다.)

### Project
- 칸반 보드 형태로 이슈관리를 하는 데 쓰인다.
- 개인 계정에서 New Project 하면 개인 프로젝트가 되고, 조직에서 하면 조직의 Project가 된다.

## 마크다운
> .MD 파일을 작성하는 문법
### 마크다운 문법

### README.md 쓰는 방법
1.팀 프로젝트
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

## 중간고사 내용 정리
1. 기본적으로 알아야 할 커맨드라인 명령어
- pwd, cd, ls - 약자
2. vim 사용법
- 명령 모드와 입력 모드 전환
- 저장하고 빠져나오는 방법
3. 버전 관리를 사용하는 이유
- 실행, 취소 재실행이 가능함
- 버전 간 소스코드 비교가 가능함
- 협업이 쉬워짐
4. 깃, 깃허브 차이
5. 저장소와 일반 디렉토리의 차이
- .git 파일 존재 유무
- 저장소 만들 때 쓰는 명령어 (git init)
6. 커밋 로그를 보고 싶을 때 치는 명령어
- git log
7. 커밋은 언제 만드는가?
- 논리적 변경이 있을 때마다 하나 만들기
8. HEAD의 정의
- 현재 체크아웃한 브랜치의 가장 최신 커밋을 가리키는 포인터
9. 현재 상태를 확인하는 명령어
- git status
10. 스테이징 영역이 왜 존재하는가? 서술
11. 원하는 파일을 스테이징 영역에 올릴 때 쓰는 명령어(git add .)
12. 커밋 메시지가 "abc"인 커밋을 만들고 싶을 때 어떻게 하나?
- git commit -m "abc"
- git commit하고 엔터친 후, abc 입력
13. gitignore 파일의 역할
14. 브랜치는 언제 만드는가? 일감이 있을 때
15. 브랜치
- 브랜치 확인하기
- 브랜치 만들기
- 브랜치 체크아웃
- 브랜치 머지하기
- 충돌 해결하는 방법