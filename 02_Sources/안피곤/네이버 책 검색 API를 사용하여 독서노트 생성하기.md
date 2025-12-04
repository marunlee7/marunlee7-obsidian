---
published: 2022-08-26T00:42:44+09:00
aliases: []
source_name: 네이버 책 검색 API를 사용하여 독서노트 생성하기
references: https://anpigon.tistory.com/177
---
# 네이버 책 검색 API를 사용하여 독서노트 생성하기

![etc-image-0](https://blog.kakaocdn.net/dn/bCbmyh/btr4hzcXhU3/OyXaJIf57bE1INAljOW021/img.png)

etc-image-0

## Book Search 플러그인

[옵시디언 Book Search 플러그인](https://github.com/anpigon/obsidian-book-search-plugin) 이 필요합니다. "커뮤니티 플러그인"에서 검색하거나 아래 링크를 클릭하여 설치할 수 있습니다.

- [옵시디언 책 검색 플러그인 설치 링크](https://anpigon.github.io/obsidian-book-search-plugin/install.html)

## 플러그인 설정하기

### New File Location

새로운 노트 파일이 생성되는 폴더 위치입니다.

### New File name

파일이 생성되는 파일 이름 규칙입니다. 입력하지 않으면 기본적으로{{title}} - {{author}}포맷이 적용되어제목 - 저자.md이름으로 파일이 생성됩니다.

### Template File

노트를 생성할 때 사용하는 템플릿 파일입니다. 샘플 템플릿 파일은 [여기](https://github.com/anpigon/obsidian-book-search-plugin#example-template) 에서 참고할 수 있습니다.

### Service Provider

책 검색에 사용할 서비스입니다. 드롭박스를 클릭하여 **Naver (Korean)를** 선택합니다.

![etc-image-1](https://blog.kakaocdn.net/dn/JKic2/btrKA35z3DK/XONWMxmqINLBMMSEyfGBj0/img.png)

etc-image-1

그다음 ⚙️기어 아이콘을 클릭하여 **Service Provider Setting에** 들어갑니다.  
Client ID와Client Secret에는 네이버 개발자 센터에서 발급받은 ID와 Secret 값을 입력합니다.  
그리고 **Save** 버튼을 눌러서 저장합니다.  
네이버 개발자 센터에서 키 발급받는 방법은 아래에서 다시 설명하겠습니다.

![etc-image-2](https://blog.kakaocdn.net/dn/xh2fg/btrKBsjTnf6/CaOk4hY1zC5ZHfdkjasyL0/img.png)

etc-image-2

## 네이버 개발자 센터에서 키 발급 받는 방법

[네이버 책 검색 API 페이지](https://developers.naver.com/docs/serviceapi/search/book/book.md) 에서 [오픈 API 이용 신청 >](https://developers.naver.com/apps/#/register?defaultScope=search) 버튼을 클릭합니다.

![etc-image-3](https://blog.kakaocdn.net/dn/b8kgDi/btrKBGI4xzc/JbMrhH0MvDJ685iRaSPF01/img.png)

etc-image-3

"애플리케이션 등록 (API 이용신청)"에서 키를 발급받기 위한 앱 정보를 입력합니다.

![etc-image-4](https://blog.kakaocdn.net/dn/cQqT71/btrKze1ydZb/QSEOeIzopcCrq89o4OjF5K/img.png)

etc-image-4

그다음 **등록하기** 버튼을 누르면 아래와 같이Client ID와Client Secret을 확인할 수 있습니다.

![etc-image-5](https://blog.kakaocdn.net/dn/7iD7C/btrKzOOQsne/i10k1ugcTV9w76CVF0Phu1/img.png)

etc-image-5

### ' > ' 카테고리의 다른 글

| [옵시디언에서 무료로 발행(Publish)하는 방법](https://anpigon.tistory.com/203) (0) | 2022.09.21 |
| --- | --- |
| [목소리로 간편하게 옵시디언 메모하기 with Tasker](https://anpigon.tistory.com/189) (0) | 2022.09.15 |
| [유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)](https://anpigon.tistory.com/176) (0) | 2022.07.26 |
| [GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167) (5) | 2022.04.24 |
| [옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)](https://anpigon.tistory.com/165) (8) | 2022.04.07 |

댓글 0