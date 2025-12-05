---
title: source_type, word_type
level: T09
file_role: system_config
parent: "[[09_System/가이드라인/09_T-System_Master_Manual]]"
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
# source_type, word_type


`source_type`은 Dataview 쿼리와 시스템 분석의 핵심 분류 기준이 되므로,
임의의 값이 아닌 아래의 확정된 값 목록 내에서만 사용되어야 합니다.


## 👑 파일 역할 (file_role) & source_type 값

| T-레벨 | 파일 역할 (file_role)       | source_type 값          | 적용 방식 및 논리 (불변)                                 |
| ---- | ----------------------- | ---------------------- | ----------------------------------------------- |
| T01  | `series_collection`<br> | 외부 출처 목록 <br>(아래 표 참조) |                                                 |
| T02  | `article_atom`          |                        |                                                 |
| T03  | `concept_dictionary`    | `concept`              | 개념 자체의 마스터 레코드이므로, `concept`으로 고정됩니다.           |
| T04  | `personal_analysis`     | `personal_analysis`    | 개인의 성찰/분석/활동 기록이므로, `personal_analysis`로 고정됩니다. |
| T05  | `sentence_collection`   | `sentence_collection`  | 문장수집                                            |
| T06  | `concept_moc`           | `moc`                  | 지식의 목차(Map of Content) 구조를 나타내므로, `moc`로 고정됩니다. |
| T07  | `journal`               | `journal`              | 저널(일간노트)                                        |
| T08  |                         |                        |                                                 |
| T09  | `system_config`         | `system_config`        | 시스템 설정 및 매뉴얼 파일이므로, `system_config`로 고정됩니다.     |

### 📚 T01 & T02 (외부 출처)의 표준 값 목록

T01 및 T02 파일 생성 시 Quickadd 선택지로 제공되어야 할 `source_type`의 표준 값 목록입니다. 이 값들은 `#출처/외부_정보/` 태그의 3단계 분류와 논리적으로 연결됩니다.

| source_type (키 값) | 한국어 설명                    | 태그 3단계와의 연결 예시        |
| ----------------- | ------------------------- | --------------------- |
| `book`            | 도서, 단행본                   | `#출처/외부_정보/도서_단행본`    |
| `article`         | 웹 기사, 뉴스, 블로그 글           | `#출처/외부_정보/아티클_웹`     |
| `report`          | 산업 보고서, 백서, 논문            | `#출처/외부_정보/문헌_논문_보고서` |
| `video`           | 유튜브, 강의 영상, 다큐멘터리         | `#출처/외부_정보/영상_강의`     |
| `podcast`         | 팟캐스트, 오디오 콘텐츠             | `#출처/외부_정보/음성_팟캐스트`   |
| `lecture`         | 오프라인 강의, 세미나 기록           | `#출처/외부_정보/강연_세미나`    |
| `course`          | 온라인 강좌 (패키지)              | `#출처/외부_정보/온라인_강좌`    |
| `web_generic`     | 일반 웹페이지, 참고 자료 (분류 불분명 시) | `#출처/외부_정보/웹_참조`      |
| `discussion`      | 회의록, 이메일, 채팅 기록 등         | `#출처/외부_정보/회의_기록`     |

## 👑 word_type 표준 키 값 목록 (T03 전용)

`word_type`은 T03 노트가 다루는 개념 항목의 유형을 상세 분류하여 Dataview 쿼리 기준을 제공합니다.

### 1. `word_type` 최종 확정 값 목록

| word_type 값 (소문자) | 분류 유형    | 3단 태그 대응 예시       | 설명                                   |
| ----------------- | -------- | ----------------- | ------------------------------------ |
| `term`            | 용어/어휘    | `#출처/개념_본질/어휘_용어` | 일반적인 단일 개념, 용어, 지식을 분류.              |
| `person`          | 인물/인명    | `#출처/개념_본질/인물_인명` | 역사적 인물, 저자, 영향력 있는 사람 등을 분류.         |
| `model`           | 원칙/모델/법칙 | `#출처/개념_본질/원칙_모델` | SWOT, 80/20 법칙 등 구조화된 분석 원리나 모델을 분류. |
| `theory`          | 이론/프레임워크 | `#출처/개념_본질/이론_법칙` | 경제학 이론, 심리학 프레임워크 등 광범위한 지식 체계를 분류.  |
| `event`           | 사건/이슈    | `#출처/개념_본질/사건_이슈` | 특정 시점에 발생한 역사적 사건이나 중요한 이슈를 분류.      |