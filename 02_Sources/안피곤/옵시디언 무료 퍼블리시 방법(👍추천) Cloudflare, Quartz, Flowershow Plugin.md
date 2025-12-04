---
published: 2024-01-28T11:55:48+09:00
aliases: []
source_name: 옵시디언 무료 퍼블리시 방법(👍추천) Cloudflare, Quartz, Flowershow Plugin
references: https://anpigon.tistory.com/449
---
# 옵시디언 무료 퍼블리시 방법(👍추천) Cloudflare, Quartz, Flowershow Plugin

## 준비하기

1. GitHub 계정이 필요합니다. GitHub 계정이 없다면 [여기](https://github.com/signup) 에서 계정을 생성할 수 있습니다.
2. Cloudflare 계정 또한 필요합니다. Cloudflare 계정이 없다면 [여기](https://dash.cloudflare.com/sign-up) 에서 계정을 생성할 수 있습니다.

## GitHub에서 새로운 Quartz 저장소 생성하기

GitHub의 [Quartz](https://github.com/jackyzha0/quartz) 페이지에 방문합니다. 그리고 ‘Use this template’ 버튼을 클릭한 다음, 'Create a new repository’를 선택합니다.

![blob](https://blog.kakaocdn.net/dn/IUmBa/btsEKFuWvks/CBDEaafEvYNLUXE8VcFzyk/img.png)

이어서 'Repository Name’을 입력하고 ‘Create Repository’ 버튼을 클릭하여 새로운 저장소를 생성합니다.

## Cloudflare에 GitHub 연결하기

[Cloudflare 대시보드](https://dash.cloudflare.com/) 에 접속해 ‘Workers 및 Pages로 응용 프로그램을 빌드’ 링크를 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/WaVBW/btsEGjM6T1e/sOTsPNAJMP4rslkf5gLHA1/img.png)

  
다음 화면에서 ‘Pages’ 탭을 선택하고, 이전에 GitHub에서 생성한 저장소를 연결합니다.

![blob](https://blog.kakaocdn.net/dn/orfpV/btsEF6mMcm2/sS10Nc9Kpfl8ZLMHotHXv0/img.png)

  
프로젝트 이름을 입력하고 (입력한 이름이 도메인명이 됩니다), 프러덕션 브랜치를 확인합니다.

![blob](https://blog.kakaocdn.net/dn/leu5X/btsELsCic15/DplEqm96sjmAFftc8HyLmk/img.png)

빌드 설정에서 '프레임워크 미리 설정’을 '없음’으로 설정하고, '빌드 명령’에는 `npx quartz build` 를 입력합니다. 그리고 '빌드 출력 디렉토리’에는 `public` 를 입력합니다.

![blob](https://blog.kakaocdn.net/dn/wuDi3/btsEGNmZWKJ/9YrsqsETkP31Wv9NCbJgsk/img.png)

## 옵시디언 노트를 웹에 게시하기

[Flowershow 플러그인](https://obsidian.md/plugins?id=flowershow) 을 사용하면 옵시디언 노트를 깃허브 저장소에 업로드 할 수 있습니다. 이를 위해 플러그인을 설치하고 Flowershow: Publish Single Note 명령을 실행합니다. 그러면 해당 노트가 깃허브 저장소에 업로드됩니다.

Flowershow 플러그인을 사용하여 노트를 업로드한 후에는 옵시디언에 추가된 리본 아이콘 🌱을 클릭하여, 업데이트된 노트를 다시 업로드하거나 삭제할 수 있습니다.

만약 노트 파일 경로가 변경되었다면, 리본 아이콘을 통해 해당 노트를 삭제한 후, 변경된 경로에 있는 노트를 다시 업로드해야 합니다.

![blob](https://blog.kakaocdn.net/dn/dZVyMU/btsEHJR54re/Wig8ucI59oVspY8aH2Zex0/img.png)

> **ℹ️ 정보**
> 
> 웹사이트에 접속했을 때 “404 Either this page is private or doesn’t exist.” 라는 메시지가 표시된다면, 이는 content 폴더 내부에 index.md 파일이 없는 것이 원인일 수 있습니다. 이 문제를 해결하기 위해서는 content 폴더 안에 index.md 파일을 생성해 주세요. 만약 방법을 모르시겠다면, [저의 블로그 깃허브 저장소](https://github.com/anpigon/anpigon-quartz/blob/v4/content/index.md) 를 참고해 주세요.

## 마치며

다음은 Quartz와 Flowershow 플러그인을 이용해 만든 제 사이트입니다: [anpigon.pages.dev](https://anpigon.pages.dev/)  
  
위 사이트는 Obsidian 노트를 기반으로 만들어졌으며, Quartz 템플릿과 Flowershow 플러그인을 활용해 Cloudflare를 통해 온라인에 게시되었습니다. 여기에는 앞으로 제가 작성한 노트를 공유할 예정입니다.  

## 관련 링크

- [옵시디언 무료 퍼블리시 서버 비용 비교 (Github Page, Vercel, Netlify, Cloudflare)](https://anpigon.tistory.com/447)

---

[![etc-image-6](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*  
[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

### ' > ' 카테고리의 다른 글

| [옵시디언 웹 스크랩핑 가이드의 모든 것](https://anpigon.tistory.com/452) (0) | 2024.02.04 |
| --- | --- |
| [티스토리 Open API 서비스 종료 대비: 새로운 블로그 연동 방안 탐색](https://anpigon.tistory.com/451) (3) | 2024.01.30 |
| [옵시디언 Flowershow 플러그인으로 무료 퍼블리시 방법](https://anpigon.tistory.com/448) (2) | 2024.01.27 |
| [옵시디언 무료 퍼블리시 서버 비용 비교](https://anpigon.tistory.com/447) (0) | 2024.01.27 |
| [옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!](https://anpigon.tistory.com/446)(0) | 2024.01.19 |

댓글 17

- [라쿠엥](https://rockuen.tistory.com/)
	안녕하세요. 제가 글을 따라 출판을 해보았는데, 깃허브에 업로드는 잘 되는데, 사이트에 들어가면,  
	막상 404  
	Either this page is private or doesn't exist.  
	라는 메시지가 뜨네요.. 혹시 왜 그런지 알수 있을까요?  
	https://sharing-note.pages.dev/ 도메인은 이 도메인으로 설정했습니다.
	2024\. 2. 1. 18:03 [답글](https://anpigon.tistory.com/#)
	- [신고](https://anpigon.tistory.com/#)
	- [링크복사](https://anpigon.tistory.com/#)
- - [안피곤](https://anpigon.tistory.com/)
		터미널에서 해당 폴더로 이동한 후, npx quartz update 명령어를 입력하세요.  
		이 명령어를 실행하려면 Node.js v20과 npm v9.3.1이 설치되어 있어야 합니다.  
		자세한 사용 방법은 Quartz 홈페이지를 참고하세요: https://quartz.jzhao.xyz
		2024\. 9. 20. 22:17 [답글](https://anpigon.tistory.com/#)
		- [신고](https://anpigon.tistory.com/#)
		- [링크복사](https://anpigon.tistory.com/#)