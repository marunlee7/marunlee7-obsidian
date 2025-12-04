---
title: Templater 플러그인 명령어 사용 방법, 옵시디언 템플릿
priority: "medium"
process: "raw"
source_name: Templater 플러그인 명령어 사용 방법, 옵시디언 템플릿
source_type: " youtube"
source_author: "북트레싱"
references: https://www.youtube.com/watch?v=17tThWhNNGw&list=PL-KPFbwFiAWA3bR3QSK3w6r_XM0KRzEFl&index=6
links: 
---
# Templater 플러그인 명령어 사용 방법, 옵시디언 템플릿

![](https://www.youtube.com/watch?v=17tThWhNNGw)  

## 하일라이트

이번 영상은 Templater 플러그인 2편 중 첫 번째 영상으로 **Templater**의 설치 및 사용을 위해 알아야 할 필수적인 명령어에 대해 알아보았습니다.  
템플릿은 기본적으로 옵시디언에서 제공하기는 하나 **템플레이터** 플러그인을 사용하면 더욱 강력한 기능을 사용하실 수 있습니다.  
다음 2편에서는 1편에서 알아본 명령어를 사용하여 직접 템플릿을 작성하고 사용하는 방법에 대해서 알아보겠습니다.  

👍 명령어 예제 링크  
https://vo.la/iRzjW  

⏰ 타임스탬프  

00:00 인트로  
00:57 템플릿 개념 설명  
01:30 Templater 플러그인 설치  
02:14 옵션 및 설정  
03:03 사용 전 세팅  
04:05 명령어 작성 - 기초  

04:35 tp.file  
04:58 파일 생성일  
06:26 노트 제목  
06:48 제목 특정 부분  
08:14 노트 저장 폴더/경로  

08:43 tp.date  
09:52 주간 요일별 날짜  

11:30 tp.system  
12:24 드롭다운 메뉴  
13:55 텍스트 필드  


## 要約 ✍︎

### tp.title

<% tp.file.title %>

### 노트 제목

<% tp.file.title.slice(9) %> 
<% tp.file.title.slice(0, 3) %>
<% tp.file.title.split("+")[1] %>

### 노트 생성 날짜

<% tp.file.creation_date("YYYY-MM-DD") %>
<% tp.file.creation_date("YYYY년 M월 D일 dddd") %>

### 노트 저장 폴더

<% tp.file.folder() %>

### 노트의 최근 수정 날짜

<% tp.file.last_modified_date("YYYY-MM-DD") %>

### 노트의 PC 경로

<% tp.file.path() %>

### Tp Date

<% tp.date.now("YYYY-MM-DD"%>
<% tp.date.tomorrow("YYYY-MM-DD"%>
<% tp.date.yesterday("YYYY-MM-DD"%>

### 주간 날짜

한 주의 시작 - 설정 
일요일 <% tp.date.weekday("YYYY-MM-DD", 0) %>
월요일 <% tp.date.weekday("YYYY-MM-DD", 1) %>
화요일 <% tp.date.weekday("YYYY-MM-DD", 2) %>

### tp.system

### 클립 보드

<% tp.system.clipboard() %>

### 드롭다운 메뉴

<% tp.system.suggester(
["별5개", "별4개", "별3개", "별2개", "별1개"],
["★★★★★", "★★★★☆", "★★★☆☆", "★★☆☆☆", "★☆☆☆☆"]
) %>

### 텍스트 필드

<% tp.system.prompt("하나의 키워드로 정리하면?", "") %>

## 思索 🙇🏻
