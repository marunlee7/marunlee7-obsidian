---
title: "T08_Completed_Status_Index"
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
# 📊 T08. 완료된 작업 인덱스 (Completed Task Index)

## 📌 개요

* **목적:** `status: completed` 상태인 모든 T01, T02, T04 노트를 집계합니다.

## 🔗 완료된 노트 목록 (Dataview 집계)

```dataview
TABLE 
  level AS "Level", 
  priority AS "중요도", 
  process AS "품질 단계"
FROM ""
WHERE 
  contains(file_role, ["series_collection", "article_atom", "personal_analysis"]) 
  AND status = "completed"
  AND !contains(file.name, "tp") 
SORT file.name ASC
```

