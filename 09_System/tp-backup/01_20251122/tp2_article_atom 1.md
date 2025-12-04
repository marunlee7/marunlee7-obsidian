---
title: <% tp.file.title %>

level: T02
file_role: article_atom

parent: "T01 시리즈 제목"
word_type: "t3전용"

status: "planned"
priority: "medium"
process: "raw"

source_name: "기사 제목 또는 출처 파일명"
source_type: "article"
source_author: ""

references: "원문 링크 또는 페이지 번호"
tags: ""
---
# 📖 <% tp.file.title %>


## 🗂️ 연결된 하위 노트 목록 (T03/T04)
```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  file_role AS "유형",
  priority AS "중요도"
FROM ""
WHERE 
  contains(parent, this.file.name) 
  AND (file_role = "dictionary" OR file_role = "personal_analysis") 
SORT file_role ASC, file.name ASC
```
