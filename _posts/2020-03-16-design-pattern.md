---
layout: post
title: 디자인 패턴 (Design Pattern)
date: 2020-03-16 10:42:44
categories: Java
tags: 디자인패턴
comments_gitment: true
---

* TOC
{:toc}

---

## 디자인 패턴이란
사람들이 수많은 시간동안 프로그램으로 여러 형태의 문제들을 해결해왔는데, 문제의 타입별로 해결하기 좋은 프로그래밍 패턴들이 있다는 것이 알려졌고 
여기에 이름들이 붙여졌다.  
주로 많이 알려진 디자인 패턴은 아래와 같다.

1) 생성 패턴
* [추상 팩토리 패턴](https://blog.naver.com/2feelus/220643071966){:target="_blank"}
* [빌더 패턴](https://blog.naver.com/2feelus/220644096727){:target="_blank"}
* [팩토리 메소드 패턴](https://blog.naver.com/2feelus/220643025321){:target="_blank"}
* [싱글톤 패턴](https://blog.naver.com/2feelus/220644592271){:target="_blank"}

2) 구조 패턴
* [어댑터 패턴](https://blog.naver.com/2feelus/220652075568){:target="_blank"}
* [브리지 패턴](https://blog.naver.com/2feelus/220654144018){:target="_blank"}
* [컴포지트 패턴](https://blog.naver.com/2feelus/220654147319){:target="_blank"}
* [데코레이터 패턴](https://blog.naver.com/2feelus/220654152753){:target="_blank"}
* [파사드 패턴](https://blog.naver.com/2feelus/220654732639){:target="_blank"}
* [프록시 패턴](https://blog.naver.com/2feelus/220655183083){:target="_blank"}
* [플라이웨이트 패턴](https://blog.naver.com/2feelus/220669069127){:target="_blank"}

3) 행위패턴
* [책임 연쇄 패턴](https://blog.naver.com/2feelus/220655715030){:target="_blank"}
* [반복자 패턴](https://blog.naver.com/2feelus/220655749483){:target="_blank"}
* [중재자 패턴](https://blog.naver.com/2feelus/220658501378){:target="_blank"}
* [전략 패턴](https://blog.naver.com/2feelus/220658663151){:target="_blank"}
* [커맨드 패턴](https://blog.naver.com/2feelus/220661208276){:target="_blank"}
* [방문자 패턴](https://blog.naver.com/2feelus/220664244510){:target="_blank"}
* [인터프리터 패턴](https://blog.naver.com/2feelus/220664898533){:target="_blank"}
* [메멘토 패턴](https://blog.naver.com/2feelus/220665171889){:target="_blank"}
* [옵저버 패턴](https://blog.naver.com/2feelus/220665210026){:target="_blank"}
* [상태 패턴](https://blog.naver.com/2feelus/220667630164){:target="_blank"}
* [템플릿 메소드 패턴](https://blog.naver.com/2feelus/220669520535){:target="_blank"}
* [널 오브젝트 패턴](https://blog.naver.com/2feelus/220669532267){:target="_blank"}

#### 객체 지향과 디자인 패턴의 관계
디자인 패턴이란 용어자체는 OOP와 직접적인 관련은 없으며, 디자인 패턴이라는 말 자체는 어떤 프로그래밍 방법론에도 사용될 수 있다.  
그러나 OOP라는 프로그래밍 방식은 디자인 패턴이라는 프로그래밍 방식과 매우 잘 어울리며 실제로 거의 함께 쓰이곤 하는 용어이다.  
그 이유는 객체 (Object)라는 개념이 가진 "변화적인 성질 (변이성)" 때문이다.  
일반적으로 객체라는 것은 때에 따라 생성되고, 객체의 성질이나 값을 부여받고, 스스로 일들을 수행하고, 다른 객체에게 값을 전달하고 소멸한다. 
즉 메모리에 태어났다가, 변경되고, 소멸된다.  
이런 변이성은 디자인 패턴에서 가장 많이 언급되는 아래의 방법론과 매우 잘 어울린다.

* 생성패턴 : 객체의 생성에 대한 방법
* 구조패턴 : 객체와 객체 사이의 상속/조합 관계설정 방법
* 행위패턴 : 객체가 특정 행동을 함으로서 다른 객체에 값을 전달하는 방법

Design Patterns이라고 하면 OOP를 빼놓고 얘기할 수가 없게 되었다.  
디자인 패턴은 효율적이며 가독성이 높은 코드를 지향할 뿐 아니라, 항상 재사용성이 높은 코드를 염두에 두고 있다.  
절차적 프로그래밍에서도 효율적이며 가독성이 높을수는 있지만, OOP에서의 디자인 패턴은 재사용성과 그를 바탕으로 한 관리 용이성 또한 염두에 두고 있다.
