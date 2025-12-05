---
title: T01_VSCode_Index
level: T01
file_role: original_source
parent: ""
status: planned
priority: medium
process: raw
source_name: vs code 최적화 + 확장 프로그램 활용법(Markdown/개발 효율 극대화)
source_author: self
source_type: ""
references: []
tags:
  - 출처/내부_활동/앱_학습
  - 개념/vscode
---
# 📚 T01_VSCode_Index (Master Index)



## 📌 개요 (Overview)

- **목적:** 이 T01 파일은 **T01_VSCode_Index**과 관련된 모든 T02 노트들을 집계하고 관리하는 마스터 허브입니다.
- **상태:** 이 프로젝트는 현재 **`planned`** 상태입니다.

## 목차

**앱 중심 학습 구조**가 이렇게 압축·정리돼요:

1. **인덱스 T01**
   1. VS Code 학습 전체 인덱스  
2. **리스트 T02**
   1. 핵심 카테고리별 페이지 (여러개 가능)  
   2. 앱별 학습 단계, 핵심 기능, 큰 그림
   3. 예: VS Code → 기본 설정, 확장 프로그램, 터미널 연동, 백업 등
3. **개념 T03** 
   1. 앱 관련 용어·기능·핵심 개념 한 페이지에 요약
   2. 개념/용어 정리 (Workspace, Snippet 등)  
   3. 군더더기 없이 핵심 + 예시 포함
   4. 예: 터미널, Git push, Workspace, Snippet
4. **성찰 (t4)** 
   1. 개인 분석/성찰  
   2. 학습하면서 느낀 점, 개선 아이디어, 나만의 팁
   3. 앱을 직접 다뤄보며 적는 실습 중심
5. **문장 수집 (t5)**
   1. 문장/코드 수집  
   2. 문서·공식 가이드·포럼에서 배운 문장, 명령어, 예시 코드 수집
   3. 필요 시 참조용, 바로 검색 가능
6. **개인 데이터T06**: 
   1. 개인 데이터/설정
   2. 내가 만든 설정, 단축키, 템플릿, 실험 결과 기록
   3. 복습·실습 재활용 용도
---

## 🔗 T02 소스 노트 목록 (Dataview 집계)

*이 노트와 parent 필드로 연결된 모든 T02 노트를 자동으로 집계합니다.*

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "노트 제목",
  status AS "진행 상태",
  priority AS "중요도",
  process AS "Process"
FROM ""
WHERE
  level = "T02" 
  AND contains(parent, this.file.name)
SORT file.mtime DESC
// SORT file.name ASC
```
