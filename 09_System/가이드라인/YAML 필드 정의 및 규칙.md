---
title: YAML 필드 정의 및 규칙
level: T09
file_role: system_config
---

## 1. ⚙️ YAML 필드 정의 및 규칙

t1 - t2- t3- t4- t5
김정운의 감정이설(칼럼 시리즈) - 챕터(02_Sources) - 용어(03_Concepts) - 분석(04_Analysis) - 문장수집(05_Collection)
하루 한자 공부(북) - 챕터(02_Sources) - 용어(03_Concepts) - 분석(04_Analysis) - 문장수집(05_Collection)

이 흐름대로 옵시디언에서 템플릿을 만들고 기록할거야.
필요한 YAML 필드 정의 및 규칙

| Key               | 정의 (Definition)        | 값 (Possible Values)                                                                                                          | T-Level 적용 (템플릿 기반) |
| ----------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| `aliases`         | 별칭 목록                  |                                                                                                                              |                     |
| `title`           | 노트의 공식 제목              | `{{value:제목_입력}}`, `09_T-System_Master_Manual 1`,                                                                            |                     |
| `published`       | 원본 발행 날짜               | `{{value:원본_발행_날짜}}`                                                                                                         |                     |
| `level`           | T-System의 논리적 레벨       | `T01`- `T09`                                                                                                                 |                     |
| `file_role`       | 파일의 시스템 내 역할           | `series_collection`, <br>`article_atom`, `concept_dictionary`, `personal_analysis`, `sentence_collection`<br>`system_config` |                     |
| `parent`          | 상위 노트 연결 고리 (지식 흐름 추적) |                                                                                                                              |                     |
| `word_type`       | T03에서 다루는 개념의 유형       | `term`, `person`, `model`, `theory`, `event`                                                                                 |                     |
| `status`          | 작업 진행 상태               | `planned`, `in-progress`, `waiting/blocked`, `completed`                                                                     |                     |
| `priority`        | 노트의 중요도                | `low`, `medium`, `high`                                                                                                      |                     |
| `process`         | 내용의 품질 단계              | `raw`, `,draft`, `final`                                                                                                     |                     |
| `source_name`     | 출처 이름                  | `{{value:출처_이름}}`<br>`self`                                                                                                  |                     |
| `source_author`   | 출처 저자                  | `{{value:출처_저자}}`<br>`self`                                                                                                  |                     |
| `source_type`     | 출처의 유형                 | `book`<br>`article`<br>`report`<br>`video`<br>`podcast`<br>`lecture`<br>`course`<br>`web_generic`<br>`discussion`            |                     |
| `action_required` | 학습 및 행동 요구사항           | `none`, `deep_dive`, `memorize`, `daily_use`                                                                                 |                     |
| `difficulty`      | 내용의 난이도                | `again`, `hard`, `good`, `easy`, `none`                                                                                      |                     |
| `satisfaction`    | 내용에 대한 개인 만족도 (1~5)    | `1` - `5`                                                                                                                    |                     |
| `references`      | 외부 참조 링크/파일            |                                                                                                                              |                     |
| `tags`            | 분류 태그 (3단 구조 원칙)       | 3단 구조<br>`출처/1단/2단`, <br>`영역/1단/2단`, <br>`개념/1단/2단` )                                                                        |                     |

