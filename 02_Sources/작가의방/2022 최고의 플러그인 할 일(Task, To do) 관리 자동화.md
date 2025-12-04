---
aliases: []
source_name: 2022 최고의 플러그인 할 일(Task, To do) 관리 자동화
references: https://www.youtube.com/watch?v=KH_P3GKtS1k&list=PLy4SLsxzyLUUqeeQzFyXoS750M3_km_pq&index=13
links:
  - "[[옵시디언 Tasks 플러그인-할 일 관리하기, 투두리스트, GTD]]"
---
# 2022 최고의 플러그인 할 일(Task, To do) 관리 자동화

![](https://youtu.be/KH_P3GKtS1k?si=0V-OT4G_JKLTmQmC)  

## 📘 요약
정보의 관리로서 메모와 자기관리는 아주 밀접한 관계가 있는 것 같은데요, 
그래서 그런지 일정관리나 할 일 관리 같은 작업을 옵시디안으로 통합
2022년 최고의 플러그인으로 선정된 적이 있는 
[[GTD]](Get Things Done) 기반의 플러그인을 소개해 드립니다.

\*\*영상에 담지 못했는데 "hide tags"를 사용하시면 좀더 깔끔한 결과를 볼 수 있어요!  
[Obsidian Tasks Plugin](https://github.com/obsidian-tasks-group/obsidian-tasks)

⏰ 타임스탬프 
[00:00](https://www.youtube.com/watch?v=KH_P3GKtS1k) 하일라이트 
[00:16](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=16s) 오늘의 목표 
[00:47](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=47s) 소개 및 설치 
[01:45](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=105s) 중요 설정 
[03:18](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=198s) 기본 사용법 
[05:32](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=332s) 쿼리 사용법
[11:13](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=673s) 활용 
[11:47](https://www.youtube.com/watch?v=KH_P3GKtS1k&t=707s) 마무리(총평)

## 📘 연습

### 체크박스 체크/해제



### 쿼리 사용법
- 쿼리 명령어를 통해 '#task' 태그가 있는 할 일 목록을 불러오고, 
  원본 노트와 연동되어 체크 상태가 자동 반영됨.
- 쿼리 기능으로 '이번 주에 할 일', 마감일 임박한 할 일' 등
  다양한 조건으로 **필터링 목록 생성 가능**
- 폴더 필터 : filter by function !task.file.folder.includes("life-disciplines-projects-main")

### 쿼리 전체 | 아래는 위 Task를 가지고 쿼리만 다르게 한 것
```tasks
filter by function !task.file.folder.includes("life-disciplines-projects-main")
# 폴더 필터
```

### 쿼리 - 이번주에 할일
```tasks
not done
due in this week
```

### 쿼리 - due in next Week, Sort by Start, not doneX
```tasks
due in next week
sort by start
```

### 쿼리 - due in next Week, Sort by Start, not Done, Edit Button 숨김, Hide Backlink, 특정태그
```tasks
due in next week
sort by start
not done
tag includes #작업노트
hide task count
```


## 📓 청상

