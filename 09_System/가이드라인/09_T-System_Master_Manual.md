---
title: T09_T-System_Master_Manual
level: T09
file_role: system_config
source_name: Gemini & User Final Standardization (2025-11-30)
source_author: system / user
tags:
  - 영역/시스템/지식관리_규칙
  - 출처/인덱스_구조/시스템_문서
---
# 📚 09_T-System_Master_Manual


## 시스템 가이드라인 목록 (Dataview 집계)

현재 '09_System/가이드라인' 폴더에 축적되는 시스템 관련 문서들을 추적합니다.

```dataview
TABLE 
  status AS "상태",
  priority AS "중요도"
FROM "09_System/가이드라인"
WHERE 
  file_role = "system_config"
SORT file.name ASC
```
