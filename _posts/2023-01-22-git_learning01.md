---
layout: single
title: "2023/01/22 git에 대해 배우다"
---

오늘은 git에 대해 공부하였다.

# git, github 는 각각 무엇인가?

git은 VCS(Version Control System)인데, 프로그램을 여러 명이서 개발할 때 소스코드를 유용하게 관리할 수 있도록 한다.
로컬에서 내가 작성한 코드와 그 수정내역(히스토리)를 기록할 수 있고, 브랜치(branch)를 생성하여 이전 버전으로 복구하거나, 삭제하거나, 다른 브랜치와 병합할 수 있다.
하지만 로컬 저장소를 이용하기 때문에 다른 사용자와 공유를 할 수가 없다.

github은 클라우드 서버를 사용하여 git 저장소를 관리하는 서비스이다. 클라우드 기반이므로 다른 사용자들과 서로의 소스코드들을 공유할 수 있고,
한 프로젝트에 여러 유저들이 참여하여 공동 작업을 할 수 있다.

정리하자면, git과 github를 통해 내가 개발하는 소스코드를 체계적으로 관리할 수 있고, 다른 사람들과 공유하며 협업할 수 있다.

# git 설치

git 사이트에 들어가서 프로그램을 다운로드, 설치한다.
설치 완료 후 git bash를 열어 환경설정한다. (유저 이름, 유저 이메일)

# git 사용방법 (terminal)
1. 초기화(첫 업로드 때 한번만 하면 되고, 그 이후로는 할 필요 없다.)
git init
2. 업로드할 파일 추가(파일이 있는 디렉토리로 이동해 있는 상태에서, 점(.)은 디렉토리 안의 모든 파일을 의미)
git add .
3. 상태 확인(선택사항)
git status
4. 히스토리 만들기/설정(히스토리 : github에서 업데이트 항목에 관해 보여지는 설명. -m은 메세지를 뜻함)
git commit -m "nth commit"
5. github repository랑 내 로컬 프로젝트랑 연결
git remote add origin http://github.com/5amriley/~~~ (이 명령어는 github에서 복사해와야함)
6. 연결 상태 확인(선택사항)
git remote -v
7. github로 업로드/푸시
git push origin master (master 자리에는 브랜치 이름이 들어가면 된다.)

# git에 계속 업데이트하는 방법

1. 업로드할 파일 추가
git add .
2. 히스토리 설정
git commit -m "nth commit"
3. github로 업로드/푸시
git push origin master

# github로 팀 프로젝트 하는 법

1. github에서 소스코드 다운로드
git clone 주소 폴더이름
※ 주소는 깃허브에서 가져와야 한다.
   폴더이름은 선택사항인데, 지정 안해주면 깃허브 프로젝트 이름으로 새 폴더가 생성되며 코드가 저장되고, 지정해주면 그 이름으로 새 폴더가 생성이 된다.
2. github에서 내 브랜치 만들기
git checkout -b 브랜치이름
3. 내 브랜치에 소스코드 업데이트하기
git add .
git commit -m "nth commit"
git push origin 브랜치이름
4. 마스터 브랜치의 코드를 가져오기/풀
git pull origin master
5. 브랜치끼리 이동하는 법(내 브랜치에서 마스터 브랜치로, 마스터 브랜치에서 다른 브랜치로...)
git checkout 브랜치이름


참고 :
https://cocoon1787.tistory.com/723
https://hackmd.io/@oW_dDxdsRoSpl0M64Tfg2g/ByfwpNJ-K
https://www.youtube.com/watch?v=lelVripbt2M
https://www.youtube.com/watch?v=cwC8t9dno2s&t=0s
