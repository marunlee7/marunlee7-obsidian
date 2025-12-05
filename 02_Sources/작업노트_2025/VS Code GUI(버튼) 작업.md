---
title: T-시스템 구조 변경 작업 리스트
level: T02
file_role: original_source
parent: 작업노트_2025
status: completed
priority: high
process: draft
source_name: ""
source_author: self
source_type: worknote
action_required: none
difficulty: good
satisfaction: 3
references: ""
tags:
  - task
  - 출처/내부_활동/아이디어
---
## 📚 VS Code GUI(버튼) 작업


말씀하신 상황을 기준으로 정리하면:

- **상황**: 좌측 소스 제어(버튼)에 `2327개의 보류중인 변경 내용`이 떠 있음 → 파일 몇 개 수정 → 다시 숫자가 뜸 → 커밋/푸시 필요.
    
- **선택**: GUI(버튼)로 작업 vs 터미널 명령어로 작업
    

📌 **GUI 방식 장점**

1. 시각적으로 파일 상태 확인 가능 (`M`=수정, `U`=추가 등)
    
2. 원하는 파일만 선택해서 스테이징 가능
    
3. 스테이징 → 커밋 → 푸시 과정을 클릭으로 순서대로 진행
    
4. 충돌/오류 발생 시 바로 알림
    

📌 **GUI 진행 순서**

1. **소스 제어 아이콘 클릭** (좌측 3번째)
    
2. **변경된 파일 확인** → 커밋하고 싶은 파일 **체크박스 선택**
    
    - 전체 선택하려면 위쪽 `+` 버튼 클릭 → 스테이징
        
3. **커밋 메시지 작성** → 하단 `✓ Commit` 클릭
    
4. **푸시** → 상단 `…` 메뉴 또는 `Push` 버튼 클릭
    

💡 **팁**:

- `+` 버튼 = 선택한 파일을 **스테이징**
    
- 체크 안 하면 커밋되지 않음
    
- 커밋 후 푸시 안 하면 로컬에만 저장
    

원하시면 제가 **화면 버튼 기준으로 2327개 변경 내용 처리 순서**를 한눈에 볼 수 있게 단계별로 그림처럼 정리해서 보여 드릴 수도 있어요.  
그렇게 해 드릴까요?



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
SORT file_role ASC, file.name ASC
```
