---
title: T08_인물사전_MOC
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
tags: [출처/인덱스_구조/주제_MOC]
---
# 👤 T08. 인물 사전 MOC

## 📌 개요

* **목적:** `word_type: person`으로 분류된 모든 T03 노트를 집계합니다.

## 🔗 T03 인물 개념 목록 (Dataview 집계)

```dataview
TABLE WITHOUT ID
  link(parent) AS "T02 원천"
FROM ""
WHERE 
  file_role = "concept_dictionary" 
  AND word_type = "person"
SORT file.name ASC
```


