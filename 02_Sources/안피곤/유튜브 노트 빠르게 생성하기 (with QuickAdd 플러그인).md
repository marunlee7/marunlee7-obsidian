---
published: 2022-07-26T00:07:18+09:00
aliases: []
source_name: 유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)
references: https://anpigon.tistory.com/176
---
# 유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)

![etc-image-0](https://blog.kakaocdn.net/dn/2d2At/btrIeMkpDG7/mK3NTCA7MykdSmKpB8xfv0/img.png)

etc-image-0

## 데모

![etc-image-1](https://blog.kakaocdn.net/dn/lXMj5/btrIfQ7XvIP/VVmKKmuguV2S2I6W5s5bwk/img.gif)

etc-image-1

## 설명

옵시디언의 [QuickAdd 플러그인](https://github.com/chhoumann/quickadd) 을 사용하여 유튜브 노트를 쉽게 생성할 수 있습니다. 스크립트는 chhoumann님의 [Macro\_MovieAndSeriesScript.md](https://github.com/chhoumann/quickadd/blob/master/docs/Examples/Macro_MovieAndSeriesScript.md) 를 참고하여 작성하였습니다.

**만약 스크립트를 이해할 수 없다면 절대 실행하지 마세요. 저는 이 스크립트의 사용으로 인해 발생한 피해에 대해 책임지지 않습니다. 반드시 정기적으로 옵시디언 볼트를 백업하세요.**

## 설치하는 방법

1. 최신 QuickAdd 버전(현재 0.5.5)을 사용하고 있는지 확인하세요.
2. [JS스크립트](https://gist.github.com/anpigon/35346cfcf853c0d67fb080a1da5c3d2e) 를 옵시디언 볼트 특정 폴더에 저장하세요. 확장자가.js로 끝나는 JavaScript 파일로 저장되어야 합니다.
3. 지정된 템플릿 폴더에 새 템플릿을 만듭니다. 예제 템플릿은 맨 아래에서 제공됩니다
4. QuickAdd 플러그인 설정을 열고Manage Macros버튼을 클릭하여 매크로 관리자를 엽니다.
	1. ![etc-image-2](https://blog.kakaocdn.net/dn/V3714/btrIeNcz4bw/4umGXx5YrX3kQYvkBTe931/img.png)
		etc-image-2
5. 새 매크로 만들기: 매크로 이름을 작성하고Add macro버튼을 클릭합니다. 그다음Configure버튼를 클릭하여 매크로 설정 화면으로 이동합니다.
	1. ![etc-image-3](https://blog.kakaocdn.net/dn/GNJcK/btrIdXmcwcC/8CwIZoEJozVBsSCMSuLAP1/img.png)
		etc-image-3
6. JS스크립트 파일을 선택하고Add버튼을 클릭합니다.
	1. ![etc-image-4](https://blog.kakaocdn.net/dn/bSYOSQ/btrIcIpLvFm/cC28VPkE5wTbktuab9jPkK/img.png)
		etc-image-4
7. 매크로에 새 템플릿을 추가합니다. 설정은 다음과 같습니다
	1. ![etc-image-5](https://blog.kakaocdn.net/dn/baw7c5/btrIcHK8FrG/KHNkkxE2G3pbIu2W9cOZR1/img.png)
		etc-image-5
	2. ![etc-image-6](https://blog.kakaocdn.net/dn/bmISGc/btrIc9glMmG/yyCQGuJbb8uhyelMaMuNG0/img.png)
		etc-image-6
	3. ![etc-image-7](https://blog.kakaocdn.net/dn/cMjiRU/btrH757jL1a/B6y1feUbUdaYGrEWAOpUp0/img.png)
		etc-image-7
	4. 위와 같이 스크립트와 템플릿이 설정되어야 합니다.
8. QuickAdd 설정 첫 화면으로 돌아가서 Macro 를 선택하고 새 항목을 추가합니다.
	1. ![etc-image-8](https://blog.kakaocdn.net/dn/Btmqn/btrIc8PhdOh/efZfSDYxXSWIiPSJEuXmRK/img.png)
		etc-image-8
9. 그다음 새로 만든 항목에 방금 만든 매크로를 연결합니다. ⚙톱니바퀴 아이콘을 클릭하고 매크로를 선택합니다.
	1. ![etc-image-9](https://blog.kakaocdn.net/dn/qWRvG/btrIfSSezpV/a7R6GCwLy9uTuuGoBexdj0/img.png)
		etc-image-9
	2. ![etc-image-10](https://blog.kakaocdn.net/dn/cuVpU5/btrIdYyEs8X/Btc8hgkyKKajKhdwhZha4K/img.png)
		etc-image-10

이제 매크로를 사용하면 유튜브 메타정보가 포함된 노트를 빠르게 생성할 수 있습니다!

## 예제 템플릿

아래 예제 템플릿을 수정하여 사용해도 좋습니다. 그리고 이 템플릿에 사용된 변수는 아래쪽에 정리하였습니다.

```yaml
# {{VALUE:title}}

![|500]({{VALUE:image}})

---

Title:: {{VALUE:title}}
Thumbnail:: {{VALUE:image}}
URL:: {{VALUE:url}}
ShortURL:: {{VALUE:shortUrl}}
Tags:: {{VALUE:videoTag}}
Published:: {{VALUE:datePublished}}
Genre:: {{VALUE:genre}}

---
```

## 템플릿 변수 정의

- fileName: 특수 문자를 제거한 유튜브 제목입니다. 템플릿 구성에서 파일 이름으로 사용합니다.
- title: 유튜브 제목
- videoTag: 유튜브 태그
- url: 유튜브 URL
- shortUrl: 유튜브 단축 URL
- description: 유튜브 요약 정보
- image: 유튜브 썸네일 이미지 URL
- imageHeight: 이미지 새로 사이즈
- imageWidth: 이미지 가로 사이즈
- videoHeight: 비디오 세로 사이즈
- videoWidth: 비디오 가로 사이즈
- videoUrl: 비디오 임베디드(embed) URL
- uploadDate: 비디오 업로드 날짜 (예.2022-07-25)
- datePublished: 비디오 발행 날짜 (예.2022-07-25)
- videoId: 비디오 ID
- channelId: 유튜브 채널 ID
- duration: 영상 재생 시간(예.PT14M2S, 14분2초)
- genre: 장르 (예.Education)

## 데이터 뷰 렌더링

제가 사용하고 있는 DataView 쿼리입니다. 사용하기 위해서는 [DataVIew 플러그인](https://github.com/blacksmithgu/obsidian-dataview) 이 필요합니다.

```yaml
TABLE WITHOUT ID

("[[" + file.name + "|" + Title + "]]") as 제목,
("[![coverImg|100](" + Thumbnail + ")]("+ShortURL+")") as 썸네일,
ShortURL as URL,
Published as 발행일,
Tags as 태그

from "유튜브 노트"
```

  
추가로 노션처럼 이쁘게 꾸미기 위해서 [Banner 플러그인](https://github.com/noatpad/obsidian-banners) 도 사용하고 있습니다.

### ' > ' 카테고리의 다른 글

| [목소리로 간편하게 옵시디언 메모하기 with Tasker](https://anpigon.tistory.com/189) (0) | 2022.09.15 |
| --- | --- |
| [네이버 책 검색 API를 사용하여 독서노트 생성하기](https://anpigon.tistory.com/177) (0) | 2022.08.26 |
| [GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167) (5) | 2022.04.24 |
| [옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)](https://anpigon.tistory.com/165) (8) | 2022.04.07 |
| [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164) (0) | 2022.03.30 |

댓글 0