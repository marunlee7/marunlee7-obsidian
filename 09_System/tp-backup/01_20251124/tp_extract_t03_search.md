<%*
// ============================================================
// 1. 설정 (여기에 Gemini API KEY를 입력하세요)
// ============================================================
const API_KEY = "AIzaSyCswFj_TWjGVlvgPHNWbGQzdzAKtdgwKq4"; 
const API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=" + API_KEY;

// ============================================================
// 2. 노트 내용 및 제목 가져오기
// ============================================================
// 현재 활성화된 T02 노트의 본문 내용을 가져옵니다. (AI 분석용 소스)
const fileContent = tp.file.content; 
const parentNoteTitle = tp.file.title; 

// ============================================================
// 3. 사용자 입력 받기
// ============================================================
const concept = await tp.system.prompt("T03 개념 단어 입력 (T02 내용에서 추출/보강할 단어)");

if (!concept || fileContent.length < 50) {
    new Notice("개념 단어가 입력되지 않았거나 T02 노트 내용이 충분하지 않습니다.");
    return;
}

// ============================================================
// 4. Gemini API 호출 (Google Search Tool 활성화)
// ============================================================

const promptText = `
당신은 Obsidian 노트 전문가입니다.
아래 제공된 [문서 내용]에서 **'${concept}'** 개념을 분석하고, **Google Search를 활용하여 정보를 보강**한 후, Obsidian T03 개념 노트 형식에 맞게 아래 JSON 형식으로 데이터를 생성하세요.

## 추출 조건
1. **[문서 내용]**과 **검색 결과**를 기반으로 '${concept}'을 정의하고 설명해야 합니다.
2. word_type은 '한자어휘', '순우리말', '영어', '개념', '인물', '서명' 중 하나를 선택하여 지정하세요.
3. 태그는 **3단계 계층 구조**('영역/주제/상세', '개념/기능/상세')를 포함하여 2개 이상 생성해야 합니다.
4. references 필드에 **검색을 통해 확보한 출처**를 포함하세요.

## 출력 JSON 형식
반드시 JSON 객체만 출력하고 마크다운 코드블록(\`\`\`json)이나 설명은 생략하세요.

{
  "aliases": ["동의어1", "유사어2"],
  "word_type": "유형(예: 개념)",
  "references": ["검색 출처 1", "검색 출처 2"],
  "tags": ["T03/concept", "영역/주제/상세", "개념/기능/상세"],
  "definition": "핵심 정의 (한 문장)",
  "detail": "문서 내용과 검색 결과를 기반으로 한 상세 요약 (2-3문장)"
}

## 문서 내용
---
${fileContent}
---
`;

let data = {
    title: concept,
    aliases: [],
    word_type: "Draft",
    references: [],
    tags: [],
    definition: "",
    detail: ""
};

try {
    new Notice("Gemini에게 요청 중 (Google Search 사용)...");
    
    const response = await requestUrl({
        url: API_URL,
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
            contents: [{ parts: [{ text: promptText }] }],
            // ======= 핵심: Google Search 툴 활성화 =======
            tools: [{ googleSearch: {} }] 
            // =============================================
        })
    });

    if (response.status === 200) {
        const rawText = response.json.candidates[0].content.parts[0].text;
        const jsonStr = rawText.replace(/```json|```/g, "").trim();
        const geminiJson = JSON.parse(jsonStr);
        
        data = { ...data, ...geminiJson };
        data.word_type = data.word_type || "개념";
        data.title = concept;
        new Notice("T03 데이터 수신 완료!");

        // ============================================================
        // 5. 새 노트 생성 및 내용 출력 (T03 파일 완성)
        // ============================================================
        const newFileName = \`\${concept}.md\`;
        const newFile = await tp.file.create_new(newFileName, "", false); 
        
        const fileContentOutput = `---
title: ${data.title}
aliases: [${data.aliases.map(a => \`"\${a}"\`).join(", ")}]
level: "T03_Dictionary"
file_role: "dictionary"
parent: [[${parentNoteTitle}]]
word_type: "${data.word_type}"
priority: "medium"
process: "draft"
source_name: "Gemini AI + Web Search"
source_type: "ai_generation"
source_author: "Gemini"
references: 
${data.references.map(r => \`- \${r}\`).join("\\n")}
tags: [${data.tags.map(t => \`"\${t}"\`).join(", ")}]
---
# 💡 ${data.title}

## 1. 정의 및 개념 (Definition)
${data.definition}

${data.detail}

## 2. 출처 및 배경 (Source)
- 분석된 T02 노트 제목: [[${parentNoteTitle}]]
- 이 내용은 Gemini AI가 T02 내용과 Web Search 결과를 조합하여 생성했습니다. 검증 및 수정이 필요합니다.
`;

        await app.vault.modify(newFile, fileContentOutput);
        await app.workspace.activeLeaf.openFile(newFile); 

    } else {
        new Notice("API 호출 실패: " + response.status);
    }
} catch (error) {
    console.error("Gemini API 처리 중 오류 발생:", error);
    new Notice("T03 자동화 오류 발생 (Console 확인)");
}
-%><% tp.file.cursor() %>