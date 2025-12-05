---
title: 옵시디언 Tasks 플러그인-연습노트✏
status: planned
priority: medium
process: raw
source_name: 옵시디언 Tasks 플러그인-연습노트✏
source_author: "북트레싱"
source_type: " youtube"
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references:
  - "[[Tasks Plugin - 상태 검토 및 확인 2025-10-24 20-41-47]]"
  - "[[태스크(tasks)]]"
---
# 옵시디언 Tasks 플러그인-연습노트✏


## 태스크 기능 [연습 2024]

| 기능     | 기능                               |
| ------ | -------------------------------- |
| 마감날짜   | due date                         |
| 시작날짜   | start datae                      |
| 예정된 날짜 | scheduled date                   |
| 중요도    | high priority <br>medium prioiry |
| 반복     |                                  |

### 할일 작성 예시

- [x] 북프레싱 Tasks 플러그인 - 할 일 관리, 투투리스트, GTD 정리하기 🔼 📅 2025-03-17 ✅ 2025-03-19
- [x] 태스크 기능 완벽하게 익히고 원형보다는 각형으로 하기 ⏫ 📅 2025-03-21 ✅ 2025-03-19
- [x] 메타 프론트매터 기능 익히기 📅 2025-03-19 ✅ 2025-03-19

### 반복 할 일 설정
- 일을 완료시키면 due date가 다음날로 바뀌게 되면서 새로운 체크리스트가 생기게 된다. 

### 할 일 목록 설명
- ==체크박스 할일 내용 중요도 날짜 시작 마감 (작성된 노트: 백링크순) 연필아이콘 연기버튼==

### 할 일 목록 만들기
- Tasks 디폴트 : 모든 태스크가 보임
- 필터 : 원하는 것만 보게끔

### 할 일 목록 필터링
- 필터 기능은 and 조합되어 나온다. 

### 폴더 필터링 : 현재폴더
```tasks 
hide backlink
folder includes {{query.file.folder}}
```

### 폴더 필터링 : 특정 폴더 : Tasks PKM 구축 폴더
``` tasks
filter by function task.file.folder.includes("PKM 구축")
```

```tasks 
folder includes {{query.file.folder}}
```
---


## 태스크 기능 [[2025-10-24]]
- 백틱 넣고 tasks
- hide backlink
- due 날짜
- priority is above none 
- filter by function task.file.folder.includes("폴더 이름")  → 특정 폴더를 지정
- filter by function !task.file.folder.includes("life-disciplines-projects-main")  특정 폴더 제외
- [[Tasks Plugin - 상태 검토 및 확인 2025-10-24 20-41-47]]
```tasks
not done
hide backlink
filter by function !task.file.folder.includes("life-disciplines-projects-main")
```
## 필터 기능 [북트레싱 필터링 예제]

### 완료되지 않은 일 - ==not done==

### 완료된 일
- has done date
- no done date
- done (on|befor|after) \<date>|\<data range>

### 정렬
- sort by priority
- sort by due
- sort by start
- sort by scheduled
- sort by done
- sort by description
- sort by path
- sort by recurring
- sort by tag

### 숨김
- hide start date
- hide due date
- hide edit button
- ==hide backlink==
- hide task count

### 마감 기한
- ==due 2025-12-25==
- due before yesterday
- due today
- due after 3 days ago
- due in this week
- due after this month
- due or or before next year
- due in 2023-Www(ww에는 주, 2자리 숫자)
- due in 2023-10 (10월)
- due (before|after|in) \<data range>

### Priority
- ==priority is (above|below|not) (lowest|low|none|medium|high|highest)==
- 이렇게 조합해서 쓴다. 
- priority is above none 

## Custom Filter

### 비어있는 필드

#### 비어있는 작업 찾기

description regex matches /^$/

#### 비어있는 작업 제외하기

description regex does not match /^$/

### 폴더 필터링

#### 현재의 폴더에 들어있는 할 일

folder includes {{query.file.folder}}

#### 폴더를 포함

filter by function task.file.folder.includes("폴더 이름")

#### 폴더를 포함하지 않음
filter by function !task.file.folder.includes("life-disciplines-projects-main")




## 기본적인 쿼리 예시
Task 플러그인에서 자주 사용되는 유용하고 기본적인 쿼리 예시들을 몇 가지 알려드리겠습니다.
쿼리는 일반적으로 **필터(Filter)**, **정렬(Sort)**, **표시 설정(Display)**의 세 부분으로 구성됩니다.

### 1. 기본적인 쿼리 예시

#### 1-1. 오늘 기한인 완료되지 않은 작업

현재 날짜 기준으로 오늘까지 완료해야 하는 작업을 보여줍니다.

코드 스니펫

```
not done
due today
```

#### 1-2. 다음 주에 기한인 작업

향후 7일 이내에 기한이 도래하는 모든 작업을 보여줍니다.

코드 스니펫

```
not done
due before in 7 days
```

#### 1-3. 특정 태그가 있는 작업

노트에 `#프로젝트A` 태그가 붙어 있는 모든 작업을 보여줍니다.

코드 스니펫

```
not done
tag includes #프로젝트A
```

#### 1-4. 특정 파일(노트)의 작업

특정 마크다운 파일(노트)에 포함된 모든 작업을 보여줍니다.

코드 스니펫

```
not done
path includes 특정_노트_제목
```

---

### 2. 정렬 및 그룹화 예시

#### 2-1. 기한이 가장 임박한 순서로 정렬

모든 완료되지 않은 작업을 기한 날짜 순으로 정렬하고, 기한이 없는 작업은 아래로 보냅니다.

코드 스니펫

```
not done
sort by due reverse
```

#### 2-2. 기한별로 그룹화하고 중요도 순으로 정렬

기한 날짜별로 그룹을 만들고, 각 그룹 내에서는 중요도(`priority`)에 따라 정렬합니다.

코드 스니펫

```
not done
sort by due
group by due
sort by priority reverse
```

#### 2-3. 생성 날짜 기준으로 최신순 정렬

가장 최근에 생성한 작업을 위에서부터 보여줍니다.

코드 스니펫

```
not done
sort by created reverse
```

---

### 3. 표시 설정 (Display) 예시

#### 3-1. 중요도와 기한만 표시

결과 목록에서 작업의 중요도와 기한 정보만 보여주고 다른 정보(경로, 반복 등)는 숨깁니다.

코드 스니펫

```
not done
due today
show priority
show due date
hide start date
hide scheduled date
hide recurrence rule
hide task count 
```

#### 3-2. 모든 날짜 필드 숨기기

시작일(Start), 예약일(Scheduled), 기한일(Due)을 모두 숨깁니다.

코드 스니펫

```
not done
hide all dates
```

---

### 4. 고급 필터링 예시

#### 4-1. 오늘 시작해야 하는 작업

오늘부터 시작하기로 설정된 작업을 보여줍니다.

코드 스니펫

```
not done
starts today
```

#### 4-2. 이번 주 월요일부터 금요일 사이에 예약된 작업

Task 플러그인은 기간 필터링에 `YYYY-MM-DD` 형식 외에도 `YYYY-MM-DD`와 같은 날짜 키워드를 지원합니다.

코드 스니펫

```
not done
scheduled after 2025-10-20 # 예시로 지난 월요일
scheduled before 2025-10-24 # 예시로 지난 금요일
```

(Task 플러그인은 `scheduled after last monday`와 같은 상대적인 구문도 지원하므로, 사용 환경에 따라 테스트해 보세요.)

## 📓 청상

