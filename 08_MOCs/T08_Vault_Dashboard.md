---
title: "T08_Vault_Dashboard"
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
# 🏠 T08. 볼트 대시보드 (Vault Dashboard)

## 📌 개요

* **목적:** 전체 볼트의 T02/T04 Task 상태 및 작업 현황을 요약합니다.

## 🔗 T02/T04 Task 상태별 개수 (Dataview 집계)

```dataview
TABLE 
  count(file.name) AS "노트 수"
FROM ""
WHERE 
  level = "T02" OR level = "T04"
GROUP BY 
  status AS "T02/T04 Task 상태"
SORT "T02/T04 Task 상태" ASC
```


> [!tip]
> ⭐ 볼트 현황을 요약하는 대시보드 파일입니다.
