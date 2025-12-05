---
title: Quicadd 자동화 시스템 재점검 요청과 T03, T05 관련 상세 논의
level: T09
file_role: system_config
parent: "[[09_System/가이드라인/09_T-System_Master_Manual]]"
source_name: Gemini & User Final Standardization (2025-11-26 최종 확정)
source_author: system / user
tags:
  - 개념/옵시디언/YAML
  - 영역/시스템/지식관리_규칙
  - 출처/인덱스_구조/시스템_문서
---
## 1. 💡 T03 파일 생성 방법론 (최우선 과제)

T03(개념 사전) 파일 생성 방법은 T-시스템의 핵심 자동화 부분이며, `word_type` 분류가 중요합니다.

| **방법론**                  | **흐름 및 Gemini 역할**                                                               | **장점**                                  | **단점**                                  |
| ------------------------ | -------------------------------------------------------------------------------- | --------------------------------------- | --------------------------------------- |
| **A. YAML/검색값 제시**       | Gemini가 개념 정의와 `word_type`을 제시 → 사용자가 Quicadd 실행 → YAML 필드 채우기 (반자동)             | 구현이 간단하고 빠름.                            | **수동 작업 시간이 길어짐.** 개념 정의를 복사/붙여넣기 해야 함. |
| **B. API 이용 자동 생성 (추천)** | 사용자가 개념/T02 원천만 제시 → **Gemini API가 YAML 필드와 본문 내용을 생성** → Quicadd가 파일 생성 (완전 자동) | **가장 높은 생산성**과 일관성 확보. T03 작업 시간 대폭 단축. | Gemini API 연동 로직 구현 복잡도 증가.             |

**✅ 제안:** **B 방법 (완전 자동 생성)을 목표로 로직을 설계해야 합니다.** T03의 목적이 개념의 불변적인 정의를 확립하는 것이므로, 초기 정의 작업을 AI가 처리하는 것이 효율적입니다.

### T03 자동 생성 로직 설계 (Quicadd/API 통합)

|**단계**|**사용자 입력**|**Gemini API 역할**|**Quicadd 역할 (파일 생성)**|
|---|---|---|---|
|**1. 명령 실행**|Quicadd 실행 (`T03 생성`)|-|-|
|**2. 필수 입력**|**1) 개념/단어 (필수)**<br><br>  <br><br>**2) T02 원천 파일명 (필수)**|-|-|
|**3. 데이터 생성**|(Gemini API 호출)|**A. 정의 생성:** 핵심 정의 및 상세 설명 생성.<br><br>  <br><br>**B. 유형 유추:** 개념 내용 기반으로 `word_type` (e.g., `term`, `person`) 유추 및 해당 태그 (e.g., `#출처/개념_본질/어휘_용어`) 결정.|-|
|**4. 파일 생성**|-|-|T03 템플릿에 **유추된 YAML 값**과 **생성된 본문 내용**을 삽입하여 파일 저장.|

이 로직에 동의하시나요? T03 자동화 진행을 위해 이 로직을 우선 확정해야 합니다.

---

## 2. 🗺️ T05 MOCs 11개 파일 검토

제시해주신 11개의 MOC 파일 목록은 **Content Index**와 **System/Task Management Index**를 모두 포괄하고 있습니다.

|**분류**|**파일 목록**|**목적**|
|---|---|---|
|**콘텐츠 MOC**|`T05_인물사전_MOC.md`, `T05_한자어휘사전_MOC.md`, `T05_Concept_MOC_List.md`|T03의 특정 `word_type`이나 전체 T03 노트를 집계.|
|**관리/시스템 MOC**|`T05_Completed_Status_Index.md`, `T05_High_Priority_Index.md`, `T05_Draft_Process_Index.md`, `T05_InProgress_Status_Index.md`, `T05_Planned_Status_Index.md`, `T05_Waiting_Status_Index.md`|SPP 필드 값을 기준으로 T01/T02/T04 노트를 분류하여 Task Dashboard 역할 수행.|
|**계층/허브**|`T05_All_T01_Series_Index.md`, `T05_Vault_Dashboard.md`|시스템 전체의 계층 구조 및 대시보드 역할.|

**✅ 검토 의견:** 목록은 T-시스템의 관리 필드(`status`, `process`, `priority`)를 완벽하게 커버하며, 콘텐츠도 인덱싱하고 있습니다.

**질문:** 이 11개 MOC 파일의 Dataview 쿼리를 새로 확정된 YAML 필드 값(예: `status: in-progress` 대신 `status: in-progress`)에 맞춰 **표준화**하는 작업이 필요할까요?

---

## 3. (미완성 항목)

세 번째 항목이 비어 있습니다. 별도의 추가 논의 사항이 있으시다면 말씀해주십시오.

T03 자동 생성 로직을 확정해주시면, 다음으로 **T05 MOC 쿼리 표준화** 작업을 진행하겠습니다.