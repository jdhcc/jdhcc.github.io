---
layout: post
title: Github 블로그 구동 관련
date: 2020-03-15 14:08:10
categories: Github
tags: Github Jekyll
comments_gitment: true
---

* TOC
{:toc}

---

## jekyll 구동

- CMD 창에서 Git의 레퍼지토리를 내려받을 디렉터리까지 접근 후 아래 명령어 입력
```scheme
C:\???>git clone (해당 레퍼지토리에 다운로드 url 복사-붙여넣기)
.............
........
Resolving deltas: 100% (??/??), done.
C:\???>cd (내려받은 레퍼지토리 명칭)
C:\???\(내려받은 레퍼지토리 명칭)>jekyll serve
.................
.......
.........
Server running... press ctrl-c to stop.
```

- 위와 같이 뜨면 내려받은 해당 레퍼지토리 안에 `.jekyll-cache` 디렉터리가 추가되고 로컬 서버 구동 완료. (https://localhost:4000/)
- 서버 종료는 Ctrl+C 키를 입력 후 다음과 같이 진행.
```scheme
C:\???\(내려받은 레퍼지토리 명칭)>jekyll serve
.................
.......
.........
Server running... press ctrl-c to stop.
일괄 작업을 끝내시겠습니까 (Y/N)? y
C:\???\(내려받은 레퍼지토리 명칭)>
```

---

## Git 커밋

- `Git Bash` 프로그램 실행.
- 내려받은 해당 레퍼지토리까지 접근.
- push 할 때 'git push' 입력 시 오류 발생하면 소괄호에 적힌 master 권한으로 push 할 것.
```scheme
$ git add .
$ git commit -m "(커밋 코멘트 입력)"
$ git push (origin master) 
```

---

## Repository Public / Private
특정 프로젝트를 Public 혹은 Private 로 변경 시 404 오류가 뜰 수 있다.  
이럴 경우 프로젝트를 다시 커밋하거나 아래의 방법을 사용한다.
```scheme
$ git commit --allow-empty -m "Trigger rebuild"
$ git push
```