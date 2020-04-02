---
layout: post
title: 기술면접
date: 2020-03-01 16:22:51
categories: 면접
tags: 면접 개념 기초 Java OOP 오버로딩 오버라이딩 Interface Abstract CallByㅡ ㅡType 프로세스 스레드 접근제한자 디자인패턴 Java메모리영역 Get Post 세션 쿠키 MVC 프레임워크
comments_gitment: true
---
* TOC
{:toc}

# Java
1) 운영체제에 독립적

자바 응용프로그램은 운영체제나 하드웨어가 아닌 JVM과 통신하고, JVM이 자바 응용프로그램으로 부터
전달받은 명령을 해당 운영체제가 이해 할 수 있도록 변환하여 전달한다.
자바로 작성된 프로그램은 운영체제에 독립적이지만 JVM은 운영체제에 종속적이어서 여러 운영체제별로
설치 버전이 나뉘어 제공된다.

2) 객체지향언어

상속, 캡슐화, 다형성이 적용된 객체지향언어이다.
* 상속 : 
* 캡슐화 : 
* 다형성 : 

3) 자동 메모리 관리 (Garbage Collection)

시스템에서 더 이상 사용하지 않는 동적 할당된 메모리 블록을 찾아 다시 사용 가능하도록 회수한다.
자바로 작성된 프로그램이 실행되면, Garbage Collector가 자동적으로 메모리를 관리해주기 때문에
프로그래머는 메모리를 따로 관리하지 않아도 된다.
(이게 없으면 프로그래머가 메모리 체크, 반환을 수동처리 해야함)

4) 네트워크와 분산처리 지원

인터넷과 대규모 분산환경을 위해 다양한 네트워크 프로그래밍 라이브러리 (API) 를 통해 쉽게 개발 가능하도록
지원한다.

5) 멀티스레드 지원

일반적인 멀티스레드처럼 운영체제에 따라 구현방법이 다르지 않고 시스템에 관계없이 구현 가능하며,
관련 라이브러리 (API) 가 제공된다.

6) 동적 로딩 지원

자바는 동적 로딩을 지원하기 때문에 실행 시 모든 클래스가 로딩되지 않고 필요한 시점에 해당 클래스를
로딩하여 사용 할 수 있다. 이외에 어플리케이션 변경사항이 있더라도 적은 작업으로 적용 가능하고,
일부 클래스가 변경되어도 전체를 다시 컴파일하지 않아도 가능하다.

# OOP
OOP는 Object Oriented Programming의 약자, 객체지향 프로그래밍이며 객체지향의 특징은 아래와 같다.

1) 코드의 재사용성 ↑

새로운 코드를 작성 할 때 기존의 코드를 이용하여 쉽게 작성 할 수 있다.

2) 코드의 관리가 용이

코드 간의 관계를 이용하여 적은 뇨력으로 쉽게 코드를 변경 할 수 있다.

3) 신뢰성 높은 프로그래밍 가능

제어자와 메소드를 이용하여 데이터를 보호하고 올바른 값을 유지하도록 하며, 코드 중복을 제거하여
불일치로 인한 오동작을 방지 할 수 있다.

# AOP
```xml
ByteBuffer header = ByteBuffer.allocate(128);
ByteBuffer body   = ByteBuffer.allocate(1024);

ByteBuffer[] bufferArray = { header, body };

channel.read(bufferArray);
```

# 오버로딩 / 오버라이딩
## 오버로딩 (Overloading)
하나의 클래스에 동일한 이름의 메소드를 여러 개 정의한다.  → 메소드 신규 정의
* 메소드의 이름이 같아야 한다.
* 매개변수의 개수 또는 타입이 다르게 지정되어야 한다.
* 매개변수는 동일하고 리턴타입이 다른 경우 오버로딩이 성립되지 않는다.

```java
class A {
  public void print() { }
  public void print(int a) { }
  public void print(int a, String b) { }
}
```

