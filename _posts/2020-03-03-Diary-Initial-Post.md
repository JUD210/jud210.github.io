---
title:  "[Diary] 블로그 시작! (GitHub Page + Jekyll)"
excerpt: "GitHub Pages, Jekyll (minimal-mistakes), hosting.kr 이 세가지를 활용하여 개인 블로그를 만들었다."
tags:
  - Blog
  - GitHub Pages
  - Jekyll
  - minimal mistakes
  - hosting.kr
categories:
  - Diary
date: 2020-03-03 22:09:52 +0900
last_modified_at: 2020-03-14 16:54:40 +0900
---
{{ page.excerpt }}
* * *

## 2020-03-03 20:47:42 +0900

예전부터 생각만 하다 말았던 일을 제대로 실행하니 아주 마음에 든다.

[
  ![variable_ex1](/assets/images/posts/2020-03-03-Diary-Initial-Post/variable_ex1.png)
](/assets/images/posts/2020-03-03-Diary-Initial-Post/variable_ex1.png)

[
  ![variable_ex2](/assets/images/posts/2020-03-03-Diary-Initial-Post/variable_ex2.png)
](/assets/images/posts/2020-03-03-Diary-Initial-Post/variable_ex2.png)

위의 예시처럼, Jekyll + Markdown을 활용하면 일반 블로그에서는 불가능한 수많은 것들이 가능해진다! 개발자라면 한 번 도전해볼 만한 가치가 있지 않을까 싶다. 이제부터 차례차례 알아가며 적용해나갈 고급 기능들을 생각하니 벌써부터 흥분이 가라앉질 않는다.

이제부터 블로그에 계속해서 많은 기능들을 추가함과 동시에, 매일마다 조금씩이나마 Today I Learned를 작성할 것이다. 다만, 현재 코로나 때문에 42서울 본과정을 집에서 진행중이기에, 매일마다 작성해야 하는 학습 레포트를, 당분간은 그대로 복사해서 올려야겠다.

## 2020-03-13 01:58:24 +0900

Today I Learned 형식으로 레포트를 작성하고 포스팅하려니 너무 오랜 시간을 빼앗기는 것 같다. 어차피 애초에 레포트 작성은 42서울 지원금을 받기 위한 형식적인 절차이지 않은가. 짧게 작성해도 그만인데다가, 내용도 난잡하여 포스팅 거리가 되지 못 한다.

그러므로, 여태까지 올린 TIL 글은 전부 삭제하고, 지금부터는 공부한 내용을 짤막하게 정리하여 올리는 식으로 바꿔야겠다.

## 2020-03-14 16:37:01 +0900

동영상을 삽입하는 간단한 방법도 알아내었다. 정말 대단하다는 말 밖에 나오지 않는다ㅋㅋ 너무 맘에 든다.

어떻게 삽입했는지 궁금하다면 [이 글]({{ site.baseurl }}{% post_url 2020-03-14-Markdown_and_Jekyll_and_Liquid_Cheatsheet %}/#21-%EC%9C%A0%ED%8A%9C%EB%B8%8C-%EB%8F%99%EC%98%81%EC%83%81-%EC%82%BD%EC%9E%85-insert-a-youtube-video)에 상세히 적혀있으니 참고하기 바란다.

{% include video id="Gp43FNXxymU" provider="youtube" %}

## 참고 자료

- [GitHub Pages 블로그 따라하기](https://devinlife.com/howto/#1-github-pages-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%94%B0%EB%9D%BC%ED%95%98%EA%B8%B0/)
- [나만의 인터넷 주소 ─ 도메인을 구매하는 히치하이커를 위한 가이드](https://june.meson.kr/2018/07/various-things-with-your-own-domain.html)
- [쉽고 빠르게 수준 급의 GitHub 블로그 만들기 - jekyll remote theme으로](https://dreamgonfly.github.io/2018/01/27/jekyll-remote-theme.html)
- [Jekyll theme: minimal mistakes](https://github.com/mmistakes/minimal-mistakes)
