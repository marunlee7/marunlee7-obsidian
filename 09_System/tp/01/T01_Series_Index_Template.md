---
title: "{{value:T01_시리즈_제목_입력}}" 
level: T01
file_role: original_source

parent: ""
word_type: "" 

status: planned 
priority: medium
process: initial_capture /* 초기값 설정 */ 

source_name: "{{value:source_name}}" 
source_author: "{{value:source_author}}"
source_type: "{{value:출처_유형 source_type}}" 
references: []

tags: 
  - 출처/{{value:source_top}}/{{value:source_sub}}
  - 영역/{{value:area_top}}/{{value:area_sub}}
---

## 📌 1. 개요 (Overview)

- **목적:** 이 T01 파일은 **{{title}}**과 관련된 모든 T02 노트들을 집계하고 관리하는 마스터 허브입니다.
- **상태:** 이 프로젝트는 현재 **`<% tp.frontmatter.status %>`** 상태입니다.

---

## 🔗 2. T02 소스 노트 목록 (Dataview 집계)

*이 노트와 parent 필드로 연결된 모든 T02 노트를 자동으로 집계합니다.*

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  status AS "진행 상태",
  priority AS "중요도",
  process AS "Process"
FROM "02_Sources" 
WHERE
  contains(parent, this.file.name)
SORT file.mtime DESC
```

