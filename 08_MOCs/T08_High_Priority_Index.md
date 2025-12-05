---
title: T08_High_Priority_Index
level: T08
file_role: concept_moc
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3

tags: [출처/인덱스_구조/시스템_문서]
---
# ⚡ T08. 최고 중요도 인덱스 (High Priority Index)

## 📌 개요

* **목적:** `priority: high` 상태인 모든 노트를 집계합니다.

## 🔗 최고 중요도 노트 목록 (Dataview 집계)

```dataview
TABLE 
  level AS "Level", 
  status AS "상태", 
  process AS "품질 단계"
FROM ""
WHERE 
  priority = "high"
  AND contains(file_role, ["series_collection", "article_atom", "concept_dictionary", "personal_analysis"])
SORT file.name ASC
```
