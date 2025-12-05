---
title: T08_Draft_Process_Index
level: T08
file_role: concept_moc

parent: ""
word_type: "" 
status: planned
priority: medium
process: raw


source_name: "" 
source_author: ""
source_type: ""
action_required: link_to_t04
difficulty:	good
satisfaction: 3

references: "" 
tags: [출처/인덱스_구조/시스템_문서]
---
# 📊 T08. 초안 품질 인덱스 (Draft Process Index)
[[문장수집-공부라는 구체적 경험을 다시 배우는 여름이다]]

## 📌 개요

* **목적:** `process: draft` 상태인 모든 T02, T03, T04 노트를 집계합니다 (내용 품질 관리).

## 🔗 초안 노트 목록 (Dataview 집계)

```dataview
TABLE 
  level AS "Level", 
  status AS "상태", 
  priority AS "중요도"
FROM ""
WHERE 
  contains(file_role, ["article_atom", "concept_dictionary", "personal_analysis"]) 
  AND process = "draft"
  AND !contains(file.name, "T0") 
SORT file.name ASC
```

