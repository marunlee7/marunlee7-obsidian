<%*
// ============================================================
// 1. 설정 (여기에 Gemini API KEY를 입력하세요)
// ============================================================
const API_KEY = "AIzaSyCswFj_TWjGVlvgPHNWbGQzdzAKtdgwKq4"; 
const API_URL = "https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=" + API_KEY;

// ============================================================
// 2. 노트 내용 및 제목 가져오기 (T02 노트 내용)
// ============================================================
const fileContent = tp.file.content; 
const parentNoteTitle = tp.file.title; // T02 제목을 T03의 parent로 사용

if (fileContent.length < 100) {
    new Notice("T02 노트 내용이 너무 짧습니다. 100자 이상이어야 분석이 가능합니다.");
    return;
}

// ============================================================
// 3. 1차 API 호출: T02 내용 분석 및 핵심 개념 목록 JSON 추출
// ============================================================
const listPrompt = `
당신은 Obsidian 노트 전문가입니다. 
아래 [문서 내용]을 분석하여, T03 개념 노트로 만들기에 적합한 **가장 중요한 핵심 개념 5개**를 한국어 단어로 추출하세요.
반드시 JSON 배열만 출력하고, 마크다운 코드블록(\`\`\`json)이나 설명은 생략하세요.

## 출력 JSON 형식
["개념1", "개념2", "개념3", "개념4", "개념5"]

## 문서 내용
---
${fileContent}
---
`;

let concepts = [];
try {
    new Notice("1/2 단계: T02 내용 분석 및 핵심 개념 목록 추출 중...");
    
    let response = await requestUrl({
        url: API_URL,
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
            contents: [{ parts: [{ text: listPrompt }] }]
        })
    });
    
    if (response.status === 200) {
        const rawText = response.json.candidates[0].content.parts[0].text;
        const jsonStr = rawText.replace(/```json|```/g, "").trim();
        concepts = JSON.parse(jsonStr);
        new Notice(`핵심 개념 ${concepts.length}개 추출 완료!`);
    } else {
        new Notice("API 호출 실패 (개념 추출): " + response.status);
        return;
    }
} catch (error) {
    console.error("개념 추출 오류:", error);
    new Notice("개념 추출 중 심각한 오류 발생 (Console 확인)");
    return;
}

// ============================================================
// 4. 2차 API 호출 (Loop): 각 개념별 T03 파일 생성
// ============================================================

for (const concept of concepts) {
    if (!concept || concept.trim() === "") continue;

    const detailPrompt = `
    당신은 Obsidian 노트 전문가입니다.
    아래 [문서 내용]을 분석하고, **Google Search를 활용하여 정보를 보강**한 후, '${concept}' 개념에 대해 Obsidian T03 개념 노트 형식에 맞게 아래 JSON 형식으로 데이터를 생성하세요.

    ## 추출 조건
    1. **[문서 내용]**과 **검색 결과**를 기반으로 '${concept}'을 정의하고 설명하세요.
    2. word_type은 '한자어휘', '순우리말', '영어', '개념', '인물', '서명' 중 하나를 선택하여 지정하세요.
    3. 태그는 **3단계 계층 구조**('영역/주제/상세', '개념/기능/상세')를 포함하여 2개 이상 생성하세요.
    4. references 필드에 **검색을 통해 확보한 출처**를 포함하세요.

    ## 출력 JSON 형식 (반드시 JSON 객체만)
    {
      "aliases": ["동의어1", "유사어2"],
      "word_type": "유형",
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

    let data = {};
    try {
        new Notice(`2/2 단계: [${concept}] 분석 및 T03 생성 중...`);
        
        let response = await requestUrl({
            url: API_URL,
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({
                contents: [{ parts: [{ text: detailPrompt }] }],
                tools: [{ googleSearch: {} }] // Google Search 활성화
            })
        });

        if (response.status === 200) {
            const rawText = response.json.candidates[0].content.parts[0].text;
            const jsonStr = rawText.replace(/```json|```/g, "").trim();
            const geminiJson = JSON.parse(jsonStr);
            
            data = { ...geminiJson };
            data.word_type = data.word_type || "개념";
            data.title = concept;
            
            // T03 파일 생성 및 내용 쓰기
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
            new Notice(`[${concept}] T03 파일 생성 완료!`);

        } else {
            new Notice(`[${concept}] API 호출 실패: ${response.status}`);
        }
    } catch (error) {
        console.error(`[${concept}] 처리 중 오류 발생:`, error);
        new Notice(`[${concept}] T03 자동화 오류 발생 (Console 확인)`);
    }
}

new Notice("T03 다중 개념 자동화 프로세스 완료.");

// 템플릿 실행 후 현재 T02 노트에는 내용을 남기지 않습니다.
-%><% tp.file.cursor() %>