## 오버라이딩 (Overriding)
조상클래스로부터 상속받은 메소드의 내용을 상속받는 클래스에 맞게 변경한다. → 메소드 내용 변경
* 선언부가 같아야 한다. (이름, 매개변수, 리턴타입 등)
* 접근제어자를 좁은 범위로 변경 할 수 없다.
- 조상의 메소드가 protected라면, 범위가 같거나 넓은 protected 혹은 public으로만 변경 가능하다.
* 조상클래스의 메소드보다 많은 수의 예외를 선언 할 수 없다.

```java
class A {
  public void print() { }
}
class B extends A {
  public void print() { }
}
```

# Interface / Abstract
New 연산자로 인스턴스 생성 불가하며, 프로토타입만 존재하는 메소드를 갖는다.
사용을 위해 하위 클래스에서 확장 및 구현을 해야 한다.

## Interface
* 추상 클래스이며 오직 추상 메소드와 상수만을 멤버로 갖고, Implements 키워드를 사용한다.
* 상속의 관계가 없는 클래스간 서로 공동되는 로직을 구현하여 쓸 수 있도록 한다.
* Extends는 하나의 클래스만 상속 가능하나 Interface는 다중 상속이 가능하다.
* 메소드 선언만 가능하고 일반 메소드를 사용 할 수 없다.

## Abstract
* 추상 메소드를 하나 이상 가진 클래스이며 자신의 생성자로 객체 생성 불가능하다.
* 하위 클래스를 참조하여 상위 클래스의 객체를 생성하거나 제어하기 위해 사용된다.
* 메소드 선언은 불가능하고 일반 메소드를 사용 할 수 있다.

# Call by ---
1) Call by References

매개변수의 원래 주소에 값을 저장하는 방식이고, 클래스 객체를 인수로 전달한 경우이다.

2) Call by Value

인수로 기본 데이터형을 사용하고, 주어진 값을 복사하여 처리하는 방식이다.
(메소드 내의 처리 결과는 밖의 변수에 영향을 주지 않는다.)

# Primitive / Reference Type
1) Primitive Type

변수에 값 자체를 저장 (정수, 실수, 문자, 논리) → **Wrapper Class**를 통해 객체로 변환 가능하다.

2) Reference Type

메모리 상에 객체가 있는 위치를 저장 → Class, Interface, Array 등

※ Wrapper Class : Primitive Type으로 표현 할 수 있는 간단한 데이터를 객체로 만들어야 할 경우 기능을 지원한다.

# 프로세스 / 스레드
크게 실행 중인 프로그램이라는 뜻으로 쓰이며, 프로세스 내에서 작업하는 각각의 작업을 스레드라고 한다.
즉, 프로세스 내에서 실행되는 세부 작업 단위로 최소 한 개에서 여러 개의 스레드가 하나의 프로세스를 이룬다.

1) 프로세스 (Process)

운영체제에서 실행 중인 하나의 실행 단위를 말하며 하나 이상의 스레드를 포함한다.

2) 스레드 (Thread)

프로세스 내에서 동시에 실행되는 독립적인 작업 단위를 말하며, 자원을 많이 사용하지 않고 구현이 쉬우며
범용성이 넓다.

# 접근 제한자
1) Public : 접근 제한이 없다. (동일한 프로젝트 내에서 모두 사용 가능)

2) Protected : 같은 패키지 안이나 다른 패키지에서 상속 받아 접근 가능하다.

3) Default : 같은 패키지 안에서만 접근 가능하다.

4) Private : 같은 클래스 안에서만 접근 가능하다.

# 디자인 패턴


# Java 메모리 영역
1) 메소드 영역

Static 변수, 전역변수, 코드에서 사용되는 Class 정보 등이 올라간다.
코드에서 사용되는 Class들을 로더로 읽어 클래스별로 런타임 필드데이터, 메소드 데이터 등을 분류해 저장한다.

2) 스택 (Stack)

지역변수, 함수 (메소드) 등이 할당되는 LIFO 방식의 메모리이다.

3) 힙 (Heap)

New 연산자를 통한 동적 할당된 객체들이 저장되며, Garbage Collection에 의해 메모리가 관리된다.

# Servlet / JSP
1) Servlet


2) JSP (Java Server Page)


