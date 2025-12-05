---
aliases: []
title: "{{value:T02_아티클/노트_제목_입력}}" # 프롬프트 간소화
published: "{{value:원본_발행_날짜}}"  # 프롬프트 간소화

level: T02
file_role: article_atom

parent: "{{value:상위_T01_파일명_입력}}"
word_type: "" # T03 전용 필드 (빈 값 유지)

status: planned # 최종 확정: Task 관리 기본값
priority: medium
process: raw # 최종 확정: T02의 초기 품질 단계

source_name: "{{value:출처_이름_입력}}" # ✅ 수정 완료 (간결화)
source_author: "{{value:출처_저자_입력}}" # ✅ 수정 완료 (간결화)
source_type: "{{value:출처_유형_입력}}" # ✅ 수정 완료 (예: book, article)

action_required: link_to_t04 # Quickadd 선택: [memorize, deep_dive, daily_use, none]
difficulty: good # Quickadd 선택: [again, hard, good, easy, none]
satisfaction: 3 # 1~5점 척도

references:
  - "{{value:주요_출처_URL_입력}}" # ✅ 수정 완료 (간결화)
tags:
  # 1. 출처 태그: Quickadd에서 source_top, source_sub 2개 값을 입력받아 자동 완성
  # T02는 '외부 정보'의 원천이므로 출처 태그가 필수입니다.
  - 출처/{{value:source_top}}/{{value:source_sub}}
  # 2. 영역 태그: T01과 마찬가지로 영역 분류 태그를 입력받아 자동 완성
  - 영역/{{value:area_top}}/{{value:area_sub}}
---
# 📖 T02. {{title}} (Source Note)



## 📎 T02 발췌 원본 (Raw Content)


## 📕 어휘



## 📘 핵심(Key) 
<!-- 
요약 대체 (본문 재독 부담 감소)
아티클 내용 중 가장 중요한 1~3가지 사실만 압축적으로 기록합니다. 
본문 전체를 읽지 않아도 내용을 상기할 수 있게 합니다.
가장 중요한 정보를 빠르게 재인(Recall)할 수 있습니다.
-->


## 📗 발상(發想) 
<!-- 
순간적 느낌/다음 주제 (직관적)
아티클을 통해 새롭게 떠오른 생각, 아이디어, 영감을 기록합니다. 
다음 탐구 주제로 이어지는 '단초(고리)'를 포착하는 데 사용합니다.
'다음 탐구(Next Action)'나 '할 일(Todo)'을 명확하게 한 줄로 추가하여, 
발상이 실제로 행동으로 이어지도록 유도합니다.
-->


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
