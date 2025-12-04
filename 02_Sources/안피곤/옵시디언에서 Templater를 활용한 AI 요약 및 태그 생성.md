---
aliases: []
source_name: 옵시디언에서 Templater를 활용한 AI 요약 및 태그 생성
references:
  - https://anpigon.tistory.com/484#comment20072093
---
# 옵시디언에서 Templater를 활용한 AI 요약 및 태그 생성

**목차** 반응형

저는 그동안 AI 요약 생성과 태그 생성에 아래 2개 플러그인을 활용하고 있었습니다.

- [AI Summarize](https://github.com/RavenWits/obsidian-ai-summarize)
- [AI Tagger](https://github.com/lucagrippa/obsidian-ai-tagger)

최근 더 좋은 LLM 모델이 계속 공개되고 있지만, 이러한 AI 플러그인의 업데이트 속도는 그만큼 따라가지 못하고 있습니다.  
직접 깃허브 리포지토리에서 코드를 수정하여 모델 추가를 요청했지만, 반영 속도가 만족스럽지 않았습니다.  
  
그래서 최근에는 위 두 플러그인을 삭제하고,[Templator](https://github.com/silentvoid13/Templater/) 플러그인의 템플릿 기능을 활용하여 기능을 비슷하게 만들었습니다.  
  
결과가 만족스러워 공유합니다.

![etc-image-0](https://blog.kakaocdn.net/dn/dB11VM/btsLz7lXeu1/AKAQmzUllbSAZJlkGjmUJ0/img.gif)

  
이 방식을 사용하면 플러그인 개발자가 새로운 모델을 추가해줄 때까지 기다릴 필요 없이 쉽게 변경 가능하고,  
프롬프트도 쉽게 변경 가능하다는 장점이 있습니다.  

---

  
Google Gemini API를 사용했으며, API 키는 [여기](https://aistudio.google.com/app/apikey) 에서 발급받을 수 있습니다.  
Google Gemini API는 무료로 사용 가능합니다.  
  
아래 템플릿에서 \`GEMINI\_API\_KEY\` 는 여러분이 발급받은 API 키로 변경하여 사용하세요.  

## 요약 생성 템플릿

```javascript
<%*const GEMINI_API_KEY="여러분의 GEMINI API KEY"%>

 

<%*

// 요약 프롬프트

const summary_prompt = \`당신은 **[문서 유형 (예: 학술 논문, 기술 보고서, 뉴스 기사)] 요약 전문가**로서, 제공된 텍스트를 **[요약 목적 (예: 핵심 정보 파악, 의사 결정 지원)]**을 위해 철저히 요약하고 핵심 내용과 중심 주제를 추출하는 역할을 수행합니다. 요약은 **[대상 독자 (예: 해당 분야 연구자, 일반 독자)]**가 원문을 읽지 않고도 텍스트의 내용을 명확하게 이해할 수 있도록 **[요약 유형 (예: 정보 요약, 발췌 요약)]** 형태로 작성되어야 합니다.

 

핵심 아이디어를 효과적으로 전달하는 데 집중하여 **[요약 길이 (예: 200단어 내외, 원본의 20%)]**로 명확하고 간결하게 작성해 주세요. 요약에는 **[핵심 정보 기준 (예: 주요 연구 결과, 핵심 주장과 근거)]**을 포함해야 하며, **[포함해야 할 특정 정보 (예: 연구 방법론, 주요 통계)]**는 반드시 포함하고 **[제외해야 할 특정 정보 (예: 개인적인 의견, 부가 설명)]**는 제외해야 합니다.

 

요약 결과물은 **[품질 기준 (예: 정확성, 완결성, 논리적 일관성, 높은 가독성)]**을 충족해야 합니다. 한국어로 답변하며 제목은 포함하지 마세요.\`

%>

 

<%*

// 노트 내용 가져오기

const fileContent = tp.file.content;

%>

 

<%*

const response = await tp.obsidian.requestUrl({

    method: "POST",

    url: "https://generativelanguage.googleapis.com/v1beta/openai/chat/completions",

    headers: {

        "Authorization": "Bearer " + GEMINI_API_KEY,

    },

    body: JSON.stringify({

        model: "gemini-2.0-flash-exp", // 모델명

        messages: [

            { "role": "system", "content": summary_prompt },

            { "role": "user", "content": fileContent }

        ]

    })

});

const summary = response.json.choices[0].message.content;

%>

 

<%*

// 요약 출력하기

tR = \`> [!summary]

> ${summary.split("\n").join("\n> ")}\`;

%>
```

## 태그 생성 템플릿

```javascript
<%*const GEMINI_API_KEY="여러분의 GEMINI API KEY"%>

 

<%*

// 태그 생성 프롬프트

const tag_prompt = \`당신은 **정보 아키텍처 전문가**로서, 제공된 문서를 분석하고 내용에 따라 태그를 생성하는 역할을 수행합니다. 당신의 목표는 문서의 핵심 내용을 정확하게 반영하는 태그를 생성하여 문서 분류 및 검색 효율성을 높이는 것입니다.

 

## 분석 과정

1. 문서를 주의 깊게 읽고 분석합니다.

2. 다음 사항을 고려합니다:

   - 핵심 주제 및 하위 주제

   - 주요 개념 및 테마

   - 문서의 맥락 및 도메인

   - 잠재적 대상 독자

   - 문서 유형 및 목적

 

## 태깅 규칙

1. 기존 태그:

   - 제공된 목록에서 **문서의 핵심 주제를 가장 잘 나타내거나, 문서에서 빈번하게 언급되는 핵심 개념을 포함하는** 1~5개의 태그를 선택합니다.

   - 기존 태그 목록에서 **정확히 일치하는** 태그만 사용해야 합니다.

   - 각 태그는 문서 내용과 **직접적으로 관련된 핵심 내용을 반영**해야 합니다.

 

2. 새로운 태그:

   - 1~3개의 새로운 태그를 생성합니다.

   - 형식: #<카테고리> (예: #머신러닝, #자연어처리)

   - **새로운 태그의 카테고리는 문서의 주요 주제, 유형 또는 목적을 가장 잘 반영하는 용어로 결정합니다.**

   - 기존 태그로 포착되지 않는 **문서의 고유한 측면이나 새로운 관점**을 설명해야 합니다.

   - 기존 태그와의 중복을 피하십시오.

 

## 중요 사항:

- 모든 태그는 # 접두사를 포함해야 합니다.

- 일반적인 태그를 피하고 구체적인 태그를 사용하십시오.

- 일관된 형식을 유지하십시오.

- **출력 형식: 생성된 모든 태그를 쉼표로 구분하여 한 줄로 표시합니다.**

 

## 예시:

 

**기존 태그:**

인공지능, 머신러닝, 딥러닝, 자연어처리, 컴퓨터비전, 데이터분석

 

**문서:**

최근 딥러닝 기술의 발전으로 이미지 인식 분야에서 괄목할 만한 성과들이 보고되고 있다. 특히 컨볼루션 신경망(CNN) 기반의 모델들은 기존 방식 대비 월등한 성능을 보여주며 다양한 산업 분야에 적용되고 있다.

 

**출력:**

#딥러닝, #컴퓨터비전, #이미지인식\`

%>

 

<%*

// 태그 정규화 함수

const processTags = async (file, newTags) => {

  const normalizeTags = tags => [...new Set(tags.map(tag => tag.trim()))];

  

  await tp.app.fileManager.processFrontMatter(file, (frontmatter) => {

    const existingTags = frontmatter?.tags || [];

    frontmatter.tags = normalizeTags([...existingTags, ...newTags]);

  });

};

%>

 

<%*

// 노트 내용 가져오기

const fileContent = tp.file.content;

%>

 

<%*

// 태그 생성하기

const response = await tp.obsidian.requestUrl({

    method: "POST",

    url: "https://generativelanguage.googleapis.com/v1beta/openai/chat/completions",

    contentType: "application/json",

    headers: {

        "Authorization": "Bearer " + GEMINI_API_KEY,

    },

    body: JSON.stringify({

        model: "gemini-2.0-flash-exp",

        messages: [

            { "role": "system", "content": tag_prompt },

            { "role": "user", "content": \`**기존 태그:**

${tp.file.tags}

 

**문서:**

${fileContent}\` }

        ]

    })

});

const tags = response.json.choices[0].message.content.split(",");

%>

 

<%*

// 태그 업데이트

const file = tp.config.target_file

await processTags(file, tags);

%>
```

## 제목 생성 템플릿

```javascript
<%*const GEMINI_API_KEY="여러분의 GEMINI API KEY"%>

 

<%*

// 제목 생성 프롬프트

const title_prompt = \`You are a title generator. 

You will give succinct titles that do not contain backslashes, forward slashes, or colons. 

Generate a title as your response. 

Answer language is korean.\`

%>

 

<%*

// 노트 내용 가져오기

const fileContent = tp.file.content;

%>

 

<%*

// 제목 생성하기

const response = await tp.obsidian.requestUrl({

    method: "POST",

    url: "https://generativelanguage.googleapis.com/v1beta/openai/chat/completions",

    headers: {

        "Authorization": "Bearer " + GEMINI_API_KEY,

    },

    body: JSON.stringify({

        model: "gemini-2.0-flash-exp",

        messages: [

            { "role": "system", "content": title_prompt },

            { "role": "user", "content": fileContent }

        ]

    })

});

const title = response.json.choices[0].message.content;

%>

 

<% await tp.file.rename(title)%>
```

## 사용 방법

작성한 템플릿을 Templater hotkeys에 등록합니다.

![etc-image-1](https://blog.kakaocdn.net/dn/c8bSx7/btsL26sUceS/RHQuib9ngIBxdIO0DHReok/img.png)

  
만약 자주 사용하는 명령어라면 명령어 팔레트의 즐겨찾는 명령어에 등록합니다.

![etc-image-2](https://blog.kakaocdn.net/dn/bOfpD1/btsL3l4s6QS/nLeKX00cFSmAky1dG509qK/img.png)

## 💡\[팁\] Commander 플러그인 활용하기

Commander는 사용자 인터페이스의 여러 부분에 명령을 추가하거나, 매크로를 생성할 수 있는 옵시디언 플러그인입니다.  
  
👉 [Commander 플러그인 설치하기](https://github.com/phibr0/obsidian-commander)  

### 🛠️ 에디터 Tab Bar에 아이콘 추가하기

Commander 설정의 **Tab Bar** 섹션에서 명령어를 추가하면, 에디터 창 오른쪽 상단에 명령어 실행 아이콘 버튼이 생성됩니다.

![etc-image-3](https://blog.kakaocdn.net/dn/bpl6OJ/btsLAgi6aY3/uKMDhbR6RQOkqkQ3yrgi41/img.png)

### 🛠️ 명령어 2개 이상 조합하여 사용하기

Commander 설정의 **Macro** 섹션에서 매크로를 추가하면, 여러 명령을 조합하여 하나의 명령어를 만들 수 있습니다. 매크로에서 생성한 명령어를 다시 Tab Bar에 추가하여 사용할 수 도 있습니다.

![etc-image-4](https://blog.kakaocdn.net/dn/n6Kr9/btsL3qrbkcQ/KMOGYdTDEm1WCkIWV6ysO0/img.png)

## 같이 보면 좋은 영상

| 구요한님의 옵시디언 AI 활용 방법 | 테디노트님의 옵시디언 Templater 활용 방법 |
| --- | --- |

- 테디노트님의 Templater 템플릿: [https://github.com/teddylee777/obsidian-templater](https://github.com/teddylee777/obsidian-templater)

---

궁금한 점이 있다면 언제든지 댓글로 문의해 주세요.

반응형 [저작자표시 비영리 변경금지](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.ko)

### ' > ' 카테고리의 다른 글

| [옵시디언에서 DeepSeek R1 무료로 사용하기](https://anpigon.tistory.com/485) (1) | 2025.01.30 |
| --- | --- |
| [옵시디언 웹 클리퍼 활용: 예스24 도서 정보를 편리하게 저장하는 방법 (템플릿 공유)](https://anpigon.tistory.com/483) (7) | 2024.12.16 |
| [옵시디언 빠른 메모의 모든 것](https://anpigon.tistory.com/471) (5) | 2024.11.11 |
| [옵시디언에서 Llama3-70b 모델 사용하기](https://anpigon.tistory.com/462) (0) | 2024.04.27 |
| [Fleeting Notes Sync: 모바일 앱에서 빠르게 메모하여 옵시디언으로 동기화하기](https://anpigon.tistory.com/459) (7) | 2024.02.12 |

## 要約 ✍︎

## 思索 🙇🏻
