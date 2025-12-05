---
title: process 처리
published: 2025-12-03
level: T02
file_role: article_atom
parent: 한자어휘 템플릿
status: completed
priority: medium
process: draft
source_name: process 처리
source_author: self
source_type: worknote

action_required: link_to_t04
difficulty: good 
satisfaction: 5 

references:
  - ""
tags:
  - 출처/외부_수집/템플릿
  - 출처/내부_활동/아이디어
  - 개념/옵시디언/템플릿
  - 영역/옵시디언
---
# 📖 T02. process 처리 


## 조정할 것

status: planned # 최종 확정: Task 관리 기본값
priority: medium
process: raw # 최종 확정: T02의 초기 품질 단계


action_required: none # Quickadd 선택: [memorize, deep_dive, daily_use, none]
difficulty: good # Quickadd 선택: [again, hard, good, easy, none]
satisfaction: 3 # 1~5점 척도



제시해 주신 원본 테이블의 값(`raw`, `draft`, `final`)과 현재 혼용되어 사용되고 있는 값(`review`, `synthesis`)을 **작업 단계(Process)** 관점에서 비교하여 정리해 보겠습니다.

---

## 📝 `process` 값 비교 및 정의

제미나이가 볼 때, `review`와 `synthesis`는 **원래의 세 가지 작업 단계(`raw`, `draft`, `final`)와는 다른 종류의 작업 목표**를 나타냅니다.

- **`raw`, `draft`, `final`:** **노트의 품질 상태**와 **완성도**를 나타내는 단계적인 지표입니다. (A → B → C)
- **`review`, `synthesis`:** **노트에 적용된 특정 행위(Action)** 또는 **목표**를 나타냅니다. (노트를 완성하기 위한 '작업 유형')
    

| 확정 값 (표준)   | 혼용 값                   | 작업 단계 관점 정의 (Process)                                      | 원래 표준과의 비교 |
| ----------- | ---------------------- | ---------------------------------------------------------- | ---------- |
| **`raw`**   | 해당 없음                  | 원본 데이터의 **최초 수집 상태** (가공 전)                                | **기초**     |
| **`draft`** | **`review`**에 해당 가능    | **가공 및 검토가 필요한 초안 상태**. '검토 중'이라는 행위는 '초안' 단계에 포함될 수 있습니다. | **중간**     |
| **`final`** | **`synthesis`**에 해당 가능 | **내용 작성이 완료되어 확정된 상태**. '종합 및 완성'이라는 행위는 '최종' 단계로 귀결됩니다.   | **완성**     |


### 💡 `process` 일관성을 위한 권장 사항

시스템의 혼란을 막기 위해, **표준화된 3단계 모델(`raw`, `draft`, `final`)**을 유지하시는 것을 권장하며, 혼용된 값은 다음과 같이 매칭하는 것이 논리적입니다.

- **`review`** 가 발견되면 → **`draft`** 로 간주하고 **검토가 필요하다** 는 의미로 사용합니다.
- **`synthesis`** 가 발견되면 → **`final`** 로 간주하고 **종합 작업이 완료되었다**는 의미로 사용합니다.
    

|원래 표준 값|적용될 혼용 값|의미 (작업 단계)|
|---|---|---|
|**`raw`**|(사용하지 않음)|최초 수집 상태|
|**`draft`**|`review`|초안 검토 필요 상태|
|**`final`**|`synthesis`|최종 완성 상태|




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
