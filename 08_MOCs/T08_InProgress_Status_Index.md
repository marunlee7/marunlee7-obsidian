---
title: T08_InProgress_Status_Index
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
# 📊 T08. 진행 중 작업 인덱스 (In-Progress Task Index)

## 📌 개요

* **목적:** `status: in-progress` 상태인 모든 T01, T02, T04 노트를 집계합니다.

## 🔗 진행 중 노트 목록 (Dataview 집계)

```dataview
TABLE 
  level AS "Level", 
  priority AS "중요도", 
  process AS "품질 단계"
FROM ""
WHERE 
  contains(file_role, ["series_collection", "article_atom", "personal_analysis"]) 
  AND status = "in-progress"
  AND !contains(file.name, "tp") 
SORT file.name ASC
```

> [!tip]+
> ⭐ `status: in-progress` 노트를 집계합니다.
