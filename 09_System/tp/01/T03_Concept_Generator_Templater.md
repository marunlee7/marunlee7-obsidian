<%*
// 템플릿 플러그인을 사용하여 사용자 입력 받기
const userInput = await tp.system.prompt("T03 개념 단어 입력");

if (userInput) {
    // QuickAdd API를 사용하여 Gemini API 호출 (AI Assistant 플러그인을 통해)
    const result = await app.plugins.plugins["quickadd"].api.inputPrompt(
      "Gemini",
      `당신은 Obsidian 노트 전문가입니다.
입력된 단어 '${userInput}'에 대해 아래 YAML Frontmatter와 본문을 포함하는 하나의 마크다운 문서를 작성하여 **순수하게 최종 마크다운 결과만** 출력하십시오.

---
title: ${userInput}
aliases: ["동의어", "유사어"]
level: "T03_Dictionary"
file_role: "dictionary"
parent: [[상위 T02 노트 파일명 입력]]
word_type: "개념 유형"
priority: "medium"
process: "draft"
source_name: "{{value:출처 이름 (생략 가능)}}"
source_type: "{{value:book,course,article,web (생략 가능)}}"
source_author: "{{value:출처 저자 (생략 가능)}}"
references: 
- 참고 자료 1
- 참고 자료 2
tags: ["T03/concept", "주제"]
---
# 💡 ${userInput}

## 1. 정의 및 개념 (Definition)
[Gemini가 생성한 정의]

## 2. 출처 및 배경 (Source)
[Gemini가 생성한 출처 설명]`
    );

    // API 결과를 템플릿의 최종 출력(tR)에 저장
    tR = result;
} else {
    // 입력이 취소되면 출력하지 않음
    tR = "";
}
-%>
<%= tR %>