# Get / Post 방식
1) Get (데이터 요청)
* 클라이언트에서 서버로 데이터를 전달할 때, 주소 뒤에 “이름”과 “값”이 결합된 쿼리 스트링 형태로 전달한다.
* 주소창에 쿼리 스트링이 그대로 보여지기 때문에 보안성이 떨어진다.
* 길이에 제한이 있다. (= 전송 데이터의 한계가 있다.)
* Post 방식보다 상대적으로 전송 속도가 빠르다
* 웹 브라우저에서 웹 서버로 전달되는 데이터가 인코딩되어 URL에 붙는다.
* 전달되는 데이터가 255개의 문자를 초과하면 문제가 발생 할 수 있다.

2) Post (데이터 전달)
* 일정 크기 이상의 데이터를 보내야할 때 사용한다.
* 서버로 보내기 전에 인코딩하고, 전송 후 서버에서는 다시 디코딩 작업을 한다.
* 주소창에 전송하는 데이터의 정보가 노출되지 않아 Get 방식에 비해 보안성이 높다.
* 속도가 Get 방식보다 느리지만 많은 데이터 전달을 위해 사용된다.
* 쿼리 스트링(문자열) 데이터 뿐만 아니라, 라디오 버튼, 텍스트 박스 같은 객체들의 값도 전송 가능하다.
* Get 방식처럼 전달되는 데이터가 보이지 않는다.

# 세션 / 쿠키
웹 사이트에서는 웹 페이지에 특정 방문자가 머무르고 있을 경우, 그 방문자의 상태를 지속시키기 위해 사용된다.

1) 세션 (Session)
* 특정 웹 사이트에서 사용자가 머무르는 기간 또는 한 명의 사용자의 한 번의 방문을 의미한다.
* 세션과 관련된 데이터는 Server에 저장된다.
* 웹 브라우저의 캐시에 저장되어 브라우저가 닫히거나 서버에서 삭제 시 사라진다.
* 쿠키에 비해 보안성이 좋다.

2) 쿠키 (Cookie)
* 사용자 정보를 유지할 수 없다는 HTTP의 한계를 극복할 수 있는 방법이다.
* 인터넷 웹 사이트의 방문 기록을 남겨 사용자와 웹 사이트 사이를 매개해주는 정보이다.
* 쿠키는 인터넷 사용자가 특정 웹 서버에 접속할 때, 생성되는 개인 아이디, 비밀번호, 방문한 사이트의 정보를 담은 임시 파일로서,
Server가 아닌 Client에 텍스트 파일로 저장되어 다음에 해당 웹서버를 찾을 경우 웹서버에서는 그가 누구인지 어떤 정보를 주로 찾았는지 등을 파악할 때 사용된다.
* 쿠키는 Client PC에 저장되는 정보이기 때문에, 다른 사용자에 의해서 임의로 변경이 가능하다. (정보유출 가능, 세션보다 보안성이 낮은 이유)

# MVC
객체지향 프로그래밍에서 MVC란, 사용자 인터페이스를 성공적이며 효과적으로 데이터 모형에 관련 시키기 위한 방법론 또는 설계 방식 중 하나이다.

MVC 패턴은 목적 코드의 재사용에 유용한 것은 물론, 사용자 인터페이스와 응용프로그램 개발에 소요되는 현저하게 줄여주는 형식이다.

※ MVC 구성요소

1) Model

소프트웨어 응용과 그와 관련된 고급 클래스 내의 논리적 데이터 기반 구조를 표현하며, 이 목적 모형은 사용자 인터페이스에 관한 어떠한 정보도 가지고 있지 않다.

2) View

사용자에게 보여지는 화면이며, 인터페이스 내의 구성요소들을 표현한다.

3) Controller

Model과 View를 연결하고 있는 클래스를 대표하며, Model과 View 내의 클래스들 간의 정보 교환을 위해 사용한다.

