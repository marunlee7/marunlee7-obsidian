---
title: "T08_한자어휘사전_MOC"
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
  - 출처/인덱스_구조/주제_MOC
---
# 📚 T08. 한자어휘 사전 MOC

## 📌 개요

* **목적:** `word_type: term`으로 분류된 모든 T03 노트를 집계합니다. (한자, 순우리말 등 일반 용어 포함)

## 🔗 T03 일반 용어 개념 목록 (Dataview 집계)

```dataview
TABLE WITHOUT ID
  link(parent) AS "T02 원천"
FROM ""
WHERE 
  file_role = "concept_dictionary" 
  AND word_type = "term"
SORT file.name ASC
```

