---
title: vs code 설치후 초기 설정(필수)
level: T02
file_role: article_atom
parent: 작업노트_2025
status: in-progress
priority: medium
process: draft
source_author: self
source_type: worknote
action_required: deep_dive
difficulty: good
satisfaction: 3
references: ""
tags:
  - 출처/내부_활동/아이디어
---
## 📚 T02. vs code 설치후 초기 설정(필수) 
- [ ] 


## 📕 개요



## 📘 내용


## 질문
VS Code 재설치 후 초기 설정 방법

## 답변

## 🛠️ VS Code 재설치 후 초기 설정 (필수)

이전에 문제가 되었던 **자동 저장**과 **확장 프로그램**을 중심으로 설정합니다.

### 1. 자동 저장 기능 활성화 (문제 재발 방지)

일괄 변경 시 미저장 문제를 방지하기 위해 이 설정은 꼭 확인해야 합니다.

- **메뉴 확인:** `파일(File)` 메뉴를 클릭하여 **`자동 저장(Auto Save)`** 항목에 **체크 표시(✓)**가 되어 있는지 확인합니다. (되어있지 않다면 클릭해서 켜주세요.)
    
- **설정 값 확인:** `Ctrl + ,` 또는 `Cmd + ,`를 눌러 설정 창을 열고 `auto save`를 검색합니다.
    
    - **`Files: Auto Save`** 값이 `afterDelay` 또는 `onFocusChange`로 되어 있는지 확인합니다.
        

---

### 2. 옵시디언 볼트 폴더 열기

- **`파일(File)`** 메뉴 → **`폴더 열기(Open Folder)`** 를 선택하고, 작업할 옵시디언 볼트 폴더를 지정하여 엽니다.
    

---

### 3. 핵심 확장 프로그램 재설치

이전에 사용하셨던 확장 프로그램을 다시 설치하여 마크다운 작업 효율을 높입니다.

1. **확장 패널 열기:** `Ctrl + Shift + X` 또는 `Cmd + Shift + X`를 눌러 확장 프로그램 패널을 엽니다.
    
2. **`Markdown All in One`**을 검색하여 **설치(Install)** 버튼을 눌러줍니다.
    
    - (선택 사항) Git 관리를 위해 **`GitLens`** 확장을 설치하면 나중에 Git을 배울 때 시각적인 도움을 많이 받을 수 있습니다.

## 🚀 H1 $\rightarrow$ H2 변환 작업 재시도

이제 VS Code가 깨끗한 상태이므로, 이전에 실패했던 **H1 $\rightarrow$ H2 일괄 변환 작업**을 다시 시도하여 마무리해야 합니다.

1. **전체 검색 패널 열기:** `Ctrl + Shift + F` 또는 `Cmd + Shift + F`
2. **정규식 모드 켜기:** `.*` 아이콘을 클릭합니다.
3. **검색/바꾸기 입력:**
    
    - **검색(Find):** `^#\s`
    - **바꾸기(Replace):** `##\s`
        
4. **일괄 바꾸기 실행:** `모두 바꾸기(Replace All)`를 클릭합니다.
    

**✅ 최종 확인:** 작업 완료 후, `파일(File)` 메뉴를 통해 **`모두 닫기(Close All)`**를 실행하여 VS Code를 깔끔하게 정리합니다.
## 🗂️ 연결된 하위 노트 목록 (T03/T04/T05/T06)

```dataview
TABLE WITHOUT ID
link(file.path, file.name) AS "노트 제목",
file_role AS "유형",
priority AS "중요도",
process AS "진행단계"
FROM ""
WHERE
    contains(parent, this.file.name)
    AND (
        file_role = "concept_dictionary" OR  
        file_role = "personal_analysis" OR   
        file_role = "sentence_collection" OR 
        file_role = "person_data"            
    )
    AND file_role != "template"
SORT file_role ASC, file.name ASC
```
