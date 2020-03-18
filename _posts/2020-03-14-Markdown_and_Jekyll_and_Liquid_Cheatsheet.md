---
title: "[Blog] Markdown & Jekyll & Liquid Cheatsheet: 문법 및 템플릿 정리"
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
- Blog
date: 2020-03-14 04:44:26 +0900
last_modified_at: 2020-03-15 07:28:00 +0900
---
{{ page.excerpt }}
* * *

<!-- markdownlint-disable -->

## 0. 들어가기에 앞서

- 이 글에는 링크가 많이 있으니, 링크를 열 때는 마우스 가운데 휠 버튼을 클릭하여 새 탭으로 여는 것을 추천한다.
- 이 글의 Markdown 원문은 **[여기서][gh-jud210-my_blog-this_post]** 자세히 볼 수 있다. 블로그 내용과 비교하며 보면 참고가 많이 될 것이다.

## 1. 마크다운 문법 및 템플릿 정리<br>　(Markdown cheatsheet: syntax and template)

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

### 1.4. 정렬 목록 (Ordered list)

```md
(Good)  

1. C
2. C++
3. Java
4. Python
```

(Good)

1. C
2. C++
3. Java
4. Python

```md
(Bad)

0. 사실
8. 이렇게 써도
0. 결과는 같지만,
3. 안 좋은 습관이다.
```
(Bad)

0. 사실
8. 이렇게 써도
0. 결과는 같지만,
3. 안 좋은 습관이다.

### 1.5. 비정렬 목록 (Unordered list)

```md
(Recommended)

- Python
  - Conditional statement
    - if
```

(Recommended)

- Python
  - Conditional statement
    - if

```md
+ Python
  + Conditional statement
    + if
```

+ Python
  + Conditional statement
    + if

```md
* Python
  * Conditional statement
    * if
```

* Python
  * Conditional statement
    * if

```md
- Python
  + Conditional statement
    * if
```

- Python
  + Conditional statement
    * if

### 1.6. 수평선 (Horizontal line)

```md
* * *
***
*****
- - -
---------------------------------------
```

* * *
***
*****
- - -
---------------------------------------

### 1.7. 주소 링크 (URL link)

```md
- URL 자체 링크 (Bare URL link)
  - <http://www.google.com>  

- 이름 및 URL 링크
  - [Inline-style link](https://www.google.com)
  - [Reference-style link][Arbitrary case-insensitive reference text]
  - [Relative reference to a link](/markdown/Markdown_and_Jekyll_and_Liquid_Cheatsheet/)
  - [Relative reference to a repository file](/assets/images/bio-photo-mini.jpg)

[arbitrary case-insensitive reference text]: http://www.google.com

- 새 탭으로 열기 (Open in new tab)
  - <http://www.google.com>{:target="_blank"}
  - [Inline-style link](https://www.google.com){:target="_blank"}
```

- URL 자체 링크 (Link bare-URL)
  - <http://www.google.com>

