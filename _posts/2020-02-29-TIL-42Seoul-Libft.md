---
title: "[TIL #6] 42서울: libft"
date: 2020-03-01 02:32:05 +0900
categories: TIL 42seoul
---

# 학습 레포트 (Today I Learned)

## 1. 학습 날짜

> 2020-02-29(토)

## 2. 학습시간

> 19:00 ~ 02:00 (집)

- [ 개인 스케쥴러: Life RPG Ignition (Season 3) ]\
  ☞ <https://goo.gl/qnehEQ>

- [ 오늘 하루는? - 일일 영상 리뷰]\
  ☞ <https://www.youtube.com/channel/UCYPWzViA-uq9sBop7ssYaEg>

## 3. 학습 범위 및 주제

- libft
  - strnstr
  - atoi
  - calloc
  - substr

## 4. 동료 학습 방법

> Hangout (인터넷 브라우저 화상 통화 / 화면 공유 / 토론)

- Hangout을 활용하여 yoolee, nakim, sujung, schang, dokang, ryukim, jinhkim, sangpark 등의 멤버들과 하루 종일 같이 공부.

> Slack: 42_seoul_global_random (메신저)

- 팁 공유 (세팅을 완료한 개발 환경 설정 파일들 공유 등)
- 전체 채팅 / DM 등을 활용한 짜잘한 질의 응답

## 5. 학습 목표

- string을 다루는 여러 함수 구현

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
[7H] libft
  strnstr, atoi, calloc, substr
    피씬 과정에서 확실히 이해하지 못 하고 넘어간 부분은
    어김없이 또다시 똑같은 문제를 낳았다..

    이번엔 메모리 할당 영역에 대한 이해력의 부족으로, 수 많은 segmentation fault (core dumped) 오류를 맛보았고, 도대체 왜?! 라는 의문 때문에 이를 해결하느라 많은 시간을 보내게 되었다.

    그리고 결국, 깨닫게 되었다...

    int *test(void)
    {
      // int arr[100];
      // ERROR!
      // warning: function returns address of local variable    [-Wreturn-local-addr]
      //   return (arr);
      //          ^
      // [1]    26439 segmentation fault (core dumped)  ./_TEST.out

      int *arr = malloc(sizeof(int) * 100);
      // SUCCESS!

      int i;

      for (i = 0; i < 10; i++)
        arr[i] = i;
      for (i = 0; i < 10; i++)
        printf("%d", arr[i]);\
      // 0123456789
      return (arr);
    }

    int main(void)
    {
      int *p_arr;
      int i;
      p_arr = test();
      printf("\n");
      for (i = 0; i < 10; i++)
        printf("%d", p_arr[i]);
      // 0123456789
    }

    호오오오울리..
    쉐ㅔㅔㅔㅔ...
```

## 8. 학습 내용에 대한 개인적인 총평 (최소 5줄 이상)

- libft-unit-test에서, libftest로 넘어오니, 쓰잘데기 없이 엄격하게 원함수를 구현하지 않아도 OK가 떴다.
- 이를 보니, libft-unit-test에서 뜨는 KO는 Moulinette조차 고려치 않는 빡센 테스트 케이스임을 직감적으로 알게 되었다... 젠장, 괜한 고생을 했다.
- 오늘은 전체적으로 많은 피로가 누적된 하루였기에, 친한 지인을 만나서 밥도 먹고, 예전부터 사고 싶었던 30만원대 의자를 하나 Flex! 해버렸다.
- 이후 집중이 안 되어 오늘 하루는 넘겨버릴까 했으나, 19시쯤 친한 동료가 회초리를 들고 나타나 따끔하게 일침을 놔주었고, 이에 화들짝 놀라 자극을 받은 나는 동료와 함께 2시까지 달렸다.
- 혼자서 하면 나태해지고 느슨해지는 내 고질적인 문제도, 동료와 함께하면 이렇게 쉽사리 해결되는구나 새삼스레 놀란 하루였다.

## 9. 다음 학습 계획 (최소 5줄 이상)

- libft part1을 겨우겨우 끝내고, 이제 part2로 넘어왔건만, 갈수록 태산이다. 아무래도 내일 이내로 파트2를 끝내기는 힘들지도 모르겠다.
- 하지만, 사유서라는 이름의 시말서를 쓰지 않기 위해선, 빡세게 달려서 꼭 파트2를 끝내고자 한다.
- 혼자서라면 정말 힘들게 풀어나갈 문제들이겠지만, 동료들로부터 배우면서, 그리고 동료들을 가르쳐주어 복습하면서 쭉 같이 나아가기에 충분히 풀어낼 수 있을 것 같다.
- 내일 libft part2를 끝내면, 일단 보너스 파트는 잠시 제껴두고 다른 쌓인 일들도 해야겠다.
- 기술 블로그, C++, 백준 알고리즘, ... 하고싶은 게 하루하루 쌓여가는 게 참 즐겁다ㅋㅋ
