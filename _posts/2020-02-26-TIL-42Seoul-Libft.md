---
title: "[TIL #3] BOJ 문제풀이 시작, 42서울 libft 과제 시작"
date: 2020-02-27 13:17:28 +0900
categories: TIL 42Seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-02-26(수)

## 2. 학습시간

> 10:00 ~ 01:00 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]\

  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]

  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- Backjoon Algorithm Online Judge: Brute Force (C++)
- Static Library
- void pointer
- libft part 1
- Markdown

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- 정적 라이브러리 (fild_name.a) 생성법
- 메모리의 구조에 대한 상세한 이해 및 이를 활용한 포인터 작동 원리 이해
- Markdown 사용법 숙지 및 레포트 작성

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
(4H) C++로 백준 알고리즘 문제 풀이

[2H] 메모리의 구조에 대한 상세한 이해 및 이를 활용한 포인터 작동 원리 이해
  Memory 구조 / Pointer
    http://tcpschool.com/c/c_memory_structure
    https://adkim.tistory.com/m/10
  void pointer
    memset을 구현하는 과정에서 왜 void pointer를 사용하는지 이해할 수 없었으나, char 와 unsigned char 모두를 받기 위한 것이었음을 알아냄.

    아래는 작성한 코멘트 전문
    /*
    ** Copy N bytes of SRC to DEST.
    **
    ** ((unsigned char *)dest_str)[idx] = src_ch;
    ** Tells the void pointer dest_str that it is     pointing unsigned char (1 byte)
    **
    ** So,
    ** if *(dest_str) == &dest_str[0] == 0x10
    ** *(dest_str + 1) == &dest_str[1] == 0x11
    ** *(dest_str + 2) == &dest_str[2] == 0x12
    */

[1H] 정적 라이브러리 (fild_name.a) 생성법
  ar -rcs
    https://stackoverflow.com/questions/29714300/what-does-the-rcs-option-in-ar-do

[3H] 기타 짜잘한 이미 아는 함수들 구현
  간단한 함수들은 Linux Man Page를 보며 구현해왔으나, memset 등에서 막혀, FreeBSD Man Page로 넘어가서 보니 엄청 디테일하게 구성 되어 있었음. 신세계.

[3H] Markdown 사용법 숙지 및 레포트 작성
  GitHub에서 항상 뜨던 README.md가 무슨 의도였는지 뒤늦게 이해

```

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

- C++로 백준 알고리즘 문제풀이를 하다보니 느낀 거지만, C++에서 사용하는 STL들이 C에 비해 얼마나 편리한지 감동하게 되었음. 부싯돌 쓰다가 라이터를 처음 쓰게 된 기분.

- 메모리 구조에 대해서 확실하게 이해하지 못 하고 있었는데, 42서울에서 C언어로 메모리를 자꾸만 만지게 되다 보니, 점점 이해도가 높아지는 중.

- 포인터에 대해서 계속 다루다보니 생긴 여러가지 의문점들이 있었는데, 메모리 구조를 이해하고 나니 void pointer 등의 전혀 의도를 알 수 없었던 것들이 점점 파악되기 시작함.

- 깃 위키에 나만의 기호로 이쁘게 꾸며서 텍스트 파일 작성을 완료하고 제출했는데, 별 해괴망측한 기호들로 도배가 된 것을 보고 멘붕이 터졌었음. 알고보니 Markdown 형식.

- GitHub Page 블로그 작성을 시작하기 위해 Markdown을 배우기로 마음 먹었는데, 때마침 레포트도 Markdown으로 작성해서 깃 위키에 올려야 하게 되어 좋았음.

## 9. 다음 학습 계획 (최소 5줄 이상)

- 내일은 백준/C++ 공부보다는 프로젝트에 집중해서, Libft Part 1은 반드시 끝내기.

- 메모리와 포인터에 대해 좀 더 확실하게 이해.

- 각 운영체제별로 타입 당 바이트 할당량이 다르던데, 어떻게 다른지 숙지.

- Jekyll theme 하나를 선택하고, GitHub Page와 DNS에 대해 공부하여 개인 블로그 만들 준비.

- 마크다운 형식을 좀 더 배워서 개인 블로그에서도 똑같이 적용할 수 있는 수준까지 끌어올리기.
