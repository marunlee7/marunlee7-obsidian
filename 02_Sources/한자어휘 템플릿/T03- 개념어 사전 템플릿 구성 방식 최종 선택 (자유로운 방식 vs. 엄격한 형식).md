---
title: T03- 개념어 사전 템플릿 구성 방식 최종 선택 (자유로운 방식 vs. 엄격한 형식)
published: 2025-12-03
level: T02
file_role: article_atom
parent: 한자어휘 템플릿
status: planned
priority: medium
process: raw
source_name: 명확한 목표(개념 정의)와 형식(YAML + Markdown)
source_author: self
source_type: worknote
action_required: link_to_t04
difficulty:	good
satisfaction: 3

references:
  - T03- 개념어 사전 템플릿 구성 방식 최종 선택 (자유로운 방식 vs. 엄격한 형식)
tags: [출처/외부_수집/템플릿, 출처/내부_활동/아이디어, 영역/옵시디언, 개념/옵시디언/템플릿]
---
# 📖 T02. 명확한 목표(개념 정의)와 형식(YAML + Markdown)


## 📅 대화 기록 요약

| **필드**    | **내용**                                                                                        |
| --------- | --------------------------------------------------------------------------------------------- |
| **기록일시**  | 2025-12-03 (수) 오전 7:50                                                                        |
| **주제**    | T03 개념어 사전 템플릿 구성 방식 최종 선택 (자유로운 방식 vs. 엄격한 형식)                                               |
| **핵심 질문** | T03 템플릿 구성에서 **"자유로운 방식(1안)"**과 **"통일된 형식 기반(2안)"** 중 어떤 것이 **최종 품질과 통찰력** 측면에서 더 나은지 재검토 요청. |

---

사용자님께서 **T03 개념어 사전**에 대해 **'품질'**과 **'통일성'** 사이의 트레이드오프(Trade-off)를 깊이 고민하시는 것은 매우 핵심적인 문제입니다. T03은 지식의 재가공이 시작되는 곳이므로, 여기에 **'통찰력'**을 불어넣는 것이 중요합니다.

# 💡 1안 Vs 2안 품질 차이 분석

|**방식**|**특징**|**관찰된 품질**|**원인 분석**|
|---|---|---|---|
|**1안 (자유로운 방식)**|**구속력이 낮음.** (YAML은 간소화하고, 본문은 자유롭게 작성)|**품질이 더 높음.** (풍부한 맥락, 깊은 통찰)|사용자가 **'개념'** 자체에 집중하여, **관련 발상, 비유, 배경 지식** 등을 형식에 얽매이지 않고 자유롭게 기록했기 때문입니다.|
|**2안 (논의된 형식)**|**구속력이 높음.** (엄격한 YAML 및 Markdown 구조)|**통일성은 높으나 맥락이 부족함.** (핵심 Key만 존재)|**"무엇을 채워야 한다"**는 구조적 의무감이 **"무엇을 생각해야 한다"**는 통찰력을 방해했을 가능성이 높습니다.|

# 🚀 T03 개념어 사전의 최적 결론: **1안 + 최소한의 YAML 통일**

T03 개념어 사전은 단순한 데이터 기록이 아니라 **지식의 밀도를 높이는 단계**입니다. 따라서 **품질과 통찰력**을 최우선으로 해야 합니다.

**사용자님의 관찰대로 1안의 품질이 더 높다면, 1안을 메인으로 사용하시고, T-시스템 관리에 필요한 최소한의 YAML만 유지하는 것이 최적의 해답입니다.**

# ✅ T03 템플릿 최종 제안 (통찰력 우선)

본문 내용은 자유롭게, 시스템 관리에 필요한 YAML만 채우도록 합니다.

**1. YAML 필드는 T-시스템 통합을 위해 유지:** (T02 연결, 유형 지정)

YAML

```
---
title: "{{value:개념어_입력}}"
level: T03
file_role: concept_dictionary 
parent: "{{value:T02_Filename_Input}}" 

priority: medium
process: final # T03은 개념을 정의하는 단계이므로 항상 final
action_required: link_to_t04
difficulty: good
satisfaction: 3
---
```

**2. 본문 Markdown 구조는 통찰력에 집중:**

T03은 **개념의 정의(Def.)**와 **사용자 관점의 통찰(Insight)** 두 가지에만 집중합니다.

Markdown

```
# ✨ {{title}}

## 💬 1. 핵심 정의 및 배경 (Definition & Context)
(여기에는 개념의 간결하고 정확한 정의와 배경을 기록합니다.)

---

## 🚀 2. 나의 통찰 및 활용 (Insight & Application)
(여기가 가장 중요합니다. 이 개념을 통해 얻은 아이디어, 비유, 다른 지식과의 연결점을 자유롭게 기록합니다.)

```

이 방식으로 진행하시면, **T-시스템의 통일성(YAML)**을 유지하면서도 **통찰력(본문)**을 극대화하여 가장 높은 품질의 T03 노트를 만들 수 있습니다.


# 🗂️ 연결된 하위 노트 목록 (T03/T04/T05/T06)

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
