---
title: tp3_hword_concept
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
<%*
const now = tp.date.now("YYYY-MM-DD");
const fileTitle = tp.file.title.trim(); 

// 🚨 접두사 제거 완료: 부모 지정 suggester 예시에서 'T02-' 접두사 제거
const parentNote = await tp.system.suggester(["煩多(번다)", "罔測(망측)"], ["煩多(번다)"], false, "1. 부모 T02 칼럼 지정 (접두사 없음)"); 
const tagsC = await tp.system.suggester(["개념/관계_상호작용/대립", "개념/자기조절/성찰", "개념/인식_사고/체계"], ["개념/관계_상호작용/대립"], false, "2. 핵심 [C. 개념] 태그 선택"); 
const sourceTitle = await tp.system.prompt("3. T03 원천 제목 입력 (예: 하루한자 [1920])");
const sourceUrl = await tp.system.prompt("4. 원천 URL 입력");
const sourceAuthor = await tp.system.suggester(["전광진", "김병기", "박원길"], ["전광진"], false, "5. 원천 저자 지정");
_%>---
title: "<% fileTitle %>"
aliases: []
level: "T03_Dictionary"
file_role: dictionary_atom 
parent: "<% parentNote %>"

source_title: "<% sourceTitle %>"
source_author: "<% sourceAuthor %>"
source_url: "<% sourceUrl %>"

tags:
  - 출처/문헌/칼럼
  - 영역/인문학/언어학
  - 영역/인문학/철학
  - <% tagsC %>
word_type: 한자어

created: <% now %>
modified: <% now %>
---

# <% fileTitle %> (T03 원자 노트)

## 1. 개요 및 정의 (Definition)

* **한자/어휘:** * **정의:** * **어원/구성:** ## 2. 핵심 분석 및 맥락 (Analysis)

* [칼럼의 주요 명제 및 논리 전개]

## 3. 연관 개념 및 활용 (Related)

* [[연관 어휘 또는 개념 링크]]

## 4. 개인적 성찰 (Reflection)

* [칼럼을 읽고 도출한 나의 생각 및 깨달음]