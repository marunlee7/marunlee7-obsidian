---
title: tp1_hword_series
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
<%* const T01Title = await tp.system.prompt("T01 시리즈 마스터 제목 입력 (예: 전광진의 하루한자와 격언)");
const sourceAuthor = await tp.system.prompt("저자 이름 입력");
const now = tp.date.now("YYYY-MM-DD");
_%>---
title: "<% T01Title %>"
aliases: []
level: "T01_Series_Master"
file_role: "series_collection"
parent: ""

source_name: "<% T01Title %>"
source_author: "<% sourceAuthor %>"
source_type: "column_series"

tags: 
  - 출처/문헌/칼럼 
  - 영역/인문학/언어학 

created: <% now %>
modified: <% now %>
status: "📙 예정"
priority: "medium"
published: 
pages: 
reading_days: 
references:
cover_url:
checkbox: false
read: false
---

# <% T01Title %> (T01 마스터)


## 📕 T02 개별 칼럼 목록 (작업노트)

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "칼럼 제목",
  process AS "가공 상태",
  priority AS "중요도"
FROM ""
WHERE 
  parent = this.file.link 
  AND level = "T02"
SORT created ASC
```


## 📕 사색 (T01 단계의 자료 전체에 대한 큰 틀의 사색)

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "제목",
  process AS "가공 상태"
FROM ""
WHERE 
  parent = this.file.link 
  AND source_author = "self" 
SORT modified DESC
```

## 📕 MOC (T02 Chapter List)

<p>Dataview를 통해 목록화된 T02 칼럼을 확인하세요.</p>

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) as "제목",
  choice(checkbox, "❗", "") AS "❗", 
  choice(read, "✓", "") AS "✓", 
  process AS "가공 상태", 
  dateformat(created, "yy-MM-dd") as "시작일",
  dateformat(modified, "yy-MM-dd") as "종료일"
FROM ""
WHERE 
  parent = this.file.name 
  AND file_role = "article_atom" 
SORT file.name asc
```

