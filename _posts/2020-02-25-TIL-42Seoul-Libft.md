---
title: "[TIL #2] WSL, VS Code 개발 환경 세팅"
date: 2020-02-27 00:24:53 +0900
categories: TIL 42seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-02-25(화)

## 2. 학습시간

> 10:00 ~ 24:00 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]

  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]

  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- Linux (Ubuntu) Bash 동작 원리
- Makefile
- Static Library

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- VS Code Settings.json 최적화
- VS Code Code Snippet 작성
- libft 를 풀기위한 기초지식을 습득하고 습득한 지식을 통해 프로그램 개발

## 6. 과제 제출 repository 주소

> SSH

- gits@git.innovationacademy.kr:hmin/Libft.git

## 7. 상세 학습 내용

```text
실제 코딩에 사용한 시간 (필수)
학습에 참고한 사이트 (홈페이지, 동영상, 자료)와 내용(권고)
오늘 발견한 문제(버그, 몰랐던 것,...) 해결 방안 (필수)
다른 교육생들과의 협업, 토론 내용(권고)
```

[] : 프로젝트 관련 공부\
() : 기타 공부

```text
[6H] Makefile 강좌 공부
  기본적인 Makefile 작동 원리 / 구조
    https://www.youtube.com/watch?reload=9&v=KjTzCUbkVyE
    https://www.youtube.com/watch?reload=9&v=lWLGdtZ44iU

  # Target : Dependencies
  #     Command
  #     Command
  #     ...

  # To set conventional variable names
  # http://www.gnu.org/software/make/manual/html_node/Implicit-Variables.html
  CC = gcc

  CFLAGS += -Wall
  CFLAGS += -Wextra
  CFLAGS += -Werror

  ...
  ... (skip)

  # $@ == The file name of the target of the rule.
  # $< == The name of the first prerequisite.
  # $^ == The names of all the prerequisites.

  hello.o : hello.c
    $(CC) -c $< $(CFLAGS)
  # gcc -c hello.c -Wall -Wextra -Werror

  main.o : main.c hello.h
    $(CC) -c $< $(CFLAGS)
  #   gcc -c main.c -Wall -Wextra -Werror

  $(TARGET) : hello.o main.o
    $(CC) -o $@ $^ $(LDFLAGS)
  # gcc -o hello.out hello.o main.o

  fclean :
    rm *.o
    rm $(TARGET)

[3H] Ubuntu 가상환경 완전 재설치
  알 수 없는 원인으로, 특정 패키지 (특히 libbsd-dev)가 어떤 명령어를 써도 업데이트 되지 않음.
  분명히 있어야 할 패키지인데, 패키지 목록에 뜨지 않음.

  심지어 한 번 지우고 재설치도 불가능

  ex)
    sudo apt update
    sudo apt upgrade
      패키지 목록 최신화
    sudo apt install libbsd-dev
      패키지 설치 안 됨: dependency 오류 뜨면서 설치 안 됨
    apt-cache search libbsd-dev
      패키지 안 뜸

  결국 우분투 지워버리고 재설치 한 후 패키지 업데이트 하니 정상 작동...


[2H] Ubuntu 패키지 관리법 배우고, 재활용 가능하도록 주요 명령어 저장
  ====== Symbols Meaning
  #: Commentary

  ====== Package Tool
  ### MUST DO THIS! It is really important to update package list!
  sudo apt update
  sudo apt upgrade
  sudo apt autoremove
  sudo apt upgrade
  sudo apt install ubuntu-wsl wslu

  ====== Manual Page
  # sudo apt install manpages-dev
  # sudo apt install libbsd-dev

  ### Colorful Man page!
  sudo apt install most
  # echo 'export PAGER="most"' >> ~/.bashrc
  # or
  # echo 'export PAGER="most"' >> ~/.zshrc
```

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

Makefile 공부가 간단하게 끝날 줄 알았지만, 생각보다 엄청 오랜 시간 동안 깊게 공부했습니다. 특히나 저는 외부 코드를 참조하더라도 모든 뜻을 반드시 이해하고 참조하려 노력하기에, 동료들이 작성한 전혀 뜻을 알 수 없는 해괴망측한 기호들을 보며 멘탈이 바사삭 깨지기도 했습니다.

최대한 구글링을 많이 하고 documentary를 참고하니 점차 숨겨진 의미들을 이해하기 시작했고, 이는 자동화라면 환장하는 제게 점점 활력을 가져다 주었습니다.

이윽고 남들과는 색다른 Makefile을 만들어낼 수 있었으나, 아직 정적 라이브러리에 대한 이해도가 없어, 이를 이해하고 적용하기 위한 길은 아직 멀고도 험한 것 같습니다.

또한, 우분투는 왜 그리 말썽인지 정말 온갖 구글링을 다 해가며, 왜 libbsd-dev 메뉴얼 페이지가 인스톨 되지 않는지 이유를 찾아내고자 했지만, 끝내 확실한 해답을 찾지는 못 했습니다. 혹시나 싶어 이미 존재하는 패키지를 지우고 재설치를 시도하자 그것마저 되지 않더군요.

분명, 아무 명령어나 긁어쓰다가 패키지 관리 툴에 문제가 생긴 것 같았지만, 도대체 어디부터 손을 봐야 dependency 오류를 해결할 수 있을 지 도저히 감이 잡히지 않아, 결국엔 WSL 우분투 가상환경을 깔끔하게 밀어버리고 재설치 했습니다.

역시나... 컴퓨터가 말썽일 땐 아래의 3가지만 실행해도 90%는 고쳐지는 듯 합니다.

1. 데스크탑 샷건
2. 재설치
3. 재부팅

## 9. 다음 학습 계획 (최소 5줄 이상)

내일은 Libft 프로젝트 관련 공부도 좋지만, 이에 올인하기보다는 친한 지인분과 백준 알고리즘 문제 풀이를 하는 시간을 좀 더 배정해보고자 합니다.

최근 C++을 배움과 동시에 코딩 테스트 문제들을 풀면서 기본적인 자료구조/알고리즘 활용 역량을 쌓아나가려 했는데, 개발 환경 셋팅 / Libft 관련 개념 공부 때문에 이에 소홀해져, 지인분이 아주 아주!! 살짝 마음이 상한 것 같습니다. 멘탈 케어 해드려야죠.

일단 이에 대한 공부가 끝나면, 기술 블로그도 한 번 만들어보고자 합니다. 블로그를 작성하면 여태까지 배운 내용이 다시 한 번 깔끔하게 복습될 뿐만 아니라, 저와 같은 문제로 고민한 많은 분들께 팁을 드릴 수도 있으니까요.

다만, GitHub Page 기본 주소는 이미 제가 예전에 만들었던 공부방송 도우미 <https://jud210.github.io/gongbang-helper/> 에서 사용중이기에, 아무래도 도메인을 구매해야할 것 같습니다.

Libft 프로젝트와 관련한 공부는 아마 정적 라이브러리에 관한 내용이 주가 될 것 같구요, 내일부턴 이미 알고있는 짜잘한 함수들은 차근차근 작성해나가고자 합니다. 이제 오늘부로 Makefile이 완성되었으니 gcc -c blahblah 같은 시간낭비는 안 해도 되겠군요. 따봉!
