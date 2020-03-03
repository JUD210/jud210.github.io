---
title: "[TIL #4] BOJ: Tetromino, 42서울: libft"
date: 2020-02-28 01:47:40 +0900
categories: TIL 42seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-02-27(목)

## 2. 학습시간

> 10:00 ~ 24:30 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]\
  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]\
  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- Backjoon Algorithm Online Judge (C++)
  - Brute Force
    - Tetromino (Success!)

- libft
  - memset
  - bzero
  - memcpy
  - memccpy
  - memmove
  - memchr
  - memcmp

- Unit-Test
  - Make a main file to test functions
  - Git Clone libft-unit-test

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- C++ STL 사용법 익혀서 Tetromino 풀기
- 메모리 구조와 포인터의 관계 더 상세하게 이해하기
- 프랑스 선배들의 unit-test 클론해서 Makefile 수정 후 작동

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
(3H) Backjoon Algorithm Online Judge (C++)
  - Brute Force
    - Tetromino (Success!)
      시간 초과가 자꾸 나서 도대체 이유가 뭔가 했는데
      긴 함수 하나를 통째로 다시 바깥으로 빼버리니
      뜬금없이 테스트 통과를 해버렸다.
      도대체 이게 왜 되는 거지? 라는 프로그래머의 난제에
      또 다시 부딪힌 하루였고, 아직까지도 이는 의문이다.

[10H] libft
  - memset, bzero, memcpy, memccpy, memmove, memchr, memcmp
    아직도 메모리에 대한 이해가 많이 부족하구나 느꼈다.
    많이 안다고 생각했는데도 뜬금없이 터지는 segmentation fault
    때문에 멘탈이 바사삭 깨질 뻔.

    char       chars[]   = "123456789"; // RW (chars)
    char       chars[10] = "123456789"; // RW (chars)
    char       *str      = "123456789"; // R  (const chars)
    const char *str      = "123456789"; // R  (const chars)

    /*
    ************************************************************
    ** memset in <string.h>
    **
    ** Copy N bytes of SRC to dst.
    **
    ** The reason why the 'void' pointer was used is
    ** because dst is 'bytes' (not 'str' == 'chars').
    **
    ** so, any type of arguments' starting point
    ** can be pointed by dst
    **
    ** if    *(dst)     == &dst[0] == 0x10
    ** then  *(dst + 1) == &dst[1] == 0x11
    **       *(dst + 2) == &dst[2] == 0x12
    **
    ************************************************************
    **
    ** If dst is not a string, src should be input 0!
    ** for example, I'll show you if I input a value which is not 0.
    **
    ** int n = 5;
    ** // (== 101)
    ** // (== 00000000 00000000 00000000 00000101)
    **        0x13     0x12     0x11     0x10
    **
    **        0x10 00000101
    **        0x11 00000000
    **        0x12 00000000
    **        0x13 00000000
    **
    **
    ** ft_memset(&n, 2, 3);
    **
    ** printf("%d", n);
    ** // 131586
    ** // (== 100000001000000010)
    ** // (== 10 00000010 00000010)
    ** // (== 00000000 00000010 00000010 00000010)
    **        0x13     0x12     0x11     0x10
    **
    **        0x10 00000010
    **        0x11 00000010
    **        0x12 00000010
    **        0x13 00000000
    **
    **
    ** ft_memset(&n, 2, sizeof(int));
    **
    ** printf("%d", n);
    ** // 33686018
    ** // (== 100000001000000010)
    ** // (== 10 00000010 00000010)
    ** // (== 00000000 00000010 00000010 00000010)
    **        0x13     0x12     0x11     0x10
    **
    **        0x10 00000010
    **        0x11 00000010
    **        0x12 00000010
    **        0x13 00000010
    **
    **
    ** ft_memset(&n, 2, 100000);
    **
    ** printf("%d", n);
    ** // 33686018
    ** // (== 100000001000000010)
    ** // (== 10 00000010 00000010)
    ** // (== 00000000 00000010 00000010 00000010)
    **        0x13     0x12     0x11     0x10
    **
    **        0x10 00000010
    **        0x11 00000010
    **        0x12 00000010
    **        0x13 00000010
    **      --------------------
    **        Start Accessing Random Address!! (maybe ?)
    **      --------------------
    **        0x14 00000010
    **        0x15 00000010
    **      ...
    **      ... (skip)
    **
    **  // Actually, the result of printf("%d", n);
    **  // can't be printed because of below error.
    **  //
    **  // Segmentation fault (core dumped)
    ************************************************************
    */

[2H] libft-unit-test 클론해서 Makefile 수정 후 작동
  - Unit-Test
    - Make a main file to test functions
    - Git Clone libft-unit-test
      한 땀 한 땀 초보 느낌 나는 테스트 케이스를 만들고 있다가
      우연히 슬랙에 올라온 unit-test 깃을 보았고,
      이를 본 나는 소름이 돋았다.
      이 걸 만든 사람은... '진짜'다.
      이왕 이렇게 열심히 만들어 준 테스트 케이스가 있는데
      굳이 아직 초보자인 내가 직접 짤 필요는 없지.
      Makefile 좀만 만져주고 바로 적용.
      신세계.
      profit.
```

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

- 메모리에 대해서 아주 세세하게 이해할 수 있는 시간이었고, 이걸 제대로 이해한 내가 스스로 대견하고 뿌듯할 정도였다.
- 동료의 질문: void  *ft_memchr(const void *s, int c, size_t n) 에서 return(s); 를 하면 왜 에러가 뜨는지 모르겠다.
- 이 질문에 대한 해답을 찾기 위해 나도 구글링을 열심히 하며 알아본 결과, const 라는 qualifier (한정자)가 붙은 parameter를 const를 떼버리고(discard) 리턴했기 때문이라는 걸 알았다.
- 역시 가르치면서 배운다.
- 이런 좋은 덕목은 서로서로 나눠야 제맛. 나도 슬랙을 통해 질문하여 좋은 의자 추천을 받았고, 시디즈 T55가 좋다는 걸 알게 되었다. 개꿀. 지원금으로 질러야겠다.

## 9. 다음 학습 계획 (최소 5줄 이상)

- 메모리를 다루다보니, str을 다루는 스킬도 자연스레 늘어났을 것이다.
- 때문에, 내일은 part1을 기필코 끝낼 것이며, part2 마저 깔끔하게 끝내버리겠다.
- 백준은 잠시 접어두고자 한다. 1주라는 시간이 생각보다 빠듯하다.
- 내일은 기필코 8시 기상에 성공해서 운동하고 바로 달려야겠다.
- 시간이 좀 남으면 VS Code 개발 환경 최적화를 좀 해야겠다. 추가하고 싶은 자동화 커맨드들이 너무나도 많이 쌓여있다.