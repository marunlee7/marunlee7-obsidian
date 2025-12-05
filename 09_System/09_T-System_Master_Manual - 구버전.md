---
title: 09_T-System_Master_Manual
level: T09
file_role: system_config

parent: ""

status: finalized
[priority: high

source_name: Gemini & User Final Standardization (2025-11-24 최종 완료)
source_author: system
tags:
  - 출처/인덱스_구조/시스템_문서
  - 시스템/YAML
  - 시스템/규칙
---
# 👑 T-시스템 마스터 매뉴얼 (최종 불변의 표준)

본 문서는 T-시스템의 논리적 구조, 폴더 구성, 모든 YAML 필드 표준 값 및 논리적 규칙을 통합 정의하며, 모든 자동화 스크립트(Dataview, Quicadd)의 유일한 진실의 원천(SSoT)입니다.

## I. 시스템 구성 및 불변의 논리 (T-Level & File Role)

T-시스템은 지식의 획득(T02) → 원자화(T03/T04) → 구조화(T01/T05)를 계층적으로 관리하며, `level` 필드 값은 자동화 안정성을 위해 반드시 단순 숫자(`T01`~`T09`)를 사용합니다.

| 폴더 번호 |      폴더명      | `level` (불변 값) |  최종 확정 `file_role`   | 핵심 역할 및 논리                              |
| :---: | :-----------: | :------------: | :------------------: | :-------------------------------------- |
|  01   |  `01_Index`   |     `T01`      | `series_collection`  | 프로젝트/시리즈의 마스터 허브 및 T02 노트 인덱스.          |
|  02   | `02_Sources`  |     `T02`      |    `article_atom`    | 외부 출처의 내용을 요약하고 원자화한 콘텐츠 (T03/T04의 원천). |
|  03   | `03_Concepts` |     `T03`      | `concept_dictionary` | 순수 개념, 어휘, 정의의 상세 마스터 레코드.              |
|  04   | `04_Analysis` |     `T04`      | `personal_analysis`  | 개인의 분석, 성찰, 실행 기록.                      |
|  05   |   `05_MOCs`   |     `T05`      |    `concept_moc`     | T03 노트를 자동 집계하고 지식을 구조화하는 목차.           |
|  09   |  `09_System`  |     `T09`      |   `system_config`    | 시스템 설정, 템플릿, 가이드 등 시스템 관리 파일.           |

---

## II. 🔑 최종 YAML 필드 표준 종합 (Dataview 기준)

### 1. 필드 값 최종 규칙 (모든 필드 포함)

|     YAML 키      |     T01 Master      |   T02 Source   |     T03 Concept      |    T04 Analysis     |    T05 MOC    | 규칙 (불변)                                         |
| :-------------: | :-----------------: | :------------: | :------------------: | :-----------------: | :-----------: | :---------------------------------------------- |
|     `level`     |        `T01`        |     `T02`      |        `T03`         |        `T04`        |     `T05`     | 단순 숫자만 사용.                                      |
|   `file_role`   | `series_collection` | `article_atom` | `concept_dictionary` | `personal_analysis` | `concept_moc` | Dataview의 집계 기준.                                |
|    `parent`     |        `""`         |     T01 제목     |        T02 제목        |     T02/T03 제목      |     `""`      | 상위 노트의 정확한 파일명만 수동 입력.                          |
|    `status`     |      `active`       |    `active`    |         `""`         |      `active`       |     `""`      | 노트의 작업 완료 상태 기록. (T03은 불변이므로 사용 안 함)            |
|   `word_type`   |        `""`         |      `""`      |        필수 입력         |        `""`         |     `""`      | T03 노트의 상세 개념 유형. (아래 III. 참조)                  |
|  `source_name`  |        필수 입력        |     필수 입력      |        `self`        |        `""`         |     `""`      | 출처의 정식 명칭. (T03은 '개념 자체'가 출처이므로 `self`).        |
| `source_author` |       `self`        |     필수 입력      |        `self`        |        `""`         |     `""`      | 출처의 저자. (T01/T03은 `self`).                      |
|  `source_type`  |        필수 입력        |     필수 입력      |      `concept`       |        `""`         |     `""`      | 출처의 유형(book, article 등). (T03은 `concept`으로 고정). |
|  `references`   |     `[]` (List)     |  `[]` (List)   |         `""`         |        `""`         |     `""`      | 원문 URL, 페이지 번호 등 출처 정보를 리스트로 기록.                |

### 2. T02 노트의 표준 Dataview 쿼리 (불변)

모든 T02 노트에 삽입될 하위 노트 연결 쿼리입니다.

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  file_role AS "유형",
  priority AS "중요도"
FROM ""
WHERE 
  contains(parent, this.file.name) 
  AND (file_role = "concept_dictionary" OR file_role = "personal_analysis") 
  AND file_role != "template"
SORT file_role ASC, file.name ASC
```


## III. 💡 `word_type` 상세 정의 및 값 (T03 전용)

`word_type`은 T03 노트가 다루는 개념 항목의 유형을 상세 분류하여 Dataview 쿼리 기준을 제공합니다.

### 1. `word_type` 최종 확정 값 목록

| word_type 값 (소문자) | 분류 유형    | 3단 태그 대응 예시       | 설명                                   |
| ----------------- | -------- | ----------------- | ------------------------------------ |
| `term`            | 용어/어휘    | `#출처/개념_본질/어휘_용어` | 일반적인 단일 개념, 용어, 지식을 분류.              |
| `person`          | 인물/인명    | `#출처/개념_본질/인물_인명` | 역사적 인물, 저자, 영향력 있는 사람 등을 분류.         |
| `model`           | 원칙/모델/법칙 | `#출처/개념_본질/원칙_모델` | SWOT, 80/20 법칙 등 구조화된 분석 원리나 모델을 분류. |
| `theory`          | 이론/프레임워크 | `#출처/개념_본질/이론_법칙` | 경제학 이론, 심리학 프레임워크 등 광범위한 지식 체계를 분류.  |
| `event`           | 사건/이슈    | `#출처/개념_본질/사건_이슈` | 특정 시점에 발생한 역사적 사건이나 중요한 이슈를 분류.      |

---

## IV. 🏷️ 3단 태그 시스템: 최종 상세 매뉴얼 (논리 통합)

### 1. T-레벨별 2단계/3단계 태그 최종 표준

| T-레벨    | 2단계 (정보의 발생 지점) | 3단계 (구체적 형식 및 유형) [예시 값] | 핵심 file_role                        | 최종 태그 예시            |
| ------- | --------------- | ------------------------ | ----------------------------------- | ------------------- |
| T01/T02 | `외부_정보`         | `도서_단행본`, `문헌_논문_보고서` 등  | `series_collection`, `article_atom` | `#출처/외부_정보/도서_단행본`  |
| T03     | `개념_본질`         | `어휘_용어`, `인물_인명` 등       | `concept_dictionary`                | `#출처/개념_본질/어휘_용어`   |
| T04     | `내부_활동`         | `개인_통찰`, `회의록_미팅` 등      | `personal_analysis`                 | `#출처/내부_활동/개인_통찰`   |
| T05/T09 | `인덱스_구조`        | `주제_MOC`, `시스템_문서` 등     | `concept_moc`, `system_config`      | `#출처/인덱스_구조/시스템_문서` |

### 2. T03/T04 태그 사용 불변 규칙 (논리적 근거)

| T-레벨 | 핵심 file_role         | 규칙 및 논리적 근거                                                                                                                                    |
| ---- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| T03  | `concept_dictionary` | T03 노트는 절대 `#출처/외부_정보` 태그를 사용해서는 안 됩니다. T03의 목적은 '개념의 불변성'을 유지하는 것입니다. 어떤 T02 출처(책, 기사)에서 왔든, 개념 자체는 `#출처/개념_본질` 태그를 사용하여 출처와 독립적으로 분류되어야 합니다. |
| T04  | `personal_analysis`  | T04 노트는 항상 `#출처/내부_활동` 태그를 사용해야 합니다. T04의 역할은 '분석, 성찰, 실행'이며, 이는 모두 사용자 내부에서 생성된 활동이므로, `parent`가 외부 출처(T02)일지라도 태그는 내부 활동으로 고정됩니다.            |
#사색 :: 제일 중요한 원칙같음 → 이해하고 받아들이도록

---

## V. 📚 시스템 및 템플릿 파일 목록 (통합 인덱스)

### 📕 추가 가이드 및 설정 파일 목록


```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "파일명",
  process AS "process",
 priority AS "priority",
  file.mtime as "수정일"
FROM "09_System/가이드라인" OR "09_System"
WHERE (file_role = "system_config" OR file_role = "tool_index")
AND file.name != this.file.name
SORT file.name ASC
```

### 📕 템플릿 파일 목록


```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "템플릿 파일",
  choice(contains(file.name, "tp1"), "T01 Index",
    choice(contains(file.name, "tp2"), "T02 Source",
      choice(contains(file.name, "tp3"), "T03 Concept",
        choice(contains(file.name, "tp4"), "T04 Analysis",
          choice(contains(file.name, "tp5"), "T05 MOC", "기타"))))) AS "T-레벨"
FROM "09_System/tp"
SORT file.name ASC
```

