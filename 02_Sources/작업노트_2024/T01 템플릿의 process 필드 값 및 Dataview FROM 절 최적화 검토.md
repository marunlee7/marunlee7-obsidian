---
title: T01 템플릿의 process 필드 값 및 Dataview FROM 절 최적화 검토
level: T02
file_role: article_atom
parent: 작업노트_2024
status: completed
priority: medium
process:
source_name:
source_author: self
source_type: worknote
action_required: none
difficulty: good
satisfaction: 3
references: ""
tags:
  - 출처/내부_활동/아이디어
---
#### 📅 대화 기록 요약

|**필드**|**내용**|
|---|---|
|**기록일시**|2025-12-05 (금) 오전 11:52|
|**주제**|T01 템플릿의 `process` 필드 값 및 Dataview `FROM` 절 최적화 검토|
|**핵심 질문**|1) `process` 필드에 `initial_capture`가 추가되었는지 여부와 2) T01 Dataview 쿼리의 `FROM ""`를 **T02 폴더 경로**로 지정하여 효율성을 높일 수 있는지 확인.|

---

사용자님, 두 가지 질문 모두 시스템의 효율성과 정확성을 높이는 데 중요한 검토 사항입니다. 하나씩 확인하겠습니다.

### 1. `process` 필드 값 검토: `initial_capture`

- **결론:** `initial_capture`는 이전에 논의된 `process`의 3가지 핵심 단계(`initial_capture`, `analyzing`, `final`) 중 하나입니다. 이는 **추가된 것이 아니라, 6가지 메타데이터 표준의 확정된 값**입니다.
    
- **용례:** T01 템플릿의 `process: initial_capture`는 이 노트가 **최초 생성되어 정보 수집 단계에 있음**을 명확히 표시하는 초기값 설정입니다. 이는 **`status: planned`**와 함께 노트의 상태를 가장 먼저 정의하는 중요한 값입니다.
    

### 2. Dataview `FROM` 절 최적화 (폴더 경로 지정)

- **결론:** **T02 폴더 경로로 지정하는 것이 Dataview 쿼리의 성능과 명확성을 높이는 데 훨씬 좋습니다.**
    

|**구분**|**현행 (FROM "")**|**개선안 (FROM "02_Sources")**|**장점**|
|---|---|---|---|
|**검색 범위**|볼트 내 **모든 파일** 검색|**`02_Sources` 폴더**만 검색|검색 범위가 좁아져 **쿼리 속도가 향상**되고, 불필요한 파일 검토를 막아 **정확성이 높아집니다**.|
|**WHERE 절**|`level = "T02"` 필터링 필수|`level = "T02"` 필터링이 불필요할 수 있음|T02 노트만 모여있는 폴더를 대상으로 하므로, `level` 필터를 생략하여 쿼리가 간결해집니다.|

#### 🛠️ T01 Dataview 쿼리 수정 (FROM 경로 지정)

T01 템플릿의 Dataview 쿼리를 최적화된 경로로 수정합니다. (`02_Sources` 폴더 사용 가정)

코드 스니펫

```
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  status AS "진행 상태",
  priority AS "중요도",
  process AS "Process"
FROM "02_Sources" /* 폴더 경로 지정으로 최적화 */
WHERE
  contains(parent, this.file.name)
SORT file.mtime DESC
```

이 구조로 **T01 템플릿을 최종 확정**합니다. 이제 T-시스템의 **T02 원본 소스 템플릿** 검토로 넘어갈까요?


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
