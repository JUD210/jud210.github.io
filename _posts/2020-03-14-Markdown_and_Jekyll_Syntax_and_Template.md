---
title:  "Markdown & Jekyll 문법 및 템플릿 정리"
excerpt: "여러가지 문법 및 템플릿을 한데 모아놓아서 정리하였다."
tags:
  - Blog
  - GitHub Pages
  - Jekyll
  - minimal mistakes
  - hosting.kr
categories:
  - Diary
date: 2020-03-14 03:18:32 +0900
last_modified_at: 2020-03-14 03:18:35 +0900
---
## 들어가기에 앞서

이 글의 Markdown 코드는 **[여기서][gh-jud210-my_blog-this_post]** 자세히 볼 수 있다.  

## 마크다운 문법

마크다운 문법은 **[이 블로그][devinlife-md]**에서 많은 부분 참고하여 정리했다.

### 줄바꿈 (new line)

```md
마크다운에서는 이런식으로
써도 줄바꿈이 되지 않는다.

줄 끝에 스페이스를 2번  
붙여야 1칸 줄바꿈이 되고,

이런식으로 완전히

띄워써야 2칸 줄바꿈이 된다.
```

마크다운에서는 이런식으로
써도 줄바꿈이 되지 않는다.

줄 끝에 스페이스를 2번  
붙여야 1칸 줄바꿈이 되고,

이런식으로 완전히

띄워써야 2칸 줄바꿈이 된다.

### 강조 표시

```md
*기울이기*  
_기울이기_  
**굵게**  
__굵게__  
~~취소선~~
```

*기울이기*  
_기울이기_  
**굵게**  
__굵게__  
~~취소선~~

### 글머리 (Header) 예시

```md
# H1 예시
## H2 예시
### H3 예시
#### H4 예시
##### H5 예시
###### H6 예시
```

# H1 예시

## H2 예시

### H3 예시

#### H4 예시

##### H5 예시

###### H6 예시

### 코드 인용 (한 줄 짜리)

```md
`그냥 강조 표시로 사용하기도 함`
```

`그냥 강조 표시로 사용하기도 함`

### 코드 인용

~~~md
```python
def print_hi(name):
  print("hello", name)
print_hi('Tom')
```
~~~

```python
def print_hi(name):
  print("hello", name)
print_hi('Tom')
```

```md
~~~c++
int main(void)
{
  cin.tie(NULL);
  ios_base::sync_with_stdio(false);

  cout << PLUS;
  return (0);
}
~~~
```

```c++
int main(void)
{
  cin.tie(NULL);
  ios_base::sync_with_stdio(false);

  cout << PLUS;
  return (0);
}
```

\`\`\`와 \~\~\~ 둘 다 사용 가능하다.

{%- comment -%}

@@T Add

### 주소 링크

```md
[](){:target="_blank"}
[][]

```

{%- endcomment -%}

### 이미지 링크

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

{% assign filename = page.path | replace: '_posts/', '' %}

[gh-jud210-my_blog-this_post]: https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{filename}}
