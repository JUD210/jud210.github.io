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
date: 2020-03-04 00:09:52 +0900
last_modified_at: 2020-03-04 20:47:42 +0900
---
## 들어가기에 앞서

이 글의 Markdown 코드는 [여기서][gh-jud210-my_blog-this_post] 자세히 볼 수 있다.  
또한, [이 글][devinlife-md]의 많은 부분을 참조했음을 미리 알린다.

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

코드 스니펫

```python
# test
def print_hi(name):
  print("hello", name)
print_hi('Tom')
```

```cpp
// test
int main(void)
{
  cin.tie(NULL);
  ios_base::sync_with_stdio(false);

  cout << PLUS;

  return (0);
}
```

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[devinlife-md]: https://devinlife.com/howto%20github%20pages/markdown-syntax/

{% assign filename = page.path | replace: '_posts/', '' %}

[gh-jud210-my_blog-this_post]: https://raw.githubusercontent.com/JUD210/my_blog/master/_posts/{{filename}}
