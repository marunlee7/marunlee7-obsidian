---
title: 00_HOME
---
# ✨ Welcome to The T-System Vault!

> [!abstract] 🔑 Vault Quick Access (Vault 주요 접근 경로)
> T-시스템을 효율적으로 관리하고 싶다면, 아래 대시보드를 클릭하세요.

## 🚀 시작하기

* **📈 대시보드 바로가기:** [[T06_Vault_Dashboard]]
    * *전체 파일 통계, 4단계 Status 현황, 시스템 운영 상태 확인.*
* **📚 Vault 구조 안내:** [[README]]
    * *T-시스템 레벨(T01~T05)의 역할과 폴더 구조 설명.*
* **⚙️ Quickadd 자동화 점검일:** 2025-11-20 (점검 필요)
    * *Quickadd 시스템 점검을 잊지 마세요.*

\---

## 📌 현재 Vault 상태 요약 (Dataview)

> [!INFO] **최근 7일간 수정된 노트 목록**
> 가장 활발하게 작업된 노트를 확인합니다.


```dataview
TABLE WITHOUT ID
  file.link AS "노트 제목",
  level AS "T-레벨",
  file.mtime AS "수정일"
FROM ""
WHERE (date(now) - file.mtime) <= dur(7 days) AND file.name != this.file.name
SORT file.mtime DESC
LIMIT 5
```

