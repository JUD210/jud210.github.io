---
title:  "Markdown & Jekyll 문법 및 템플릿 정리"
excerpt: "여러가지 문법 및 템플릿을 한데 모아놓아서 정리하였다."
tags:
  - Markdown
  - Jekyll
  - Syntax
  - Template

  - Blog
  - GitHub Pages
categories:
  - Markdown
date: 2020-03-14 04:44:26 +0900
last_modified_at: 2020-03-14 04:44:27 +0900
---
## 들어가기에 앞서

이 글의 Markdown 코드는 **[여기서][gh-jud210-my_blog-this_post]** 자세히 볼 수 있다.  

## 마크다운 문법 (Markdown Syntax)

마크다운 문법은 **[이 블로그][devinlife-md]**에서 많은 부분 참고하여 정리했다.

### 줄바꿈 (newline)

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

### 강조 표시 (font style)

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

### 글머리 (header)

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

### 한 줄 짜리 코드 인용 (one line code block)

```md
`그냥 강조 표시로 사용하기도 함`
```

`그냥 강조 표시로 사용하기도 함`

### 코드 인용 (code block)

~~~md
```python
def print_hi(name):
  print("hello", name)
print_hi('Tom')
```
~~~

```python
def print_hi(name):
  print("Hello", name)
print_hi('Tom!')
# Hello, Tom!
```

```md
~~~c++
int main(void)
{
  cin.tie(NULL);
  ios_base::sync_with_stdio(false);

  cout << "Hello!";
  return (0);
}
~~~
```

```c++
int main(void)
{
  cin.tie(NULL);
  ios_base::sync_with_stdio(false);

  cout << "Hello!";
  return (0);
}
```

\`\`\`와 \~\~\~ 둘 다 사용 가능하다.

<!-- 
@@T Add Contents!

### 주소 링크 (link)

```md
[](){:target="_blank"}
[][]

```

### 이미지 링크

Advanced

[
  ![]({{ site.url }}/assets/images/posts/2020-03--TIL/.png)
]({{ site.url }}/assets/images/posts/2020-03--TIL/.png)
 -->

### 인용문 (blockquote)

```md
> 인용문
```

> 인용문

```md
> 인용문 1
>> 인용문 2
>>> 인용문 3
```

> 인용문 1
>> 인용문 2
>>> 인용문 3

{% assign filename = page.path | replace: '_posts/', '' %}

[gh-jud210-my_blog-this_post]: https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{filename}}
[devinlife-md]: https://devinlife.com/howto%20github%20pages/markdown-syntax/
