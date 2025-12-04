---
published: 2022-09-15T21:34:10+09:00
aliases: []
source_name: 목소리로 간편하게 옵시디언 메모하기 with Tasker
references: https://anpigon.tistory.com/189
---
# 목소리로 간편하게 옵시디언 메모하기 with Tasker

유튜브 영상 " [아이폰 꺼내서 목소리로 옵시디안에 바로 빠르게 메모하기](https://youtu.be/lKO_BBM_fbA) "를 보면 아이폰에서 목소리를 사용하여 텍스트 메모하는 방법을 가이드하고 있습니다.

안드로이드에서 할 수 있는 방법이 없나 찾아보다가 [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=ko) 로 가능하다는 것을 알게 되었습니다.

![|300](https://i.imgur.com/dADTkEE.gif)

## Tasker 설정 파일 Import 하기

제가 만든 설정을 [Taskernet](https://taskernet.com/shares/?user=AS35m8m49N4GZI6FSDL6K%2Fh8kyVIjYDxgNKqXvKCPqXoQqCdEQkBh2VwktM8GXhL1TD6&id=Project%3Aobsidian#) 에 업로드 했습니다. 이 페이지에서 Import 버튼을 눌러 Tasker 앱으로 import 합니다. 만약 자동으로 Import 가 안된다면 Download XML File 링크를 클릭하여 다운로드 받은 XML 파일을 앱에서 직접 Import 하면 됩니다.

![|250](https://steemitimages.com/350x0/https://i.imgur.com/CpkHoCd.png)

## Tasker 설정 수정하기

"3. Write File"에서 File에는 본인의 파일 경로에 맞게 변경합니다. 그리고 Text에는 자동 메모 형식을 입력합니다. Text에 입력되어 있는 형식을 수정하지 않고 그대로 사용하면 `- 22.09.14 16:15:52: 메모` 형식으로 기록됩니다. 알맞게 수정하여 사용하시기 바랍니다.

| ![etc-image-2](https://steemitimages.com/300x0/https://i.imgur.com/rFKLwor.jpg) | ![etc-image-3](https://steemitimages.com/300x0/https://i.imgur.com/QurFEcO.jpg) |
| --- | --- |

## 홈화면에 위젯 사용하기

홈화면 위젯에서 Task Shortcut를 찾아서 선택합니다.  
그리고 Task Selection 에서 speech to text를 선택합니다.

| ![etc-image-4](https://steemitimages.com/250x0/https://i.imgur.com/Dv5o2pq.jpg) | ![etc-image-5](https://steemitimages.com/250x0/https://i.imgur.com/UXIyDb0.jpg) |
| --- | --- |

홈화면에 다음과 같이 위젯이 생성되었습니다.  
이제 이 위젯을 누르면 음성으로 메모가 가능합니다.

![|300](https://steemitimages.com/300x0/https://i.imgur.com/YtepJlM.jpg)

## Task를 앱으로 만들기

Task를 앱으로 만들어 두면 조금 더 편하기 사용할 수 있습니다.  
앱을 만들기 위해서는 [Tasker App Factory](https://play.google.com/store/apps/details?id=net.dinglisch.android.appfactory&hl=ko) 가 추가로 필요합니다.

다음 절차를 따라 수행합니다.

1. 맨 하단 가운데 "정사각형 아이콘 버튼"을 클릭합니다.  
	그리고 아이콘을 선택합니다. 저는 “Application Icon” 중에서 적당한 아이콘을 사용했습니다.  
	![|300](https://steemitimages.com/300x0/https://i.imgur.com/3p19Xz8.jpg)
2. 그다음 Tasks에서 "speech to text"를 선택하고,  
	우측상단의 "케밥 메뉴 아이콘"을 누릅니다. 그리고 "As App"을 선택합니다.  
	![|300](https://steemitimages.com/300x0/https://i.imgur.com/Gngjxbe.jpg)
3. 마지막으로 Package를 작성하고,  
	뒤로가기를 선택하면 앱이 생성/설치됩니다.

![|300](https://steemitimages.com/300x0/https://i.imgur.com/WIQnFV3.jpg)

※ 만약 Tasker로 만든 앱이 잘 동작하지 않는다면 **앱 권한을 확인** 해보세요.  
마이크와 저장공간 권한이 모두 켜져 있어야 합니다.

![|300](https://steemitimages.com/300x0/https://i.imgur.com/iUnxp0H.jpg)

END.

### ' > ' 카테고리의 다른 글

| [옵시디언 티스토리 플러그인(마크다운 에디터)](https://anpigon.tistory.com/214) (23) | 2022.11.24 |
| --- | --- |
| [옵시디언에서 무료로 발행(Publish)하는 방법](https://anpigon.tistory.com/203) (0) | 2022.09.21 |
| [네이버 책 검색 API를 사용하여 독서노트 생성하기](https://anpigon.tistory.com/177) (0) | 2022.08.26 |
| [유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)](https://anpigon.tistory.com/176) (0) | 2022.07.26 |
| [GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167) (5) | 2022.04.24 |

,

댓글 0