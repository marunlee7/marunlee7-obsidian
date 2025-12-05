---
title: 옵시디언 템플레이터(Templater) - 교보문고 도서 검색(제목, 저자)한 다음 선택하여 정보 가
aliases: []
level: T02
file_role: article_atom
parent: "북마크"
word_type: t3전용 # T03 전용 필드 (빈 값 유지)
status: planned
priority: medium
process: raw
source_name: 옵시디언 템플레이터(Templater) - 교보문고 도서 검색(제목, 저자)한 다음 선택하여 정보 가
source_author: "self"
source_type: "article"  
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-Templater-%EA%B5%90%EB%B3%B4%EB%AC%B8%EA%B3%A0-%EB%8F%84%EC%84%9C-%EA%B2%80%EC%83%89%ED%95%9C-%EB%8B%A4%EC%9D%8C-%EC%84%A0%ED%83%9D%ED%95%98%EC%97%AC-%EC%A0%95%EB%B3%B4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0
tags: [출처/외부_수집/북마크]
---
# 옵시디언 템플레이터(Templater) - 교보문고 도서 검색(제목, 저자)한 다음 선택하여 정보 가져오기

## My Thought


## 요약

메타 데이터(Frontmatter)에 제목과 저자 정보를 입력하고 템플레이터를 실행하여 교보문고 검색을 합니다. 그 검색 목록을 옵시디언의 목록 선택창을 써서 표시합니다. 그 목록 가운데 찾고 있는 도서를 선택하면 그 정보가 메타 데이터와 본문에 넣어지도록 합니다.

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbAa02u%2Fbtr9z83iv3E%2FAAAAAAAAAAAAAAAAAAAAALrpst89suyBt2ItiZUtkyrr7yxobxVFNP-aHV1nxDiB%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1761922799%26allow_ip%3D%26allow_referer%3D%26signature%3Dq4uQnbGDU0Vt6huWT%252FARF75DOIU%253D)

검색 목록 창

설치 방법은 다음 슬라이드를 보면 됩니다.

[https://docs.google.com/presentation/d/1eFoL\_hvWVsFJevjQ6gXbOtt9mZovm\_OIjbSj56cxniM/edit?usp=sharing](https://docs.google.com/presentation/d/1eFoL_hvWVsFJevjQ6gXbOtt9mZovm_OIjbSj56cxniM/edit?usp=sharing)

### Dataview 목록 예시

다음 Dataview 코드 블럭은 위에서 가져온 정보로 만들어진 노트들을 책표지 썸네일과 제목, 저자로 표로 만들어 보여 줍니다. 자신의 메타데이터(frontmatter) 구조가 저와 다르다면 조금 바꿔야 합니다.

```bash
---
cssclass: cards, cards-cover, cards-2-3, table-100, width-100
---

\`\`\`dataview
table without id 
    ("![|80](" + cover + ")") as Cover,
    ("[[" + file.path + "|" + book-title + "]]") as Title,
    join(nonnull(list(authors.authors, authors.translaters)), ", ") as Authors,
    publisher as Publisher, 
    string(replace(publish-date," (", "<br>(")) as P-date, 
    category as Category,
    default(rating, "") + padright("", default(rating, 0), "⭐")  as Rating
from #book
where cover != null
\`\`\`
```
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FOlZjN%2FbtseK8EBXoL%2FAAAAAAAAAAAAAAAAAAAAACuT65ZEFim40QdNcDNyCADCNtzBgA3Xc1VccOiXab0A%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1761922799%26allow_ip%3D%26allow_referer%3D%26signature%3DcQsYbgM3Llu2EoUPLOC1Gl8l7Z4%253D)

도서정보 노트의 목록을 보여주는 Dataview 코드 블럭

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fb3kr7W%2FbtseTgUQ4Qa%2FAAAAAAAAAAAAAAAAAAAAANUGtBLeSsFLW5YOl1kxUbZ9RCYtmGgskpLNe_CxW3sq%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1761922799%26allow_ip%3D%26allow_referer%3D%26signature%3D0tLQDAEE3wvIdpqoM9VZ33wRq%252BE%253D)

도서정보 노트의 목록 - 테이블 보기

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbsSPzt%2FbtseQVcVjwL%2FAAAAAAAAAAAAAAAAAAAAAPSWVP8zv09Ly-Qnu9fKRVj9K7OIZLBnSnC8p1UP6CdD%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1761922799%26allow_ip%3D%26allow_referer%3D%26signature%3Djx29kLmY5r2PwaB2D%252BfXe2L46mk%253D)

도서정보 노트의 목록 - 카드 보기

## 소스 코드

제 Gist 코드입니다.

tr\_search\_kyobobook.js - 검색 실행

