---
title: "[TIL #7] 42서울: libft"
date: 2020-03-02 03:34:38 +0900
categories: TIL 42seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-03-01(일)

## 2. 학습시간

> 11:00 ~ 03:00 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]\
  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]\
  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- libft
  - strjoin
  - strtrim
  - split
  - itoa
  - strmapi
  - putchar_fd
  - putstr_fd
  - putendl_fd
  - putnbr_fd
  - lstnew

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- string을 다루는 여러 함수 구현
- 연결리스트 개념 이해

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
[11H] libft
  strjoin, strtrim, split, itoa, strmapi
    str을 다루는 것에 많이 익숙해졌기에 로직을 짜는 것은 순조로워졌지만, 해당 로직을 구현하는 실력이 부족하여 많이 헤매었다.

  putchar_fd, putstr_fd, putendl_fd, putnbr_fd
    write 함수의 첫 번째 인자인 0, 1, 2가 file descriptor라는 걸 알게 되었지만, fd의 개념이 조금 난해하여, 그냥 input / output / error 정도로만 외워두었다.

  lstnew
    연결리스트에 대한 이해도가 많이 부족하여 해당 개념을 익히고 활용하는 시간이 오래 걸렸다. lstadd_front 는 특히 너무나 헷갈려서, 다른 분의 해답 코드를 보며 그림판으로 그림을 그려가며 익혔다. 내일부터는 이 개념을 숙지하고 활용하여 나머지 list 관련 문제들을 끝낼 수 있을 것 같다.

```

![old_lstadd_front](./img/old_lstadd_front.png)

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

- 요즘들어 늦게 일어나고 늦게 잠드는 것이 일상이 된 것 같다. 아무래도 같이 공부하는 동료와 시간대를 맞추려 하다보니 더욱 그런 것 같다.
- 차라리 계획표의 기준 시간대를 싹 뒤로 밀고 이 시간대까지 하는 걸 일반화 시키는 것도 나쁘지 않을 듯 하다.
- 특히, 오늘은 어제와 마찬가지로 너무나도 멘탈 관리가 힘든 날이었는데, 동료가 채찍질을 해준 덕분에 중도포기 하지 않고 끝까지 달릴 수 있었던 것 같다.
- string을 다룰 때 로직을 짜는 건 잘 되는데 구현이 어려운 걸 보면, 아직도 갈 길이 먼 것 같다. 좀 더 많이 다뤄보면 익숙해지겠지.
- 연결리스트는 봐도봐도 헷갈리는 느낌이었는데, 동료에게 연결리스트 개념을 가르쳐주기 위해 수업 준비를 하다보니, 많이 헷갈렸던 개념들이 촤라락 정리되었다.

## 9. 다음 학습 계획 (최소 5줄 이상)

- 내일은 연결리스트를 아주 뼛속까지 해체해서 이해하고 구현할 것이다.
- 또한, 백준 알고리즘 문제풀이도 재개할 것이다. 1주라는 제한 시간에 너무 얽매여있었던 것 같다.
- 또한!, 도메인을 구매해서 블로그 포스팅도 시작할 것이다.
- 그리고 이를 위해 수면 시간은 왠만하면 7시간 정도로 유지할 예정이다.
- 그렇다... 내일은 오늘보다 더 빡세게 달릴 것이다. 일론 머스크 빙의 가즈아!