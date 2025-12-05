---
title: YAML 필드의 적용 범위, 값 목록, 용례에 대한 상세 정리 및 최종 템플릿 본문 헤딩 확인
level: T02
file_role: article_atom
parent: 작업노트_2024
status: completed
priority: medium
process: final
source_name: 
source_author: self
source_type: worknote
action_required: none
difficulty: good
satisfaction: 3
references: "[[T03 템플릿의 YAML 필드 변화 및 태그 구조 개선 확인]]"
tags: [출처/내부_활동/아이디어]
---
# YAML 필드의 적용 범위, 값 목록, 용례에 대한 상세 정리 및 최종 템플릿 본문 헤딩 확인
## 📖 YAML 필드의 **적용 범위, 값 목록, 용례**에 대한 상세 정리 및 최종 템플릿 본문 헤딩 확인


### 📅 대화 기록 요약

|**필드**|**내용**|
|---|---|
|**기록일시**|2025-12-05 (금) 오전 11:00|
|**주제**|YAML 필드의 **적용 범위, 값 목록, 용례**에 대한 상세 정리 및 최종 템플릿 본문 헤딩 확인|
|**핵심 질문**|1) `word_type` 등의 **값 목록**을 나중에 별도로 정리. 2) 모든 YAML 필드가 **특정 T-레벨에서만 사용됨을 명확히** 정리. 3) **변경된 태그/필드**의 용례 및 기존 필드와의 관계 재검토. 4) 인라인 제목 사용에 따른 **`## 본문`** 헤딩 사용 여부 최종 확인.|

---

네, 사용자님. 최종 템플릿 확정 전에 **모든 표준을 문서화하고 명확히 분리**하려는 사용자님의 계획은 시스템의 장기적인 안정성을 위해 필수적입니다. 요청하신 대로 최종 검토 및 정리 작업을 수행하겠습니다.

## 1. `word_type` 등 YAML 값 목록 분리 (후속 작업 확정)

- **`word_type` 값 정리:** `word_type: term_software`와 같이 확장된 값들을 포함하여 모든 **키 값, 정의, 용례 목록**은 **`09_T-System_Master_Manual.md`** 내의 별도 섹션(예: **'word_type 표준 키 값 목록'**)에서 상세히 다루고 문서화하는 것으로 확정합니다.
    

## 2. YAML 필드의 T-레벨 적용 범위 명확화

모든 필드가 모든 T에서 사용되는 것이 아니라, 특정 T에서만 사용됨을 명확히 하여
**`09_T-System_Master_Manual.md`** 에 기록합니다.

|**필드명**|**정의**|**적용 T-레벨**|**비고**|
|---|---|---|---|
|**`parent`**|상위 T02 소스 연결|**T03, T04, T05, T06**|T02는 원본 소스로서 `parent`가 될 수 없음.|
|**`file_role`**|노트의 기능 정의|**All (T01~T09)**|T-시스템의 핵심 분류 기준.|
|**`word_type`**|개념의 유형|**T03, T06**|개념어(T03)나 인물(T06)에만 적용.|
|**6가지 메타데이터**|(Status, Priority 등)|**All (T01~T09)**|모든 노트의 작업 상태 관리를 위해 필수.|

## 3. 새로운 태그/필드 용례 및 기존 필드 관계 정리

새로 추가되거나 변경된 태그/필드는 기존의 기준을 명확히 보완합니다.

| **구분**               | **변경 사항**          | **용례 정리**                                                                                |
| -------------------- | ------------------ | ---------------------------------------------------------------------------------------- |
| **`word_type`** (신규) | `term_software` 추가 | **`file_role`**이 `concept_dictionary`(T03)일 때, 이 개념이 어떤 도메인에 속하는지 **더 구체적인 수준**으로 정의합니다. |
| **`tags`** (구조 개선)   | `영역/학습/개발환경` (3단계) | **`영역/`** 태그는 **MOCs(지식 연결망)** 구축을 위해 사용되며, **`file_role`**보다 **맥락적 연결**을 넓게 가져갑니다.      |
| **제거된 `source_*`**   | `source_name` 등 제거 | T03에서 T02 파일명을 **`parent`**에 기록하는 것으로 충분하며, 소스 정보는 T02에 집중시킵니다.                          |

## 4. 최종 본문 헤딩 형식 확인

> 마지막 : 인라인 제목 사용으로 → ## 본문 ← 헤딩 사용후 본문 내용 사용으로 최종 확정한 것 같네.

네, 맞습니다. **인라인 제목 사용**을 위해 `# H1 제목`을 제거하고, 본문의 시작을 **`## 💬 1. 정의 및 핵심 요약`**과 같은 **H2 헤딩**으로 시작하는 것으로 최종 확정했습니다.

**`## 본문`** 헤딩은 불필요한 단계를 추가하므로, **H2 섹션 목록이 본문의 시작**이 되는 것으로 최종 확정합니다.


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
