---
title: 프로세스 → final 목표로 진행
level: T02
file_role: article_atom
parent: 작업노트_2024
status: completed
priority: medium
process: final
source_name: 
source_author: self
source_type: worknote
action_required: link_to_t04
difficulty: good
satisfaction: 3
references: ""
tags: [출처/내부_활동/아이디어]
---
# 📖 T02. 프로세스 → Final 목표로 진행

## 작업 내용 상세하게

모든 계획 프로세스 → final 목표로 진행 





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
