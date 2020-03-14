---
title: "Markdown & Jekyll & Liquid Cheatsheet: 문법 및 템플릿 정리"
excerpt: "Markdown & Jekyll & Liquid의 문법 및 템플릿을 Cheatsheet 형식으로 한데 모아서 정리하였다."
tags:
- Markdown
- Jekyll
- Liquid
- Syntax
- Template

- Blog
- GitHub Pages
categories:
- Markdown
date: 2020-03-14 04:44:26 +0900
last_modified_at: 2020-03-14 18:53:34 +0900
---
{{ page.excerpt }}

## 0. 들어가기에 앞서

- 이 글에는 링크가 많이 있으니, 링크를 열 때는 마우스 가운데 휠 버튼을 클릭하여 새 탭으로 여는 것을 추천한다.
- 이 글의 Markdown 원문은 **[여기서][gh-jud210-my_blog-this_post]** 자세히 볼 수 있다. 블로그 내용과 비교하며 보면 참고가 많이 될 것이다.

## 1. 마크다운 문법 및 템플릿 정리<br>　(Markdown cheatsheet: syntax and template)

- 마크다운은 **[이 블로그][devinlife-md]**에서 많은 부분 참고하여 정리했다.

### 1.1. 줄바꿈 (Newline)

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

### 1.2. 강조 표시 (Font style)

```md
*기울게 (Italic)*  
**굵게 (Bold)**  
***굵고 기울게 (Bold & Italic)***

_기울게 (Italic)_  
__굵게 (Bold)__  
___굵고 기울게 (Bold & Italic)___

~~취소선 (Strikethrough)~~
```

*기울게 (Italic)*  
**굵게 (Bold)**  
***굵고 기울게 (Bold & Italic)***

_기울게 (Italic)_  
__굵게 (Bold)__  
___굵고 기울게 (Bold & Italic)___

~~취소선 (Strikethrough)~~

### 1.3. 글머리 (Header)

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

### 한 줄 짜리 코드 인용 (One line code block)

```md
`그냥 강조 표시로 사용하기도 함`
```

`그냥 강조 표시로 사용하기도 함`

### 1.4. 코드 인용 (Code block)

1\. (Good) \`\`\`

~~~text
```python
def print_hi(name):
  print("Hello", name)
print_hi('Tom')  # Hello Tom!
```
~~~

```python
def print_hi(name):
  print("Hello", name)
print_hi('Tom!')  # Hello Tom!
```

2\. (Good) ~~~

```text
~~~c++
#include <iostream>
using namespace std;

int main(void)
{
    cin.tie(NULL);
    ios_base::sync_with_stdio(false);

    cout << "Hello!";  // Hello!
    return (0);
}
~~~
```

```c++
#include <iostream>
using namespace std;

int main(void)
{
    cin.tie(NULL);
    ios_base::sync_with_stdio(false);

    cout << "Hello!";  // Hello!
    return (0);
}
```

3\. (Bad: No syntax highlighting) 4 spaces or 1 tab

```text
    public class HelloWorld
    {
        public static void main(String[] args) {
            System.out.println("Hello World!");  //Hello World!
        }
    }
```

    public class HelloWorld
    {
        public static void main(String[] args) {
            System.out.println("Hello World!");  //Hello World!
        }
    }

<!-- 
@@T Add Contents!

### 주소 링크 (link)

```md
[]()  
[](){:target="_blank"}  
[][]

```

### 이미지 링크

Advanced

[
![]({{ site.url }}/assets/images/posts/2020-03--TIL/.png)
]({{ site.url }}/assets/images/posts/2020-03--TIL/.png)
 -->

### 1.5. 인용문 (Blockquote)

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

## 2. Jekyll & Liquid 문법 및 템플릿 정리<br>　(Jekyll & Liquid cheatsheet: syntax and template)

### 2.1. 유튜브 동영상 삽입 (Insert a youtube video)

```liquid
{% raw %}{% include video id="Gp43FNXxymU" provider="youtube" %}{% endraw %}
```

{% include video id="Gp43FNXxymU" provider="youtube" %}

### 2.2. 변수 활용 (Use a variable)

```liquid
{% raw %}{% assign file_path = page.path | replace: '_posts/', '' %}
[이 글의 Markdown 원문][gh-jud210-my_blog-this_post] 구경하기

[gh-jud210-my_blog-this_post]: <https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{ file_path }}>{% endraw %}
```

{% assign file_path = page.path | replace: '_posts/', '' %}
[이 글의 Markdown 원문][gh-jud210-my_blog-this_post] 구경하기

[gh-jud210-my_blog-this_post]: <https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{ file_path }}>

### 2.3. 반복문 및 조건문 활용 (Use Loop and Conditional)

```liquid
{% raw %}{% assign target_time = "2020년 03월" %}

- {{ target_time }}에 작성된 포스트 목록
{% for post in site.posts %}
{% assign t = post.date | date: "%Y년 %m월" %}
  {% if t == "2020년 03월" %}
  - [\[{{ post.date | date: "%Y-%m-%d" }}\] {{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}{% endraw %}
```

{% assign target_time = "2020년 03월" %}

- {{ target_time }}에 작성된 포스트 목록
{% for post in site.posts %}
{% assign t = post.date | date: "%Y년 %m월" %}
  {% if t == "2020년 03월" %}
  - [\[{{ post.date | date: "%Y-%m-%d" }}\] {{ post.title }}]({{ post.url }})
  {% endif %}
{% endfor %}

<!-- Links -->

[devinlife-md]: <https://devinlife.com/howto%20github%20pages/markdown-syntax/>
