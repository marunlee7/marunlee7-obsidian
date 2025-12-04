---
published: 2022-04-24T22:06:15+09:00
aliases: []
source_name: GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)
references: https://anpigon.tistory.com/167
---
# GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)

> 옵시디언 노트를 무료로 퍼블리싱하는 방법에 대해 최근(2024년 1월 28일)에 새로 작성한 글이 있습니다.  
> 해당 글은 바로 아래 링크에서 확인하실 수 있습니다.

[

GitHub와 Cloudflare를 이용하여 Obsidian 노트를 온라인에 게시하는 방법 (with Quartz)

준비하기 GitHub 계정이 필요합니다. GitHub 계정이 없다면 여기에서 계정을 생성할 수 있습니다. Cloudflare 계정 또한 필요합니다. Cloudflare 계정이 없다면 여기 에서 계정을 생성할 수 있습니다. GitHub

anpigon.tistory.com

](https://anpigon.tistory.com/449)

---

  
최근에 gatsby로 만들어진 블로그를 검색하다가 마음에 드는 템플릿을 발견하였습니다.  
바로 [gatsby-starter-digital-garden](https://github.com/mathieudutour/gatsby-starter-digital-garden) 입니다.

- 템플릿 적용된 사이트: [https://mathieudutour.github.io/gatsby-digital-garden/](https://mathieudutour.github.io/gatsby-digital-garden/)

" [옵시디언 무료 퍼블리시하기: 나만의 디지털 가든 만들기](https://steemit.com/hive-101145/@anpigon/20220330t113002362z) "에서 옵시디언 디지털 가든 플러그인을 소개한 적이 있습니다. 이전 글에서 설명했듯이 옵시디언 Digital Garden 플러그인을 사용하면 GitHub에 글을 쉽게 업로드 할 수 있습니다.  
  
이번에는 옵시디언 플러그인과 위 템플릿을 사용하여 개인 블로그를 만드는 방법을 설명합니다.

## 시작하기

### Github에 리포지토리 생성하기

1. 아래 Github URL에 접속합니다.
	- [https://github.com/anpigon/gatsby-starter-digital-garden-template](https://github.com/anpigon/gatsby-starter-digital-garden-template)
		- 이 리포는 Obsidian Digital Garden Plugin에서 사용할 수 있게 코드를 조금 수정하였습니다.
2. \[Use this template\] 버튼을 클릭합니다.![etc-image-0](https://blog.kakaocdn.net/dn/bLRgUU/btrAdIdqvBi/mXOKCufd3VAmcMZs0nOdqK/img.png)
	etc-image-0
3. Repository name를 수정하고, \[Create repositiry from template\] 버튼을 누릅니다.![etc-image-1](https://blog.kakaocdn.net/dn/d9qN7u/btrAj2Psf4m/vJbUYu0BgPyhfckk2zC4k0/img.png)
	etc-image-1

### 폴더 구조

gatsby-starter-digital-garden은 아래와 같은 폴더 구조를 가집니다. (중요하지 않은 파일은 설명에서 제외했습니다.)

```
gatsby-starter-digital-garden
├── src 
│   └── site
│       └── notes
│           ├── example-dir
│           │   └── hi.mdx
│           └── hello.mdx
└── gatsby-config.js
```
- **/src/site/notes**: 해당 폴더에는 샘플 메모가 포함되어 있습니다. 샘플 메모를 삭제하시고 자신의 메모를 작성합니다.
- **gatsby-config.js**: 설정 파일입니다. 사이트 제목 및 설명, Gatsby 플러그인 등과 같은 사이트(메타데이터)에 대한 정보를 설정할 수 있습니다.

### 개츠비 설정하기

gatsby-config.js 파일에서 rootNote와 title를 수정합니다.

```
module.exports = {
  plugins: [
    {
      resolve: \`gatsby-theme-garden\`,
      options: {
        contentPath: \`${__dirname}/src/site/notes\`,
        rootNote: \`/home\`, // 웹사이트에서 첫번째로 보여지는 메모 파일 경로입니다.
      },
    },
    \`gatsby-plugin-netlify\`
  ],
  siteMetadata: {
    title: \`Site title\`, // 여기에 사이트 명을 입력합니다.
  },
}
```

### Netlify 사이트 만들기

1. [https://app.netlify.com/](https://app.netlify.com/) 에 접속합니다.
2. \[Add new site\] → \[Import an exising project\] 버튼을 차례로 선택합니다.![etc-image-2](https://blog.kakaocdn.net/dn/zuRlJ/btrAgpkYUZc/6p778LgSuWrP1L2NSMNur0/img.png)
	etc-image-2
3. 방금 Github에 생성한 리포지토리를 검색하고 선택합니다.![etc-image-3](https://blog.kakaocdn.net/dn/Dx3rj/btrAj2hEanb/ve0F1UNkGLhYK3iX553i5k/img.png)
	etc-image-3
4. \[Deploy site\] 버튼을 선택합니다.![etc-image-4](https://blog.kakaocdn.net/dn/bDtXSM/btrAj1C1USF/XMRdFRH7RUneKqrNd4byLK/img.png)
	etc-image-4
5. \[Domain settings\]에서 site name을 변경하거나 custom domain를 설정할 수 있습니다.![etc-image-5](https://blog.kakaocdn.net/dn/FZ5qZ/btrAeQcg4MU/hmyuIglIOd10jy13nJPm9k/img.png)
	etc-image-5
	- site name에 site-name를 입력하면, 사이트 URL은 [https://site-name.netlify.app](https://site-name.netlify.app/) 가 됩니다.

## 옵시디언 디지털 가든 플러그인으로 퍼블리시하기

### Digital Garden 플러그인 설치하기

1. 옵시디언에서 Digital Garden 플러그인을 검색하고 설치합니다.![etc-image-6](https://blog.kakaocdn.net/dn/dazxkY/btrAlg779Cc/3F9YpUj2o3PEC8pb7ip4w0/img.png)
	etc-image-6
2. 그 다음 Digital Garden Settings으로 이동합니다.![etc-image-7](https://blog.kakaocdn.net/dn/meB4o/btrAj2Psf14/FltCx01LpQKlFThcyqcQf0/img.png)
	etc-image-7
	- Github repo name에 방금 생성한 리포지토리 이름(예.digitalgarden)을 입력합니다.
	- Github Username에 깃헙 유저 이름을 입력합니다.
	- GitHub token에는 깃헙 액세스 토큰을 입력합니다. 깃헙 액세스 토큰을 발급 받는 방법은 아래에서 다시 설명합니다.

### 깃헙 엑세스 토큰 발급하기

1. 아래 URL에 접속하여 Github personal access token을 발급합니다.
	- [https://github.com/settings/tokens](https://github.com/settings/tokens)
2. Expiration는No expiration를 선택합니다.Select scopes에서repo를 선택합니다.![etc-image-8](https://blog.kakaocdn.net/dn/cLoqBT/btrAczBxMBy/8Im5UwuGkhoxO5bGSV6mwK/img.png)
	etc-image-8
3. 발급 받은 깃헙 액세스 토큰을 Digital Garden Settings에 복사&붙여넣기합니다.

### 메모 작성하고 발행하기

옵시디언에서 새 메모를 작성하고, 맨 위에 다음 프론트 매터를 추가합니다. dg-publish가 true인 메모만 GitHub에 업로드 됩니다.

```yaml
---
dg-publish: true
---
```

  
그 다음 옵시디언에서 명령어 창을 열고 Publish Single Note 명령어를 선택합니다.

![etc-image-9](https://blog.kakaocdn.net/dn/bgGdQi/btrAghGnPHc/tdDsHBoKAbX9JHpMFlKU11/img.png)

etc-image-9

#### ' > ' 카테고리의 다른 글

| [네이버 책 검색 API를 사용하여 독서노트 생성하기](https://anpigon.tistory.com/177) (0) | 2022.08.26 |
| --- | --- |
| [유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)](https://anpigon.tistory.com/176) (0) | 2022.07.26 |
| [옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)](https://anpigon.tistory.com/165) (8) | 2022.04.07 |
| [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164) (0) | 2022.03.30 |
| [Shell commands 플러그인을 사용하여 git 동기화하기](https://anpigon.tistory.com/159) (0) | 2022.03.13 |

댓글 5

- [오송인](https://slowdive14.tistory.com/)
	이 템플릿 예쁘네요 감사합니다.  
	  
	안피곤님 질문이 하나 있습니다. 시간이 되시면 도움 부탁드립니다. 저는 기초적인 html 지식이나 마크다운 문법 정도만 알고 코딩은 잘 몰라서 어려움이 있네요. ^^  
	  
	mdx 파일이 아니라 Digital Garden of 잔향.md 파일을 rootNote로 할당하려면 gatsby-config.js 파일에서 /home 부분을 어떻게 수정해야 할까요?  
	  
	단순히 home을 Digital Garden of 잔향 이라고 이름만 바꾸었더니 적용이 안 되네요.  
	  
	제 깃헙의 해당 페이지 주소는 다음과 같습니다.  
	https://github.com/slowdive14/gatsby/blob/master/gatsby-config.js
	2022\. 4. 26. 11:45 [답글](https://anpigon.tistory.com/#)
	- [신고](https://anpigon.tistory.com/#)
	- [링크복사](https://anpigon.tistory.com/#)