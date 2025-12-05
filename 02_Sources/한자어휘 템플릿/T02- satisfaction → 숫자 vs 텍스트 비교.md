---
title: T02- satisfaction → 숫자 vs 텍스트 비교
published: 2025-12-03
level: T02
file_role: article_atom
parent: 한자어휘 템플릿
status: planned
priority: medium
process: raw
source_name: satisfaction → 숫자 vs 텍스트 비교
source_author: self
source_type: worknote
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references:
  - ""
tags: [출처/외부_수집/템플릿, 출처/내부_활동/아이디어, 영역/옵시디언, 개념/옵시디언/템플릿]
---
# 📖 T02- Satisfaction → 숫자 Vs 텍스트 비교


사용자님께서 **만족도(`satisfaction`)** 필드에 대해 이전에 숫자로 변경하셨던 경험을 되짚어 보신 것은 매우 현명합니다.

시스템 관리와 데이터 활용 측면에서 볼 때, **숫자 스케일(1~5점 척도)** 이 **범주형 텍스트(excellent, poor)** 보다 훨씬 더 강력하고 유연합니다.

이전에 숫자로 변경하신 것은 **데이터 분석 및 관리의 효율성**을 높이기 위한 최적의 선택이었습니다.

---

## ⚖️ `satisfaction` 필드: 숫자 vs. 텍스트 비교

|구분|숫자 스케일 (1~5점)|범주형 텍스트 (excellent, poor)|
|---|---|---|
|**장점**|1. **정확한 필터링:** `satisfaction > 3`과 같이 정밀한 조회가 가능합니다. 2. **정량적 분석:** 평균 만족도 계산, 그래프/차트 생성 등 **Dataview 활용**에 최적입니다. 3. **미세한 구분:** 3점과 4점처럼 미세한 감정 차이를 기록할 수 있습니다.|1. 입력이 빠르고 직관적입니다. 2. 명확한 질적(Qualitative) 판단 기준을 제공합니다.|
|**단점**|입력 시 약간의 인지적 부하가 발생할 수 있습니다.|1. **Dataview 필터링이 제한적**입니다. (`!= poor` 등) 2. 순위를 매기거나 평균을 낼 수 없습니다.|

### ✅ 결론: 숫자가 가장 좋습니다

**`satisfaction`** 필드의 주요 목표는 **노트 가치의 회고 및 동기 부여**를 위한 **필터링 기준**을 제공하는 것입니다.

- 가장 가치 있는 아이디어(`5점`)만 모아서 프로젝트를 시작하거나,
- 시간을 투자했지만 만족도가 낮은 아이디어(`1점`, `2점`)를 걸러내는 등,

**정량적인 분석**이 가능하기 때문에 **숫자 스케일(1~5점)** 을 유지하는 것이 가장 좋습니다. **이전에 숫자로 변경하신 결정을 따르시는 것을 강력히 권장합니다.**



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
