---
title: tp4_hword_moc
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
<%*
const now = tp.date.now("YYYY-MM-DD");
const mocTag = await tp.system.suggester(["개념/관계_상호작용", "개념/자기조절", "개념/인식_사고"], ["개념/관계_상호작용"], false, "MOC의 핵심 Level 2 태그 지정");
const mocTitle = await tp.system.prompt("T04 MOC 제목 입력 (예: 관계_상호작용 MOC)");
_%>
title: "<% mocTitle %>"
aliases: []
level: "T04_Concept_MOC"
moc_tag: "<% mocTag %>"

created: <% now %>
modified: <% now %>
---

# <% mocTitle %> (T04 통합 MOC)

## 📌 개요
이 MOC는 **[[<% mocTag %>]]** 태그를 가진 모든 T03 원자 노트(어휘/개념)들을 자동으로 목록화합니다.

## 📕 T03 개념 목록 (Dataview)

```dataview
TABLE 
  parent AS "부모 칼럼",
  source_author AS "저자",
  created AS "정리일"
FROM ""
WHERE 
  contains(tags, "<% mocTag %>")
  AND level = "T03_Dictionary"
SORT created DESC
```
