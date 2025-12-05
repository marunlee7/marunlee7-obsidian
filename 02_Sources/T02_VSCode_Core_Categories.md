---
aliases: []
title: T02_VSCode_Core_Categories
published: ""
level: T02
file_role: article_atom
parent: T01_VSCode_Index
word_type: ""
status: planned
priority: medium
process: raw
source_name: ""
source_author: ""
source_type: ""
action_required: link_to_t04
difficulty: good
satisfaction: 3
references:
  - ""
tags:
  - 앱스/vscode
  - 출처/내부_활동/앱_학습
---
# 📖 T02_VSCode_Core_Categories (Source Note)


## T02 카테고리
[[T03_Concept_Workspace]]
1. 기본 설정
2. 필수 확장 프로그램
3. 터미널 + Git 연동
4. Markdown / Obsidian 연계
5. 파일 탐색기 & 작업 효율
6. 백업 & 동기화
7. 개발용 설정


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
