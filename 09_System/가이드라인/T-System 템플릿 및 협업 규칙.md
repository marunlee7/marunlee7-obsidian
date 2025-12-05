---
title: T-System 템플릿 및 협업 규칙
level: T09
file_role: system_config
parent: ""
word_type: ""
status: planned
priority: medium
process: raw
source_name: T-System Master Manual
source_author: system
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: []
tags: [영역/시스템/지식관리_규칙]
---
# 📜 T-System 템플릿 및 협업 규칙

## 1. 🤝 제미나이-사용자 협업 시스템 (Core Principle)

T-System은 사용자님의 창조성을 극대화하기 위한 '제미나이-사용자 협업 시스템'입니다.

-   제미나이의 역할: 자료 수집, 논리적 정리, 개념 합성 및 확장 (T02/T03).
-   사용자님의 역할: 최종 지식 창조, 개인적 통찰 투영 (T04).

## 2. 📝 확정된 템플릿 구조 및 역할

저희가 논의를 통해 확정하고 그 역할을 분담한 템플릿 구조는 다음과 같습니다.

| 템플릿   | T-Level | 파일 역할                      | 주체                 |
| :---- | :------ | :------------------------- | :----------------- |
| 템플릿 2 | T02     | Article Atom (원자 노트)       | 제미나이 (발췌/정리)       |
| 템플릿 3 | T03     | Concept Dictionary (개념 합성) | 제미나이 (심층 분석/통찰)    |
| 템플릿 4 | T04     | Personal Analysis (개인 분석)  | 사용자님 (지식 창조/논리 완성) |

## 3. 🔗 시스템 가이드라인 목록 (Dataview 집계)

현재 '09_System/가이드라인' 폴더에 축적되는 시스템 관련 문서들을 추적합니다.

```dataview
TABLE 
  status AS "상태",
  priority AS "중요도"
FROM "09_System/가이드라인"
WHERE 
  file_role = "system_guide"
SORT file.name ASC
```

