---
title: "T08_Concept_MOC_List"
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
# 🗺️ T08. MOC 파일 목록 (MOC Index Hub)

## 📌 개요

* **목적:** 시스템 내 모든 MOC 파일을 나열합니다.

## 🔗 모든 MOC 파일 목록 (Dataview 집계)

```dataview
TABLE WITHOUT ID 
  file.path AS "MOC 파일명"
FROM ""
WHERE 
  file_role = "concept_moc"
  AND !contains(file.name, "tp") 
SORT file.name ASC
```

