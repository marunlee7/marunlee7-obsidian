---
title: "{{value:T08_주제 영역 MOC 제목}}"
level: T08
file_role: concept_moc
tags:
  - 출처/인덱스_구조/주제_MOC
---
# 🗺️ T08. {{title}} (Concepts Map of Content)

## 📌 개요

* **목적:** 이 T08 파일은 특정 **주제 영역**과 관련된 모든 T03 개념 노트를 자동으로 집계하여 지식을 구조화합니다.

## 🗂️ 🔗 연결된 T03 개념 노트 (Dataview 집계)

*T03 폴더 내에서 특정 태그를 가진 모든 개념을 자동으로 집계합니다.*

```dataview
TABLE 
  word_type AS "유형",
  status AS "상태",
  link(parent) AS "출처 T02"
FROM "03_Concepts"
WHERE 
  contains(tags, "출처/개념_본질/어휘_용어") OR contains(tags, "출처/개념_본질/인물_인명")
SORT file.name ASC
```
