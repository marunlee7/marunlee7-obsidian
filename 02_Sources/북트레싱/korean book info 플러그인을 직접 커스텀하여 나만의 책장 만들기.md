---
title: korean book info 플러그인을 직접 커스텀하여 나만의 책장 만들기
priority: "medium"
process: "raw"
source_name: korean book info 플러그인을 직접 커스텀하여 나만의 책장 만들기
source_type: " youtube"
source_author: "북트레싱"
references:
  - https://www.youtube.com/watch?v=r-DL7-egGgo&list=PL-KPFbwFiAWA3bR3QSK3w6r_XM0KRzEFl&index=17
links: 
---
# Korean Book Info 플러그인을 직접 커스텀하여 나만의 책장 만들기

![](https://www.youtube.com/watch?v=r-DL7-egGgo)  
 :: main.js 수정작업 진행했지만 몇가지 해결 못함. 
- 소스 references
- my_rate
- view-count 있을 때
- 메인 타이틀, 서브 타이틀

이번 영상에서는 웹(Yes24)에서 도서의 정보를 
옵시디언으로 손쉽게 가져올 수 있는 korean book info 플러그인의 
간단한 사용법과 플러그인을 직접 **커스텀하는 방법**에 대해 다뤄보았습니다.  

코드를 수정해야하기 때문에 어려움을 느끼시는 분들이 계신다면 
제가 공유해드리는 파일을 다운 받아서 약간의 수정만 더 하셔서 사용하시면 되겠습니다  

## 요약

📚 Korean Book Info 플러그인 소개 및 활용법
북트레싱 채널에서 **Korean Book Info 플러그인을 커스텀하여 사용하는 방법**을 소개합니다.
이 플러그인은 YES24에서 책 정보를 가져와 나만의 서재를 만들 수 있도록 도와주는 유용한 도구입니다. 

⚙️ 플러그인 설치 및 기본 설정
플러그인 설치는 옵시디언 설정에서 커뮤니티 플러그인 탐색을 통해 Korean Book Info를 검색하여 설치하고 활성화하면 됩니다. 옵션에서는 **태그 이름을 변경**하거나, 책 제목, 소개, 목차 표시 여부 등을 설정할 수 있습니다. 

🔎 책 정보 불러오기 과정
새 파일을 생성하고 책 제목을 입력한 후, 'Add book info' 아이콘을 클릭하면 책 정보를 불러올 수 있습니다. **검색 결과 최상단에 있는 책 정보가 불러와지므로**, 원하는 책이 아닐 경우 저자 이름을 함께 입력하여 검색 정확도를 높일 수 있습니다. 

✏️ 프론트매터 커스터마이징
플러그인이 가져오는 프론트매터 정보의 순서나 형식을 변경하고 싶다면, **.obsidian 폴더 내의 plugins/kr-book-info-plugin/main.js 파일을 수정**해야 합니다. 윈도우에서는 숨김 항목 표시를 활성화해야 .obsidian 폴더를 볼 수 있습니다. 

👨‍💻 ==main.js 파일 수정 방법==
main.js 파일을 텍스트 편집기(메모장, 텍스트 편집기, VS Code 등)로 열어 
frontmatter 부분을 찾습니다.
**옵시디언에서 원하는 형식으로 변경한 후**, main.js 파일에서 해당 부분을 수정하면 됩니다. 예를 들어, 태그 위치를 변경하거나, 카테고리 삭제, 날짜 형식 변경 등이 가능합니다. 
**작가의 경우 리스트 형식으로 표시하기 위해 별도의 코드가 필요**하며, 
더보기란에 링크를 통해 공유될 예정입니다. 
수정 후에는 옵시디언을 재시작해야 변경 사항이 적용됩니다. 
**만약 문제가 발생하면 플러그인을 삭제 후 재설치**하는 것을 권장합니다. 

⚠️ 추가 팁 및 주의사항
main.js 파일 수정 시 콜론(:)을 기준으로 **왼쪽 부분만 변경하는 것을 추천**합니다. 프론트매터를 추가할 때는 콤마(,)를 잊지 않도록 주의해야 합니다. 수정된 main.js 파일은 공유될 예정이며, **.obsidian/plugins/kr-book-info-plugin 폴더에 덮어쓰기**하여 사용할 수 있습니다. 파일을 덮어쓴 후에는 반드시 옵시디언을 재시작해야 합니다. 


## 思索 🙇🏻

### Korean Book Info 추가 수정 삭제 항목

원본
```
created: 2022-04-00 00:00
tag: 📚독서 국내도서 경제경영 경제 경제상식/경제이야기
title: 부의 추월차선：부자들이 말해 주지 않는 진정한 부를 얻는 방법
author: 엠제이 드마코, 신소영
category: 경제경영
total_page: 392
published: 2022-02-00
cover_url: http://image.yes24.com/goods/106369008/XL
status: 🟩 완료
start_read_date: 2022-04-00
finish_read_date: 2022-04-00
my_rate: 0
book_note: ❌
```

