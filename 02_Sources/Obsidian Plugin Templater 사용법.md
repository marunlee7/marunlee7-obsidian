---
title: Obsidian Plugin Templater 사용법
published: 2025-11-27
level: T02
file_role: article_atom
parent: Templater 기초부터 중급까지
word_type: ""
status: planned
priority: medium
process: raw
source_name: Templater 기초부터 중급까지
source_author: ChatGPT
source_type: " article"
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references:
  - ""
tags: [출처/외부_정보/아티클_웹]
---
# 📖 T02. Obsidian Plugin Templater 사용법


## 📌 주요 내용 요약 (Summary)

Templater 변수 사용
<% tp.user.prompt("질문") %> → 사용자 입력 받기
<% tp.file.title %> → 현재 파일 이름
<% tp.date.now("YYYY-MM-DD HH:mm") %> → 현재 시간



[[템플레이터 테스ㅡ]]

## 🗂️ 연결된 하위 노트 목록 (T03/T04)
```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  file_role AS "유형",
  priority AS "중요도"
FROM ""
WHERE 
 contains(parent, this.file.name)    AND (file_role = "concept_dictionary" OR file_role = "personal_analysis")    AND file_role != "template"
SORT file_role ASC, file.name ASC
```
