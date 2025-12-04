---
title: "T08_문장수집_시간순_인덱스"
level: T08 # ✅ T08 레벨 확정
file_role: system_index # 시스템 관리 인덱스 역할

parent: ""
references: []

tags:
 - 출처/인덱스_구조/시스템_문서
 - 영역/시스템/T05_추적
---
# 💬 T08. 문장 수집 시간순 인덱스


## 🧭 1. 개요 및 목적


이 인덱스는 T05 문장 수집 파일을 **최신 생성 순서**로 집계하여, 사용자의 학습 및 기록 흐름을 시간순으로 추적할 수 있도록 돕습니다.


## 📚 2. T05 문장 수집 기록 목록 (Dataview 집계)


*T05 문장 수집 파일을 파일명(시간) 기준으로 최신 순으로 정렬합니다.*

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  parent AS "T02 원본",
  file.ctime AS "생성 시간"
FROM ""
WHERE
  level = "T05" 
  AND file_role = "sentence_collection" 
  AND !contains(file.name, "tp") 
  AND !contains(file.name, "Template") 
SORT file.name DESC
```

