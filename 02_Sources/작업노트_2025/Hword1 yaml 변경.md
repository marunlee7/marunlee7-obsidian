---
title: Hword1 yaml 변경
level: T02
file_role: article_atom
parent: 작업노트_2025
status: completed
priority: high
process: draft
source_author: self
source_type: worknote
action_required: none
difficulty: good
satisfaction: 3
references: ""
tags:
  - 출처/내부_활동/아이디어
---
# 📖 T02. 하루한자공부 - 개별한자  
- [ ] #task 하루한자공부 - 개별한자 📅 2025-12-04

## 작업 내용 상세하게

word_type: hanja

status: finalized → planned
priority: medium
process: definition → raw

source_name: 사단법인 한국어문회
source_author: self
source_type: book

action_required: memorize → deep_dive
difficulty: good 
satisfaction: 5 

## 린터하기 ← 삭제후(removed)
process: raw
action_required: deep_dive

## 삭제 ->  불필요 
source_name: 사단법인 한국어문회
source_author: self

source_name:
source_author: 

## 🗂️ 연결된 하위 노트 목록 (T03/T04/T05/T06)

```dataview
TABLE WITHOUT ID
link(file.path, file.name) AS "노트 제목",
file_role AS "유형",
priority AS "중요도",
process AS "진행단계"
FROM ""
WHERE
    contains(parent, this.file.name)
    AND (
        file_role = "concept_dictionary" OR  
        file_role = "personal_analysis" OR   
        file_role = "sentence_collection" OR 
        file_role = "person_data"            
    )
    AND file_role != "template"
SORT file_role ASC, file.name ASC
```
