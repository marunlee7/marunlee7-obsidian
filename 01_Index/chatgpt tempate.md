---
title: chatgpt tempate
level: T01
file_role: original_source

parent: ""
word_type: "" # T03 전용 필드 (빈 값 유지)
status: planned # 최종 확정: planned. Task 관리 기본값.

priority: medium
process: "" # T01은 process 필드 사용 안 함 (빈 값 유지)

source_name: "chatgpt tempate"
source_author: self
source_type: "article"
references: []
tags: [출처/외부_정보/아티클_웹, 출처/외부_정보/도서_단행본]
---
# 📚 T01. Chatgpt Tempate (Master Index)



## 📌 개요 (Overview)

* **목적:** 이 T01 파일은 {{source_name}}과 관련된 모든 T02 노트들을 집계하고 관리하는 마스터 허브입니다.
* **상태:** 이 프로젝트는 현재 {{status}} 상태입니다.

---

## 🔗 T02 소스 노트 목록 (Dataview 집계)

*이 노트와 parent 필드로 연결된 모든 T02 노트를 자동으로 집계합니다.*

```dataview
TABLE 
  status AS "진행 상태",
  priority AS "중요도",
  process AS "Process",
  link(file.path, file.name) AS "노트 제목"
FROM ""
WHERE 
  level = "T02" 
  AND contains(parent, this.file.name)
sort modified desc
// SORT file.name ASC
```