- 이름 및 URL 링크 (Link URL with name)
  - [Inline-style link](https://www.google.com)
  - [Reference-style link][Arbitrary case-insensitive reference text]
  - [Relative reference to a link](/markdown/Markdown_and_Jekyll_and_Liquid_Cheatsheet/)
  - [Relative reference to a repository file](/assets/images/bio-photo-mini.jpg)

[arbitrary case-insensitive reference text]: http://www.google.com

- 새 탭으로 열기 (Open in new tab)
  - <http://www.google.com>{:target="_blank"}
  - [Inline-style link](https://www.google.com){:target="_blank"}

### 1.8. 이미지 삽입 (Insert image)

```md
- 이미지 삽입
  - Inline-style 
![Alternative Text](/assets/images/bio-photo-mini.jpg)
  - Inline-style 가운데 정렬 (Align center) by Jekyll
![Alternative Text](/assets/images/bio-photo-mini.jpg){: .align-center}
  - Reference-style
![Alternative Text][bio-photo-mini]

[bio-photo-mini]: /assets/images/bio-photo-mini.jpg

- 클릭 시 전체화면 (Click to view in fullscreen mode)
  - Inline-style
[
  ![Alternative Text](/assets/images/bio-photo-mini.jpg)
](/assets/images/bio-photo-mini.jpg)
  - Reference-style 
[![Alternative Text][bio-photo-mini]][bio-photo-mini]
```

- 이미지 삽입
  - Inline-style 
![Alternative Text](/assets/images/bio-photo-mini.jpg)
  - Inline-style 가운데 정렬 (Align center) by Jekyll
![Alternative Text](/assets/images/bio-photo-mini.jpg){: .align-center}
  - Reference-style
![Alternative Text][bio-photo-mini]

[bio-photo-mini]: /assets/images/bio-photo-mini.jpg

- 클릭 시 전체화면 (Click to view in fullscreen mode)
  - Inline-style
[
  ![Alternative Text](/assets/images/bio-photo-mini.jpg)
](/assets/images/bio-photo-mini.jpg)
  - Reference-style 
[![Alternative Text][bio-photo-mini]][bio-photo-mini]

### 1.9. 각주 (Footnote)

```md
각주1 [^1], 각주2 [^2]

[^1]: 테스트 1
[^2]: 테스트 2
```

<!-- @@T 각주를 이쁘게 꾸미고 싶다면 [이 글]() 참고 -->

각주1 [^1], 각주2 [^2]

[^1]: 테스트 1
[^2]: 테스트 2

### 1.10. 인용문 (Blockquote)

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

### 1.11. 한 줄 짜리 코드 인용 (One line code block)

```md
A single<br>line break  
`A single<br>line break`  
```

A single<br>line break  
`A single<br>line break`  

### 1.12. 코드 인용 및 문법 강조 (Code block and Syntax highlighting)

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

### 1.13. 표 작성 (Create a table)

```md
- 좌측 정렬 (Align left)

| 항___목 | 가___격 | 개___수 |
| ------- | ------- | ------- |
| 라면    | 800원   | 10개    |
| 과자    | 900원   | 20개    |
```

- 좌측 정렬 (Align left)

| 항___목 | 가___격 | 개___수 |
| ------- | ------- | ------- |
| 라면    | 800원   | 10개    |
| 과자    | 900원   | 20개    |

```md
- 중앙 정렬 (Align center)

| 항___목 | 가___격 | 개___수 |
| :-----: | :-----: | :-----: |
|  라면   |  800원  |  10개   |
|  과자   |  900원  |  20개   |
```

- 중앙 정렬 (Align center)

| 항___목 | 가___격 | 개___수 |
| :-----: | :-----: | :-----: |
|  라면   |  800원  |  10개   |
|  과자   |  900원  |  20개   |

```md
- 좌측 - 중앙 - 우측 정렬 (Align left - center - right)

| 항___목 | 가___격 | 개___수 |
| :------ | :-----: | ------: |
| 라면    |  800원  |    10개 |
| 과자    |  900원  |    20개 |
```

- 좌측 - 중앙 - 우측 정렬 (Align left - center - right)

| 항___목 | 가___격 | 개___수 |
| :------ | :-----: | ------: |
| 라면    |  800원  |    10개 |
| 과자    |  900원  |    20개 |

```md
- Don't recommend this! Use table formatter

|항___목|가___격|개___수|
|:-|:-:|-:|
|라면|800원|10개|
|과자|900원|20개|
```

- Don't recommend this! Use table formatter

|항___목|가___격|개___수|
|:-|:-:|-:|
|라면|800원|10개|
|과자|900원|20개|

## 2. Jekyll & Liquid 문법 및 템플릿 정리<br>　(Jekyll & Liquid cheatsheet: syntax and template)

### 2.1. 유튜브 동영상 삽입 (Insert a youtube video)

```liquid
{% raw %}{% include video id="Gp43FNXxymU" provider="youtube" %}{% endraw %}
```

{% include video id="Gp43FNXxymU" provider="youtube" %}

### 2.2. 포스트 링크 삽입 (Insert a link to a post)

```liquid
{% raw %}[Link this post]({{ site.baseurl }}{% post_url 2020-03-14-Markdown_and_Jekyll_and_Liquid_Cheatsheet %}){% endraw %}
```

[Link this post]({{ site.baseurl }}{% post_url 2020-03-14-Markdown_and_Jekyll_and_Liquid_Cheatsheet %})

### 2.3. 변수 활용 (Use a variable)

```liquid
{% raw %}{% assign file_path = page.path | replace: '_posts/', '' %}
[이 글의 Markdown 원문][gh-jud210-my_blog-this_post] 구경하기

[gh-jud210-my_blog-this_post]: <https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{ file_path }}>{% endraw %}
```

{% assign file_path = page.path | replace: '_posts/', '' %}
[이 글의 Markdown 원문][gh-jud210-my_blog-this_post] 구경하기

[gh-jud210-my_blog-this_post]: <https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{ file_path }}>

### 2.4. 반복문 및 조건문 활용 (Use Loop and Conditional)

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

## 참고 자료

- [Markdown 문법 알아보기](https://devinlife.com/howto%20github%20pages/markdown-syntax)
- [Markdown-Chatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
