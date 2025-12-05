---
title: T-시스템 구조 변경 작업 리스트
level: T02
file_role: original_source
parent: 작업노트_2025
status: completed
priority: high
process: draft
source_name: ""
source_author: self
source_type: worknote
action_required: none
difficulty: good
satisfaction: 3
references: ""
tags:
  - task
  - 출처/내부_활동/아이디어
---
## 📝 T-시스템 구조 변경 작업 리스트 (최종 포함)

이전 회신에서 제시해 드린 **T-시스템 YAML 구조 변경 작업 리스트**와 **예상 소요 시간**에, 방금 요청하신 **대화 기록 요약**을 포함하여 최종적으로 완성했습니다.

### 📌 1. 📅 대화 기록 요약

|**필드**|**내용**|**기록 일시**|
|---|---|---|
|**기록 일시**|2025-12-05 (금) 오후 12:22||
|**주제**|T-시스템 템플릿 논의 순서 재확인||
|**핵심 질문**|모든 혼란을 폐기하고 **'오늘 아침 확정 표준'**을 기준으로 논의를 재시작한다면, 논리적인 순서에 따라 T01 템플릿부터 다시 검토해야 함을 요청.||

---

### 2. 🗓️ 최종 작업 리스트 및 예상 소요 시간

| **작업 요소**            | **예상 소요 시간**                | **비고**                                            |
| -------------------- | --------------------------- | ------------------------------------------------- |
| **전체 파일 백업**         | 10분                         | 모든 작업 시작 전 **필수**                                 |
| **폴더명 변경 (2번)**      | 5분                          | `05_MOCs` $\rightarrow$ `05_Collection`           |
| **대량 치환 작업 (1, 3번)** | 20분                         | `file_role` 등 핵심 키값 변경                            |
| **메타데이터 수정/추가 (4번)** | 25분                         | `process`, `priority`, `status` 유효값 통일 및 필수 필드 추가 |
| **태그 점검 (1번)**       | 30분 ~ 3시간                   | **수동 재분류** 필요성에 따라 가장 가변적                         |
| **총 예상 소요 시간**       | **최소 1시간 30분 ~ 최대 4시간 10분** | 태그 재분류 작업량에 따라 달라짐                                |

---

### 3. 🛠️ T-시스템 YAML 구조 변경 작업 리스트 (VS Code 대량 치환용)

안정적인 작업을 위해 **T05 폴더 변경**을 **가장 먼저** 수행해야 합니다.

|**#**|**파일 대상**|**이전 값 (OLD)**|**새 값 (NEW)**|**VS Code 치환 규칙**|
|---|---|---|---|---|
|**1.**|T01 파일 전체|`file_role: series_collection`|`file_role: original_source`|`file_role: series_collection` $\rightarrow$ `file_role: original_source`|
|**2.**|T02 파일 전체|`file_role: article_atom`|`file_role: original_source`|`file_role: article_atom` $\rightarrow$ `file_role: original_source`|
|**3.**|T05 파일 전체|`file_role: concept_moc`|`file_role: sentence_collection`|`file_role: concept_moc` $\rightarrow$ `file_role: sentence_collection`|
|**4.**|T09 파일 전체|`file_role: system_config`|`file_role: system_manual`|`file_role: system_config` $\rightarrow$ `file_role: system_manual`|
|**5.**|T05 폴더|`05_MOCs`|`05_Collection`|폴더명 변경: `05_MOCs` $\rightarrow$ `05_Collection` **(선행 작업)**|
|**6.**|T01/T02 tags|`tags: [- 출처/인덱스/시리즈]` 등|`tags: [- 출처/{{series_type}}/{{series_name}}]`|태그 규칙 점검 및 통일 (필요시 수동 재분류)|
|**7.**|T01~T06 (`process`)|`process: initial_capture`|`process: raw`|`process: initial_capture` $\rightarrow$ `process: raw`|
|**8.**|T01~T06 (`priority`)|`priority: critical` 등 (무효값)|`priority: high` (유효값)|무효값(critical 등)을 유효값(high)으로 일괄 수정|
|**9.**|T01~T06 (`status`)|`status: finalized` 등 (무효값)|`status: completed` (유효값)|무효값(finalized 등)을 유효값(completed)으로 일괄 수정|
|**10.**|T01~T06 (필수 필드 추가)|(누락)|`action_required`, `difficulty`, `satisfaction`|누락된 필수 필드들을 파일 하단에 일괄 추가|

이 목록을 기반으로 **'오늘 아침 확정 표준'**에 맞춰 **T01 템플릿**부터 다시 검토하시겠습니까?



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
SORT file_role ASC, file.name ASC
```
