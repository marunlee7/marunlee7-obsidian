---
title: T08_Vault_Dashboard_old
level: T08_MOC_Index
file_role: system_index
parent: ""
status: planned
priority: medium
process: raw
source_name: System Dashboard
source_author: self
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: []
tags: []
---
# 📈 Vault 종합 관리 대시보드

## 📕 소개

이 파일은 Vault 내의 모든 파일 상태와 통계를 한눈에 보여주는 종합 대시보드 역할을 합니다. (DataviewJS가 아닌 일반 Dataview로 가능한 선에서 구성했습니다.)


이 대시보드는 T-시스템의 **전반적인 진행 상태**와 **파일 통계**를 제공하여 Vault 운영 현황을 모니터링합니다.

## 📁 주요 통계

### 1. 파일 개수 (T-레벨별)

```dataview
TABLE WITHOUT ID
  level AS "T-레벨", 
  length(rows) AS "파일 수"
FROM ""
WHERE !contains(file.name, "tp") AND file.name != this.file.name
GROUP BY level
SORT level ASC
````

### 2. 최신 수정된 노트 (전체)

```dataview
TABLE WITHOUT ID
  file.link AS "노트 제목",
  level AS "T-레벨",
  file.mtime AS "수정일"
FROM ""
WHERE !contains(file.name, "tp") AND file.name != this.file.name
SORT file.mtime DESC
LIMIT 10
```

### 3. 미완료된 작업 (Process: Draft)


```dataview
TABLE WITHOUT ID
  file.link AS "노트 제목",
  level AS "T-레벨",
  priority AS "중요도"
FROM ""
WHERE process = "draft" AND file.name != this.file.name
SORT file.mtime DESC
```

## 📊 Status 기반 통계 (4단계)

### 4. 상태별 파일 개수 요약 (Status별)


```dataview
TABLE WITHOUT ID
  length(rows) AS "파일 수"
FROM ""
WHERE !contains(file.name, "tp") AND file.name != this.file.name
GROUP BY status
SORT status ASC
```

> [!NOTE] 이 표를 통해 `planned`, `in-progress`, `waiting/blocked`, `completed` 4단계 상태별 파일 개수를 한눈에 파악할 수 있습니다.

### 5. ⚙️ T08 시스템 운영 준비 현황 (Operational Readiness)

시스템 설정 파일 중 구축이 미완료(`status: completed`가 아닌)된 파일을 추적합니다. **이 목록은 항상 비어있는 것이 정상**입니다.

```dataview
TABLE WITHOUT ID
  file.link AS "시스템 파일",
  status AS "현재 상태",
  process AS "품질 단계",
  file.mtime AS "최종 수정일"
FROM ""
WHERE
  file_role = "system_index" AND  
  status != "completed" AND      
  file.name != this.file.name AND 
  !contains(file.name, "tp") 
SORT file.mtime DESC
```

## 6. ⚠️ T01 누락 필드 점검 (Source 정보)

Quickadd 템플릿 업데이트 전에 생성된 T01 파일 중, 'source_type' 또는 'source_author' 필드가 누락된 파일을 표시합니다. 이 목록은 항상 비어있어야 합니다.

```dataview
TABLE WITHOUT ID
  file.link AS "T01 제목",
  default(source_type, "❌ 누락") AS "유형",
  default(source_author, "❌ 누락") AS "저자",
  file.mtime AS "최종 수정일"
FROM ""
WHERE
  file_role = "series_collection" AND
  (source_type = null OR source_author = null) AND 
  file.name != this.file.name AND 
  !contains(file.name, "tp") 
SORT file.mtime DESC
```


> [!note]
> 시스템 파일만 대상으로
> 완료되지 않은 파일만 표시

→ 개인참조 : [[vault 종합 관리 대시보드에 파일이 포함돠는 것]]


> [!tip]
> ⭐ `status: planned` 노트를 집계합니다.
