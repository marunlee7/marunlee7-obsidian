---
published: 2022-03-30T20:41:10+09:00
aliases: []
source_name: Digital Garden 플러그인 나만의 디지털 가든 만들기
references: https://anpigon.tistory.com/164
---
# Digital Garden 플러그인 나만의 디지털 가든 만들기

**목차**

> 옵시디언 노트를 무료로 퍼블리싱하는 방법에 대해 최근(2024년 1월 28일)에 새로 작성한 글이 있습니다.  
> 해당 글은 바로 아래 링크에서 확인하실 수 있습니다.

[

GitHub와 Cloudflare를 이용하여 Obsidian 노트를 온라인에 게시하는 방법 (with Quartz)

준비하기 GitHub 계정이 필요합니다. GitHub 계정이 없다면 여기에서 계정을 생성할 수 있습니다. Cloudflare 계정 또한 필요합니다. Cloudflare 계정이 없다면 여기 에서 계정을 생성할 수 있습니다. GitHub

anpigon.tistory.com

](https://anpigon.tistory.com/449)

---

## Github과 Netlify 셋팅하기

[GitHub](https://github.com/)  계정과  [Netlify](https://app.netlify.com/) 계정이 필요합니다.  
Netlify는 Github 계정을 사용하여 가입할 수 있습니다.  
옵시디언에서 Digital Garden 플러그인 검색하고 설치합니다.

![etc-image-0](https://blog.kakaocdn.net/dn/b3hqIJ/btrx2eLgq0a/5kxjKA0xFUCa9jp9uMZbMK/img.png)

etc-image-0

그리고 Digital Garden Settings으로 이동합니다.

![etc-image-1](https://blog.kakaocdn.net/dn/lyNRI/btrxVEyby16/zrgCyWOYT2ESAQi801XKWK/img.png)

etc-image-1

- Github repo name에 방금 생성한 리포지토리 이름(예. digitalgarden)을 입력합니다.
- Github Username에 깃헙 유저 이름을 입력합니다.
- GitHub token에는 깃헙 액세스 토큰을 입력합니다. 깃헙 액세스 토큰을 발급 받는 방법은 아래에서 다시 설명합니다.

## 깃헙 엑세스 토큰 발급하기

아래 URL에 접속하여 Github personal access token을 발급합니다.  
[https://github.com/settings/tokens](https://github.com/settings/tokens)  
Expiration는 No expiration를 선택하고, Select scopes에서 repo를 선택해주세요.

![etc-image-2](https://blog.kakaocdn.net/dn/cYJhPW/btrxY3YX2rS/liLKOqC02rkhkIrdfKhdk0/img.png)

etc-image-2

  
발급 받은 깃헙 액세스 토큰을 토큰을 복사하여, Digital Garden Settings를 다시 열고 토큰을 붙여넣습니다.  

## 메모 작성하고 발행하기

옵시디언에서 새 메모를 작성하고, 맨 위에 다음 프론트 매터를 추가합니다.

```yaml
---
dg-home: true
dg-publish: true
---
```
- dg-home: 이것은 홈페이지 또는 디지털 가든의 항목이라는 것을 플러그인에 알려줍니다. (하나의 메모에만 사용합니다)
- dg-publish: 이 메모를 디지털 가든에 업르드해야 한다고 플러그인에 알려줍니다. 이 설정이 없는 메모는 업로드되지 않습니다.  
	![etc-image-3](https://blog.kakaocdn.net/dn/wOd15/btrxZGaV9FI/TQ724BIekKRGLcC4nFcNS0/img.png)
	etc-image-3
	  
	  
	이제 마지막으로 명령어 창을 열고Publish Single Note명령어를 선택합니다.  
	![etc-image-4](https://blog.kakaocdn.net/dn/cvfPFg/btrxVEE1BQu/5Emhjq6APvCB3AWyvZG2tK/img.png)
	etc-image-4

  
축하합니다. 이제 무료로 호스팅되는 나만의 디지털 가든이 생겼습니다!  
옵시디언에서 평소처럼 링크를 추가할 수 있습니다. 이중 대괄호는 \[\[Some Other Note\]\]와 같이 방금 게시한 메모에 추가할 수 있습니다. \[\[Some Other Note#A Header\]\] 구문을 사용하여 특정 헤더에 연결할 수도 있습니다. 링크된 메모는 자동으로 업로드 되지 않으므로 링크하는 메모는 직접 업로드 해야합니다. 링크된 메모를 업로드하지 않은 경우에는, 이 메모가 존재하지 않는다고 알리는 페이지로 연결됩니다.  
템플릿을 업데이트 하고 싶으면 src/site/styles/custom-style.scss 파일을 수정하면 됩니다.

### ' > ' 카테고리의 다른 글

| [GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167) (5) | 2022.04.24 |
| --- | --- |
| [옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)](https://anpigon.tistory.com/165) (8) | 2022.04.07 |
| [Shell commands 플러그인을 사용하여 git 동기화하기](https://anpigon.tistory.com/159) (0) | 2022.03.13 |
| [옵시디언(Obsidian) 플러그인 개발 시작하기](https://anpigon.tistory.com/158) (0) | 2022.03.13 |
| [옵시디언 스팀잇 플러그인 개발](https://anpigon.tistory.com/156) (4) | 2022.03.05 |

, , , , ,

댓글 0