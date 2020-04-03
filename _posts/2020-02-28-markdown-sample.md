---
layout: post
title: Markdown Sample
date: 2020-02-28 20:31:55
categories: Markdown
tags: Markdown
comments_gitment: true
---
I have some text.

I want some _italics_.

I want some __볼드(진하게)__

I want some **bold**.

I want some ~~cancel~~.

I want some <u>cancel</u>.

> test
>> test
>>> test

# this is heading 1

## this is heading 2

### this is heading 3

you want a list?
* first
* second
* third

you want an ordered list?
1. whatever
1. whatever
1. whatever
  
+ test
    - estt
      * stte
        + ttes

Jekyll uses Rouge by default for syntax highlighting, here are some tests.

Ruby:
{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Python with line numbers:
{% highlight python linenos %}
def print_hi(name):
    print("Hi, {}".format(name))

print_hi('Tom')
# prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

C with line numbers:
{% highlight c linenos %}
void print_hi(string name) {
  printf("Hi, %s", name);
}
print_hi("Tom");
/* prints 'Hi, Tom' to STDOUT. */
{% endhighlight %}

   |   |   |   |
---|---|---|---|---
IO | 1 | 2 | /
NIO | 3 | 4 | 5

>single tone：test

---

(1)
테스트  
테스트

(2)
테스트
테스트

(3)
테스트

테스트

|                  | 수학                        | 평가              |  
|:--- | ---: | :---: |  
| 철수             | 90            | 참잘했어요. |  
| 영희           | 50            | 분발하세요. |

$$f(x)= if x < x_{min} : (x/x_{min})^a$$  
$$otherwise : 0$$  
$$P(w)=U(x/2)(7/5)/Z$$  
$$p_{\theta}(x) = \int p_{\theta}(2z)p_{\theta}(y\mid k)dz$$  
$$x = argmax_k((x_t-x_u+x_v)^T*x_m)/(||x_b-x_k+x_l||)$$

<script type="text/javascript" 
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML">
</script>

```xml
⊙ 가상 머신
프로그램을 실행하기 위해 물리적 머신과 유사한 머신을 소프트웨어로 구현
```
ex) bash, cpp, dockerfile, markdown, yml, html, http, json, r, ruby, xml, sql ...

유형1(`설명어`를 클릭하면 URL로 이동) : [JDHCC 블로그](https://jdhcc.github.io "마우스를 올려놓으면 말풍선이 나옵니다.")  
유형2(URL 보여주고 `자동연결`) : <https://jdhcc.github.io>  
유형3(동일 파일 내 `문단 이동`) : [동일파일 내 문단 이동](#markdown의-반드시-알아야-하는-문법)

![](http://ifeve.com/wp-content/uploads/2013/06/scatter.png)

<img src="http://ifeve.com/wp-content/uploads/2013/06/scatter.png" width="300" height="200"> 

![composive][composive]

![io][io]

![io-match][io-match]

![io-match-2][io-match-2]

[io]: {{"/i0.jpg" | prepend: site.imgrepo }}
[io-match]: {{"/io-match.jpg" | prepend: site.imgrepo }}
[io-match-2]: {{"/io-match-2.jpg" | prepend: site.imgrepo }}
[composive]: http://my.csdn.net/uploads/201205/03/1336015104_5713.jpg