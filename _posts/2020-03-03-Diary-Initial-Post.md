---
title:  "블로그 시작! (GitHub Page + Jekyll)"
excerpt: "GitHub Pages, Jekyll (minimal-mistakes), hosting.kr 이 세가지를 활용하여 개인 블로그를 만들었다."
tags:
  - Blog
  - GitHub Pages
  - Jekyll
  - minimal mistakes
  - hosting.kr
categories:
  - Diary
date: 2020-03-04 00:09:52 +0900
last_modified_at: 2020-03-04 02:03:03 +0900
---

GitHub Pages + Jekyll (minimal-mistakes) + hosting.kr\
이 세가지를 활용하여 개인 블로그를 만들었다.

예전부터 생각만 하다 말았던 일을 제대로 실행하니 아주 마음에 든다.

```text
제목: {{ page.title }}
마지막으로 수정된 시간: {{ page.last_modified_at }}\
카테고리들: {{ page.categories }}
```

제목: {{ page.title }}\
마지막으로 수정된 시간: {{ page.last_modified_at }}\
카테고리들: {{ page.categories }}

위의 예시처럼, Jekyll Theme + Markdown을 활용하면 일반 블로그에서는 불가능한 수 많은 것들이 가능해진다! 개발자라면 한 번 도전해볼만 한 가치가 있지 않을까 싶다. 이제부터 차례차례 알아가며 적용해나갈 고급 기능들을 생각하니 벌써부터 흥분이 가라앉질 않는다.

## 참고

- [GitHub Pages 블로그 따라하기](https://devinlife.com/howto/#1-github-pages-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%94%B0%EB%9D%BC%ED%95%98%EA%B8%B0/){:target="_blank"}
- [나만의 인터넷 주소 ─ 도메인을 구매하는 히치하이커를 위한 가이드](https://june.meson.kr/2018/07/various-things-with-your-own-domain.html){:target="_blank"}
- [쉽고 빠르게 수준 급의 GitHub 블로그 만들기 - jekyll remote theme으로](https://dreamgonfly.github.io/2018/01/27/jekyll-remote-theme.html){:target="_blank"}
- [minimal mistakes](https://github.com/mmistakes/minimal-mistakes){:target="_blank"}
