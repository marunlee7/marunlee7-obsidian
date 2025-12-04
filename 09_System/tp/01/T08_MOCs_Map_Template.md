---
title: "{{value:T06_MOC_Subject_Title}}"
level: T06
file_role: moc_map

parent: ""
references: [] # 불필요한 필드는 []로 비워둡니다.

tags:
  # T06의 불변 규칙: 해당 MOC의 주제를 정의하는 '#영역/' 태그가 필수입니다.
  - 영역/{{value:area_top}}/{{value:area_sub}}
---
# 🗺️ T06. {{title}} (Concepts Map of Content)


## 🧭 1. 지도 개요 및 흐름 (Map Overview)


MOCs의 핵심은 **특정 `#영역/` 태그를 가진 모든 T1-T5 파일을 통합적으로 집계**하는 것입니다.

## 🌳 2. 핵심 연결 (Hub Concepts)


## 📚 3. 통합 지식 목록 (Aggregated Knowledge)

*이 쿼리는 MOC 파일의 `#영역/` 태그를 가진 모든 T01~T05 파일을 집계합니다.*
```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  level AS "T-레벨",
  file_role AS "역할",
  priority AS "중요도",
  difficulty AS "난이도"
FROM ""
WHERE
  # 🚨 성능 최적화: T-System 노트만 대상으로 설정하여 로딩 부하를 줄임
  contains(["T01", "T02", "T03", "T04", "T05"], level)
  # T06 MOC의 주 태그(tags[0])를 포함하는 모든 노트를 집계합니다.
  AND contains(file.tags, this.file.tags[0]) 
  AND file.name != this.file.name
SORT level DESC, priority DESC
```


