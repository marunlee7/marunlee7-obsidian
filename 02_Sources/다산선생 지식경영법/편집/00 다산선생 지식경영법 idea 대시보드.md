---
title: 00 다산선생 지식경영법 idea 대시보드
aliases: []
status: planned
priority: medium
process: raw
source_name: 00 다산선생 지식경영법 idea 대시보드
action_required: link_to_t04
difficulty:	good
satisfaction: 3
links:
tags: [출처/외부_정보/도서_단행본]
---

# 🧠 다산 선생 지식경영법: 아이디어 수집 대시보드

이 목록은 책 정리 노트 전체에서 추출된 **개인적인 통찰, 비판, 적용 아이디어**를 모아 보여줍니다.

```dataviewjs
// 쿼리할 폴더와 태그를 설정합니다.
const FOLDER_PATH = "30-리소스/Booknote/B-다산선생 지식경영법";
const TAG_NAME = "정민/다산선생지식경영법";
const PAGES = dv.pages(`"${FOLDER_PATH}" OR #${TAG_NAME}`); 

let allIdeas = [];

// 모든 파일을 순회하며 콜아웃을 추출합니다.
for (const p of PAGES) {
    if (!p.lists) continue; // lists 속성이 없는 파일은 건너뜁니다.

    for (const t of p.lists) {
        // 콜아웃의 첫 줄을 필터링합니다: 블록 인용으로 시작하며 [!idea를 포함.
        if (t.text.startsWith('>') && t.text.includes('[!idea')) {
            
            // 1. 콜아웃 헤더(첫 줄)에서 콜아웃 타입과 제목을 제거합니다.
            // 정규식: > [!idea] 혹은 > [!idea]+Title 형태를 모두 제거.
            let content = t.text.replace(/^>\s*\[\!idea(\]|(\+\])).*$/, '').trim();

            // 2. 콜아웃의 본문(하위 줄)을 추출하고, 첫 줄과 연결합니다.
            if (t.children && t.children.length > 0) {
                // 자식 노트를 순회하며 > 마커를 제거하고 공백으로 연결합니다.
                const body = t.children.map(c => c.text.replace(/^>\s*/, '').trim()).join(' ');
                
                // 내용이 없더라도 body가 있다면 합칩니다.
                content = (content.length > 0 ? content + ' ' : '') + body;
            }

            // 내용이 비어있지 않다면 리스트에 추가합니다.
            if (content.length > 0) {
                // 출처 링크 생성
                const referencesLink = `[[${p.name}#^${t.blockId} | ${p.name.substring(0, 15)}...]]`;
                
                allIdeas.push(dv.el("li", 
                    `${content} (출처: ${referencesLink})`
                ));
            }
        }
    }
}

dv.header(3, `✅ 총 ${allIdeas.length}개의 아이디어가 추출되었습니다.`);

// 최종 리스트를 출력합니다.
dv.el("ul", allIdeas);
```

