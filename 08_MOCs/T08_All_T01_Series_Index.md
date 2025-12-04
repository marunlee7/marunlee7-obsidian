---
title: "T08_All_T01_Series_Index"
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
# 🗺️ T08. 모든 T01 시리즈 인덱스 (Master Series Hub)


## 📌 개요

* **목적:** 모든 T01 프로젝트/시리즈 노트를 집계하여 전체 작업 영역을 한눈에 파악합니다.

## 🔗 T01 시리즈 목록 (Dataview 집계)

```dataview
TABLE 
  status AS "상태", 
  priority AS "중요도"
FROM ""
WHERE 
  level = "T01" 
  AND file_role = "series_collection" 
  AND !contains(file.name, "tp") 
SORT file.name ASC
```
