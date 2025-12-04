---
title: <% tp.file.title %>
level: T03
file_role: concept_dictionary
parent: ""
word_type: term
status: in-progress
priority: high
process: draft
source_name: ""
source_author: self
source_type: article
action_required: deep_dive
difficulty: good
satisfaction: 4
references: []
tags:
---
# 🧩 한글(<% tp.file.title %>)



## 🔗 연결된 노트 목록 (T02/T04/T05/T06)
```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  file_role AS "유형",
  priority AS "중요도"
FROM ""
WHERE 
  contains(parent, this.file.name) 
  OR contains(references, this.file.name)
  OR contains(tags, this.file.name)
SORT file_role ASC, file.name ASC
```
