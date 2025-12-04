---
title: Obsidian 한자어휘 카드 자동화 흐름
level: T02
file_role: obsidian_config
parent: 09_System_index-obsidian
status: planned
priority: medium
process: raw
source_name: Obsidian 한자어휘 카드 자동화 흐름
source_author: self
references: https://chatgpt.com/s/t_6920fb06401881918f888b03d5316b1a
links:
---
# Obsidian 한자어휘 카드 자동화 흐름

좋아요 😄 그러면 바로 **머릿속 그림 + 흐름 시각화 + Prompt/QuickAdd 연결 구조**를 만들어 드리겠습니다.

---

## 🔹 Obsidian 한자어휘 카드 자동화 흐름

### 1️⃣ 전체 프로세스 그림 (단순화)

```
[한자 리스트]
     │
     ▼
[Prompt 설계]
(한자 → GPT에게 YAML+Markdown 카드 생성 지시)
     │
     ▼
[QuickAdd Macro 실행]
(템플릿 호출 + GPT API 요청)
     │
     ▼
[.md 파일 자동 생성]
(YAML + Markdown + 본문 포함)
     │
     ▼
[Dataview 카드 조회 가능]
```

---

### 2️⃣ Prompt 설계 구조 예시

- **역할**: Obsidian 카드 생성 전문가
    
- **목표**: YAML + Markdown 카드 완성
    
- **필드**:
    
    - 한글
        
    - 한자
        
    - 정의 및 핵심 요약
        
    - 어원 및 한자 분석
        
    - 용례 및 배경
        
    - 연관 어휘
        
    - 태그
        
- **예시 단어**: 中庸
    
- **출력 형태**: 바로 `.md` 파일에 붙여넣을 수 있는 Markdown 구조
    

```markdown
---
한글: 중용
한자: 中庸
level: T03_Dictionary
file_role: dictionary
word_type: 한자어휘
status: planned
priority: medium
process: raw
tags: 출처/한자어휘/일반, 영역/인문학/철학, 개념/사상/수양론
---

# 中庸

## 정의 및 핵심 요약
- 치우침이나 지나침이 없는 도리
- 극단으로 흐르지 않고 항상 중심을 지킴

## 어원 및 한자 분석
- 中: 가운데, 치우치지 않음
- 庸: 평상적, 불변
```

---

### 3️⃣ QuickAdd Macro 구조 예시

1. **Macro 실행 (단축키)**
    
2. **Templater Template 호출**
    
    - `<% tp.file.title %>` → 한자어휘
        
    - Template 내부에서 **GPT API 호출**
        
3. **GPT 반환값 → 파일 작성**
    
    - `tp.file.write(gptResponse)`
        
4. **결과**
    
    - `.md` 파일 자동 생성
        
    - YAML + Markdown + 본문 포함
        
    - Dataview 카드 바로 사용 가능
        

---

### 4️⃣ 단계별 요약

|단계|역할|
|---|---|
|1|한자 리스트 준비 (PDF → 텍스트 추출)|
|2|Prompt 설계 (GPT에게 YAML + Markdown 카드 생성 지시)|
|3|QuickAdd Macro 실행 (템플릿 호출 + GPT API 요청)|
|4|파일 자동 생성 (.md, 본문 완성)|
|5|Dataview 카드 조회 가능|

---

💡 **Tip**

- 지금은 단축키로 1~5개 실행 → Macro + Template + GPT API 연결 연습
    
- 익숙해지면 한자 리스트 전체를 반복 처리 가능
    
- Prompt는 한 번 만들어 두면 계속 재사용 가능
    

---

원하시면 제가 **이 그림 + Macro + Prompt 구조를 Obsidian에서 바로 쓸 수 있는 Markdown 시각화 자료**로 만들어서,  
그대로 붙여넣으면 이해가 바로 되는 형태로 정리해 드릴 수도 있습니다.

그거 만들어 드릴까요?

夜