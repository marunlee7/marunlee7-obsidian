---
title: "T08_Waiting_Status_Index"
level: T08
file_role: concept_moc

parent: ""
word_type: "" 

status: "" 
priority: "" 
process: "" 

source_name: "" 
source_author: ""
source_type: ""

references: "" 
tags:
  - 출처/인덱스_구조/시스템_문서
---
# ⚠️ T08. 대기/보류 작업 인덱스 (Waiting/Blocked Task Index)

## 📌 개요

* **목적:** `status: waiting/blocked` 상태인 모든 T01, T02, T04 노트를 집계합니다.

## 🔗 대기/보류 노트 목록 (Dataview 집계)

```dataview
TABLE 
  level AS "Level", 
  priority AS "중요도", 
  process AS "품질 단계"
FROM ""
WHERE 
  contains(file_role, ["series_collection", "article_atom", "personal_analysis"]) 
  AND contains(status, ["waiting", "waiting/blocked"])
  AND !contains(file.name, "tp") 
SORT file.name ASC
limit 300
```

