---
title: "VS Code 학습 완전 MOC"
level: T08
file_role: MOC
parent: ""
tags:
  - 앱/VSCode
---
# 📚 VS Code 학습 완전 MOC



## 🔍 Dataview 쿼리: T02~T06 전체 연결

```dataview
TABLE WITHOUT ID
link(file.path, file.name) AS "노트 제목",
file_role AS "유형",
status AS "진행 상태",
priority AS "중요도",
process AS "Process",
tags AS "태그"
FROM ""
WHERE contains(tags, "앱/VSCode")
SORT priority DESC, status ASC, file_role ASC, file.name ASC
```

