---
title: "[TIL #1] WSL 설치, VS Code 개발 환경 세팅"
date: 2020-02-26 23:22:48 +0900
categories: TIL 42Seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-02-24(월)

## 2. 학습시간

> 10:00 ~ 01:40 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]\

  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]

  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- Mac에서 Windows로 개발 환경 옮기기
- WSL Ubuntu 설치
- Text editor: VS Code 셋팅
- gcc 등의 C 개발 환경 셋팅

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- libft 를 풀기위한 기초지식을 습득하고 습득한 지식을 통해 프로그램 개발
- Mac OS와 최대한 동일한 C언어 개발 환경 구성하기

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
(4H) C++ 공부
  Memory 구조 / Pointer
    http://tcpschool.com/c/c_memory_structure
    https://adkim.tistory.com/m/10

[2H] VSCode Tutoring for friends

[1H] Windows10 에 WSL(Windows Subsystem Linux) Ubuntu 설치
  sudo apt install ...

[1H] Mac OS에서 등록한 VS Code 셋팅 끌어오기
  Ubuntu: 기본 쉘 bash에서 oh-my-zsh로 변경

[1H] VS Code에 Ubuntu bash 기본 터미널로 등록

[1H] Shell command 익히기
  find . -type f -name="*.c" -exec mv {} {}.bak \;
    https://unix.stackexchange.com/questions/27586/how-can-i-edit-multiple-files-in-vim
    https://unix.stackexchange.com/questions/45025/how-to-suspend-and-bring-a-background-process-to-foreground

[1H] Makefile 강좌 공부

[2H] gcc <unistd.h> include path error 해결
  "C_Cpp.default.compilerPath": "/usr/bin/gcc",
```

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

맥에서 세팅해놓은 개발 환경을 윈도우로 그대로 끌어오는 과정이 아주 빡세고 고통스러웠습니다.
하지만, 그 과정에서 리눅스(우분투), Bash, Zsh, oh-my-zsh, ... 등에 대한 수 많은 새로운 개념을 알게 되었습니다.
특히, alias와 .zshrc세팅 파일들에서도 if문과 else if문을 쓸 수 있다는 게 가히 혁명적인 발견이었습니다.

개발 환경을 설정하고 최적화하는 것을 좋아하기에 과제는 뒤로 하고 너무 이쪽에만 에너지를 쏟은 것이 아닌가 걱정은 됩니다.
그래도 본과정은 피씬과 다르게 여러가지 원하는 것들을 할 수 있는 여유가 있다고 했으니, 괜찮지 않을까 싶습니다.

피씬 때 배운 shell 명령어들을 활용하여, 몇 백자를 때려박아야 할 명령들을 몇 글자로 한 번에 수행할 때마다, 영화 속에 나오는 해커가 된 기분이라 아주 마음에 듭니다.

## 9. 다음 학습 계획 (최소 5줄 이상)

피씬 과정에서 배우지 못하고 넘어갔던 개념들, 그리고 너무 급하게 넘어가서 기억나지 않는 개념들을 복습할 것입니다.

예를 들면, Makefile 진도 이후부터는 완전히 아는 것이 없는데, 지금 당장 기본적으로 알아야 하는 개념이 되어버리니 갈 길이 살짝 막막해 보이기도 합니다.

또한, string 관련된 함수들은 메뉴얼/개념 위주가 아닌 테스트 케이스 위주로 작성을 하다 보니, 정확히 무슨 기능을 하는 함수였는지 자세하게 기억이 나질 않습니다. ex) strlcat

하지만 피씬 때도 그러했듯이, 이 또한 지나가겠죠.

내일은 Makefile 딱 하나만 바라보고 이를 마스터하기 위해 노력해야겠습니다.
그리고 C++ 등 기타 공부 시간을 조금은 줄여야겠습니다.
