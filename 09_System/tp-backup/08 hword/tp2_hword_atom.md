<%*
const T02Title = await tp.system.prompt("T02 칼럼 제목 입력 (예: 煩多(번다))");

// ===================================================================
// T01 마스터 노트를 동적으로 가져오는 코드 (적용됨)
// ===================================================================

const dv = app.plugins.plugins['dataview']?.api;
let T01Titles = ["(T01 마스터를 먼저 생성해 주세요)"]; // 기본값 설정

if (dv) {
  // Vault 전체에서 file_role이 'series_collection'인 파일 이름을 배열로 가져옵니다.
  T01Titles = dv.pages('')
    .where(p => p.file_role === "series_collection") 
    .map(p => p.file.name)
    .array();
  
  // 검색 결과가 없다면 기본값을 유지
  if (T01Titles.length === 0) {
      T01Titles = ["(T01 마스터를 먼저 생성해 주세요)"];
  }
}

// 템플릿 Suggester에 동적 배열을 사용합니다.
const T01Parent = await tp.system.suggester(T01Titles, T01Titles[0], false, "T01 마스터 지정 (동적 목록)");
// ===================================================================

const sourceAuthor = await tp.system.prompt("저자 이름 입력");
const now = tp.date.now("YYYY-MM-DD");
_%>---
title: "<% T02Title %>"
aliases: []
level: "T02"
file_role: "article_atom"
parent: '[[<% T01Parent %>]]' # 🚨 최종 수정: 홑따옴표로 감싸 YAML 파싱 오류 방지

source_name: "<% T02Title %>"     
source_author: "<% sourceAuthor %>" 
source_type: "article"                 

tags: 
  - 출처/문헌/칼럼 
series_num: 

created: <% now %>
modified: <% now %>   
process: raw         
priority: medium                    
page_range: 
published: 
references:
links: 
anki: 
checkbox: false
read: false
---

# 📖 <% T02Title %> (<% sourceAuthor %>)

## 📘 어휘 추출 및 요약

## 📗 청상 (발췌 및 사색)

### 1. 주요 발췌 1 (Sub-Heading)
> "인용문... 특히 중요하거나 사색이 필요한 부분"

## 🔗 MOC 이 칼럼에서 파생된 모든 개념/어휘 (Dataview 쿼리)

```dataview
TABLE 
    source_author AS "저자", 
    created AS "정리일"
FROM ""
WHERE level = "T03_Dictionary"
  AND parent = this.file.link  
SORT created ASC
```