([https://gist.github.com/eoureo/c7459151106ec98187b4589e8fdff57d/raw/(2)%20tr\_search\_kyobobook.js](https://gist.github.com/eoureo/c7459151106ec98187b4589e8fdff57d/raw/\(2\)%20tr_search_kyobobook.js))

(Tr) 교보문고 검색.md - 템플릿 파일(⚠️ 주의! 확장자를 md로 해야 함)

([(Tr) 교보문고 검색.md.js 파일 링크](https://gist.githubusercontent.com/eoureo/c7459151106ec98187b4589e8fdff57d/raw/\(3\)%20\(Tr\)%20%EA%B5%90%EB%B3%B4%EB%AC%B8%EA%B3%A0%20%EA%B2%80%EC%83%89.md.js))

```bash
<%_*
        
        
          

          let url = tp.frontmatter["url"];
        
        
          

          

        
        
          

          // 메타 데이터에 url이 있으면 검색 없이 바로 책 정보 가져옴.
        
        
          

          // 메타 데이터에 url이 없으면 검색.
        
        
          

          if(!url) {
        
        
          

            // 메타 데이터에서 book title과 authors를 가져 온다.
        
        
          

            const title = tp.frontmatter["book title"]? tp.frontmatter["book title"]: "";
        
        
          

            const authors = tp.frontmatter["authors"]? tp.frontmatter["authors"]: [];
        
        
          

            console.log(title);
        
        
          

            console.log(authors);
        
        
          

          

        
        
          

            // 저자 정보를 문자로 바꾸기
        
        
          

            let authors_str = "";
        
        
          

            if(typeof authors == "string") {
        
        
          

              authors_str = authors;
        
        
          

            }
        
        
          

            else if(authors instanceof Array) {
        
        
          

              authors_str = authors.join(" ");
        
        
          

            }
        
        
          

            else {
        
        
          

              for(let key in authors) {
        
        
          

                if(typeof authors[key] == "string") {
        
        
          

                  authors_str += " " + authors[key];
        
        
          

                }
        
        
          

                else if(authors[key] instanceof Array) {
        
        
          

                  authors_str += " " + authors[key].join(" ");
        
        
          

                }
        
        
          

              }
        
        
          

            }
        
        
          

          

        
        
          

            // 검색하여 책 정보 주소를 가져온다.
        
        
          

            try {
        
        
          

            url = await tp.user.tr_search_kyobobook(tp, title, authors_str);
        
        
          

            }
        
        
          

            catch(e) {
        
        
          

              console.log(e);
        
        
          

            }
        
        
          

          }
        
        
          

          

        
        
          

          console.log("url:", url);
        
        
          

          

        
        
          

          if(url) {
        
        
          

            // 책 정보 가져옴.
        
        
          

            tR = await tp.user.tr_get_kyobobook_info(tp, url);
        
        
          

            if(tR == "") {
        
        
          

              return;
        
        
          

            }
        
        
          

          }
        
        
          

          else {
        
        
          

            return;
        
        
          

          }
        
        
          

          _%>
```

tr\_get\_kyobobook\_info.js - 제 이전 글([https://eoureo.tistory.com/15](https://eoureo.tistory.com/15))의 소스 코드입니다. 파일에 메타 데이터 넣기를 하는 코드입니다.

([https://gist.github.com/eoureo/17c8bf42058408e4d1f63ae245e8da9a/raw/(2)%20tr\_get\_kyobobook\_info.js](https://gist.github.com/eoureo/17c8bf42058408e4d1f63ae245e8da9a/raw/\(2\)%20tr_get_kyobobook_info.js))

### ' > ' 카테고리의 다른 글

| [옵시디언 Dataview 결과를 마크다운 형식으로 복사하기 - 템플레이터 사용](https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-Dataview-%EA%B2%B0%EA%B3%BC%EB%A5%BC-%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4-%ED%98%95%EC%8B%9D%EC%9C%BC%EB%A1%9C-%EB%B3%B5%EC%82%AC%ED%95%98%EA%B8%B0-%ED%85%9C%ED%94%8C%EB%A0%88%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9) (5) | 2023.05.02 |
| --- | --- |
| [옵시디언 템플레이터(Templater) - Callout 넣기](https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-%ED%85%9C%ED%94%8C%EB%A0%88%EC%9D%B4%ED%84%B0-Templater-Callout-%EB%84%A3%EA%B8%B0) (6) | 2023.04.16 |
| [옵시디언 템플레이터(Templater) - 교보문고 도서 정보 가져오기(User Script Functions을 써서)](https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-Templater-%EA%B5%90%EB%B3%B4%EB%AC%B8%EA%B3%A0-%EB%8F%84%EC%84%9C-%EC%A0%95%EB%B3%B4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-User-Script-Functions) (5) | 2023.04.11 |
| [옵시디언 - 한꺼번에 여러 노트의 태그들을 바꾸기(Feat. 템플레이터 & 데이터뷰)](https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-%ED%95%9C%EA%BA%BC%EB%B2%88%EC%97%90-%EC%97%AC%EB%9F%AC-%EB%85%B8%ED%8A%B8%EC%9D%98-%ED%83%9C%EA%B7%B8%EB%93%A4%EC%9D%84-%EB%B0%94%EA%BE%B8%EA%B8%B0-Feat-%ED%85%9C%ED%94%8C%EB%A0%88%EC%9D%B4%ED%84%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B7%B0) (0) | 2023.04.05 |
| [옵시디언 템플레이터(Templater) - 교보문고 도서 정보 가져오기 (고침 @2023-04-05 20:00:00)](https://eoureo.tistory.com/entry/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-Templater-%EA%B5%90%EB%B3%B4%EB%AC%B8%EA%B3%A0-%EB%8F%84%EC%84%9C-%EC%A0%95%EB%B3%B4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0) (3) | 2023.03.22 |