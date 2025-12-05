---
title: T08_인물_DB_MOC
level: T08
file_role: concept_moc
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
tags: []
---
# 👤 T08. 인물 데이터베이스 마스터 목록


**이 문서는 YAML level: T06을 가지는 모든 인물 프로필 노트를 자동으로 수집합니다.**


## 🔍 Dataview 쿼리: 인물 프로필 목록

```dataview
TABLE 
  tags AS "분류 태그",
  domain AS "관리 영역",
  source AS "최초 출처"
FROM ""
WHERE level = "T06" AND !contains(file.name, "T0") 
SORT file.name ASC
```

