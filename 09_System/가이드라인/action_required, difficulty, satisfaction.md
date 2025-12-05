---
title: 학습 경험 YAML 필드 최종 확정 테이블
level: T09
file_role: system_config
parent: "[[09_System/가이드라인/09_T-System_Master_Manual]]"
---

## 🚦 학습 경험 YAML 필드

| YAML 키 (Field Key) | 최종 확정 값 (영문 표준)                                                   |                                                                    | 한국어 정의 및 역할                            | 충돌 방지 논리                                            |
| ------------------ | ----------------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------- | --------------------------------------------------- |
| `action_required`  | `memorize`<br><br>`deep_dive`<br><br>`daily_use`<br><br>`none`    | `암기`<br><br>`심화_탐구`<br><br>`일상_활용`<br><br>`none`                   | 노트 내용에 대해 취할 후속 조치. (행동 동사)            | 기존 SSoT 값과 충돌 없음.                                   |
| `difficulty`       | `again`<br><br>`hard`<br><br>`good`<br>  <br>`easy`<br><br>`none` | `다시_학습`<br><br>`복습_필요`<br><br>`이해_완료`<br><br>`매우_쉬움`<br><br>`none` | Anki 시스템을 응용한 주관적 이해도. 복습 주기를 결정합니다.   | `priority: high/medium/low`와 완전히 다른 Anki 스타일 단어 사용. |
| `satisfaction`     | 1~5점 척도                                                           | `만족도_상`<br><br>`만족도_중`<br><br>`만족도_하`<br><br>`none`                | 노트 내용에 대한 개인적인 흥미도나 만족도. 동기 부여에 활용합니다. |                                                     |