# 프레임워크 (Framework)
* 특정 형태의 소프트웨어 문제를 해결하기 위해 상호 협력하는 클래스 프레임과 인터페이스 프레임의 집합.
* 특정한 틀을 만들어 놓고 거기에 살을 붙여 놓음으로써 프로그램을 만들어 작업시간을 줄여주는 것이다.
* 프레임워크는 특정 개념들의 추상화를 제공하는 여러 클래스나 컴포넌트로 구성된다.
* 프레임워크는 이렇게 추상적인 개념들이 문제를 해결하기 위해 같이 작업하는 방법을 정의한다.
* 프레임워크는 좀 더 높은 수준에서 패턴을 조작한다.
* 프레임워크가 중요한 이유는 객체지향 개발을 하게 되면서 개발자의 취향에 따라 다양한 프로그램이 나오게 되었다.
프로그램 개발에 투입되는 개발자도 점점 늘어남에 따라 전체 시스템의 통합성, 일관성이 부족하게 되었기 때문이다.
* 개발 시간을 줄이고 오류를 줄일 수 있지만, 개발 능력 저하가 가장 큰 문제가 된다.

※ 스프링 프레임워크 (Spring Framework)
* Java 플랫폼을 위한 오픈소스 애플리케이션 프레임워크이다.
* 개발을 편하게 해주는 오픈소스 경량급 애플리케이션 프레임워크이다.
* Java 개발을 위한 프레임워크로 종속 객체를 생성해주고, 조립해주는 도구이다.
* Java 로 된 프레임워크로 Java SE로 된 Java 객체를 Java EE에 의존적이지 않게 연결해주는 역할이다.
* 경량 컨테이너로서 자바 객체를 직접 관리 => 각각의 객체 생성, 소멸과 같은 라이프 사이클을 관리하며 스프링으로부터 필요한 객체를 얻어올 수 있다.
* 스프링은 POJO(Plain Old Java Object) 방식의 프레임워크. => 일반적인 J2EE 프레임워크에 비해 구현을 위해 특정한 인터페이스를 구현하거나 상속을 받을 필요가 없어 기존에 존재하는 라이브러리 등을 지원하기에 용이하고 객체가 가볍다.
* 스프링은 제어의 역행(IoC : Inversion of Control)을 지원 => 컨트롤의 제어권이 사용자가 아니라 프레임워크에 있어서 필요에 따라 스프링에서 사용자의 코드를 호출한다.
* 스프링은 의존성 주입(DI : Dependency Injection)을 지원 => 각각의 계층이나 서비스들 간에 의존성이 존재할 경우 프레임워크가 서로 연결시켜준다.
* 스프링은 관점 지향 프로그래밍(AOP : Aspect-Oriented Programming)을 지원 => 따라서 트랜잭션이나 로깅, 보안과 같이 여러 모듈에서 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리할 수 있다.
* 스프링은 영속성과 관련된 다양한 서비스를 지원 => MyBatis나 Hibernate등 이미 완성도가 높은 데이터베이스 처리 라이브러리와 연결할 수 있는 인터페이스를 제공한다.
* 스프링은 확장성이 높음 => 스프링 프레임워크에 통합하기 위해 간단하게 기존 라이브러리를 감싸는 정도로 스프링에서 사용이 가능하기 때문에 수많은 라이브러리가 이미 스프링에서 지원되고 있고 스프링에서 사용되는 라이브러리를 별도로 분리하기도 용이하다.

※ Spring MVC 구조

1) DispatcherServlet

어플리케이션으로 들어오는 모든 Request를 받는 관문이다. Request를 실제로 처리할 Controller에게 전달하고 그 결과값을 받아서 View에게 전달하여 적절한 응답을 생성할 수 있도록 흐름을 제어한다.

2) HandlerMapping

Request URL 각각 어떤 Controller가 실제로 처리할 것인지 찾아주는 역할

3) Controller

Request를 직접 처리한 후 그 결과를 다시 DispatcherServlet에게 돌려준다.

4) ModelAndView

Controller가 처리한 결과와 그 결과를 보여줄 View에 관한 정보를 담고있는 객체이다.

5) ViewResolver

View관련 정보를 갖고 실제 View를 찾아주는 역할을 한다.

6) View

Controller가 처리한 결과값을 보여줄 View를 생성한다.

# 

   |   |   |   |
---|---|---|---|---
IO | 1 | 2 | /
NIO | 3 | 4 | 5


You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}