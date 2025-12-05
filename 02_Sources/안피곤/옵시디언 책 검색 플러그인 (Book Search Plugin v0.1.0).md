---
title: 옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)
aliases: []
published: 2022-04-07T21:54:06+09:00
status: planned
priority: medium
process: raw
source_name: 옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/165
---
# 옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)

**목차**

옵시디언에서 책을 검색하여 독서 노트를 빠르게 생성할 수 있는 플러그인입니다.

![etc-image-0](https://blog.kakaocdn.net/dn/bg9Fqp/btryG9kdjJn/0uiNp4ZU9t7pbslhbQvvA0/img.gif)

etc-image-0

  
독서 노트 템플릿은 Obsidianary님의 [옵시디언 독서노트 템플릿](https://olait.tistory.com/31) 을 참고했습니다.  
플러그인은 아직 개발 중입니다. 하지만 지금도 충분히 사용가능하다고 생각합니다.

책 정보 검색은 API\_KEY가 필요없는 Google Books API를 사용했습니다.  
하지만 사용해보니 Google Books API가 국내 책 검색에는 데이터가 충분하지 않은 것 같아요.

나중에 시간이 된다면 네이버, 카카오, 알라딘 등 국내 책 검색 Open API도 사용해볼 예정입니다.

## 플러그인 설치 방법

~~아직 옵시디언 커뮤니티 플러그인으로 등록하지 않았습니다. 그래서 [릴리즈 페이지](https://github.com/anpigon/obsidian-book-search-plugin/releases) 에서 zip 파일을 다운로드 받아서 볼트의.obsidian/plugins/ 폴더에 압축을 해제하여 수동 설치해야 합니다.  
~~플러그인 심사가 통과 되어서 옵시디언 커뮤니티 플러그인에 등록되었습니다. (2022-04-19)  
옵시디언 커뮤니티 플러그인에서 검색하여 설치합니다.

![etc-image-1](https://blog.kakaocdn.net/dn/YN7pJ/btrAQRAUSTH/G2GpiZ7ksGO96enzExUXl0/img.png)

etc-image-1

## 사용 방법

1. 서드파티 플러그인(Community plugins)에서 Book Search 플러그인을 활성화 해주세요.![etc-image-2](https://blog.kakaocdn.net/dn/Lko8T/btryIrrbae5/pbWhFOMRPGHJfkmNWi5QC1/img.png)
	etc-image-2
2. 그 다음 Book Search Settngs에서 새 노트를 생성할 폴더를 설정합니다.![etc-image-3](https://blog.kakaocdn.net/dn/m5kb1/btryKv0b3IJ/3gB0uFvUSeruXpeVLpH1z0/img.png)
	etc-image-3
3. 왼쪽 사이드 리본바에서 책 아이콘을 클릭하세요.![etc-image-4](https://blog.kakaocdn.net/dn/nvmVi/btryFNHLZri/YiZ5mIATK1j96YHmZPlINk/img.png)
	etc-image-4
4. 책 제목, 저자, 출판사 또는 ISBN으로 검색합니다.![etc-image-5](https://blog.kakaocdn.net/dn/vwsSZ/btryKvTpU0h/oesVyXQpYWvkkDv5DTCH00/img.png)
	etc-image-5
5. 검색된 결과에서 선택합니다.![etc-image-6](https://blog.kakaocdn.net/dn/4t2tw/btryHKKKMaG/eBFNxYWjlF3VBD7HnOyr7K/img.png)
	etc-image-6
6. 짠~! 새로운 노트가 생성되었습니다.![etc-image-7](https://blog.kakaocdn.net/dn/bGjqLq/btryKQQtVeI/4uVvPvUjjmpzHMzCKbLTw1/img.png)
	etc-image-7

  
  
저는 옵시디언에서 노션 환경과 비슷하게 만들어서 사용하고 있습니다.  
데이터 뷰를 활용하면 아래와 같은 화면은 물론 독서 통계 페이지를 만들 수 있어요.

![etc-image-8](https://blog.kakaocdn.net/dn/cgFm78/btryJB0Apco/BBykrOq65fUViihKwJCbNk/img.png)

etc-image-8

### ' > ' 카테고리의 다른 글

| [유튜브 노트 빠르게 생성하기 (with QuickAdd 플러그인)](https://anpigon.tistory.com/176) (0) | 2022.07.26 |
| --- | --- |
| [GitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167) (5) | 2022.04.24 |
| [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164) (0) | 2022.03.30 |
| [Shell commands 플러그인을 사용하여 git 동기화하기](https://anpigon.tistory.com/159) (0) | 2022.03.13 |
| [옵시디언(Obsidian) 플러그인 개발 시작하기](https://anpigon.tistory.com/158) (0) | 2022.03.13 |

, ,

댓글 8

- 김정현
	정말 너무 잘 쓰고 있습니다. 안피곤님 플러그인을 사용하기 위해 옵시디언을 설치했습니다. 정말 고맙습니다.  
	그런데 책 제목에:가 들어간 경우 등록이 되지 않는 경우가 발생합니다. 혹시 수정해주실 수 있을까요?  
	예를 들어 재레드 다이아몬드의 <대변동: 위기, 선택, 변화>의 경우 검색은 되지만 등록은 안됩니다.
	2022\. 7. 18. 14:06 [답글](https://anpigon.tistory.com/#)
	- [수정](https://anpigon.tistory.com/#)
	- [삭제](https://anpigon.tistory.com/#)
	- [신고](https://anpigon.tistory.com/#)
	- [링크복사](https://anpigon.tistory.com/#)
- - [안피곤](https://anpigon.tistory.com/)
		제 블로그에 방문해주셔서 정말로 감사드립니다! 제가 만든 플러그인에 이렇게 관심을 가져주시고, 독서 정리에 도움이 된다니 정말 기쁘네요. 😊  
		  
		현재 이 플러그인은 저 혼자서 개발하고 유지하고 있기 때문에, 자원과 시간이 한정되어 있습니다. 그럼에도 불구하고, 사용자의 소중한 피드백은 플러그인 개선에 큰 도움이 됩니다.  
		  
		geonjunzi님이 제안해주신 알라딘 연동에 대해서는 진지하게 고려해보겠습니다. 이와 관련하여 구체적인 계획이 수립되면, 블로그를 통해 새로운 소식으로 알려드릴게요.
		2024\. 2. 12. 20:44 [답글](https://anpigon.tistory.com/#)
		- [신고](https://anpigon.tistory.com/#)
		- [링크복사](https://anpigon.tistory.com/#)