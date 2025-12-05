---
title: 옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!
aliases: []
published: 2024-01-19T10:21:30+09:00
status: planned
priority: medium
process: raw
source_name: 옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/446
---
# 옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!

옵시디언 노트 앱을 사용하면서 Google Tasks를 효과적으로 관리하고 싶으신가요? 옵시디언 Google Tasks 플러그인을 사용하면 옵시디언 내에서 직접 할 일 목록을 관리할 수 있어 생산성을 높일 수 있습니다. 이 글에서는 플러그인 설치부터 사용 방법까지 상세히 안내해드립니다.

- 🌐 **홈페이지**: [https://github.com/YukiGasai/obsidian-google-tasks](https://github.com/YukiGasai/obsidian-google-tasks)
- 📥 **설치링크**: [https://obsidian.md/plugins?id=obsidian-google-tasks](https://obsidian.md/plugins?id=obsidian-google-tasks)

**옵시디언 Google Tasks 플러그인의 주요 기능:**

- 태스크 목록 조회
- 새 태스크 생성
- 태스크 편집(새 태스크을 생성하고 이전 태스크을 삭제)
- 태스크 완료/할 일로 표시
- 완료된 태스크 삭제

## Google Tasks 플러그인 설치 및 설정 방법

옵시디언 Google Tasks 플러그인을 설치하고 나서 옵시디언을 재시작해야합니다.

### 1\. Google Cloud 프로젝트 생성

먼저 [Google Cloud](https://console.cloud.google.com/projectcreate) 에 접속하여 새로운 프로젝트를 생성합니다. 간단한 프로젝트 명을 설정하고 “만들기” 버튼을 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/bGGAdb/btsEGkkYJKd/oVOhQskMjNE41WqhORKXQ1/img.png)

### 2\. Google Tasks API 활성화

Google Cloud 마켓플레이스에서 [Google Tasks API](https://console.cloud.google.com/marketplace/product/google/tasks.googleapis.com?q=search&referrer=search&project=) 페이지로 이동하여 ‘사용’ 버튼을 클릭해 Google Tasks API를 활성화합니다.

![blob](https://blog.kakaocdn.net/dn/b9ubjA/btsEFfR4wNX/Tcjgb85wACUpNwmduENaZ0/img.png)

### 3\. OAuth 동의 화면 설정

[OAuth 동의 화면](https://console.cloud.google.com/apis/credentials/consent?project=) 을 설정합니다. User Type 사용자 유형을 외부 앱으로 등록 후 필요한 정보를 입력하고 “만들기” 버튼을 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/veHwr/btsEGQjDuNz/1JQ4otK6kC10ucNw3pcmx0/img.png)

그 다음 화면에서 필요한 정보를 입력하고 “저장 후 계속” 버튼을 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/BWZor/btsEGQqnrer/EzrEN3ZJVa8kMOqajIYgT1/img.png)

그 다음 화면에서 테스트 사용자를 추가하고 “저장 후 계속” 버튼을 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/lm4fJ/btsEEWLZyvV/Gb6K7vTHa479J7Ji9lyFVK/img.png)

### 4\. API 액세스 토큰 생성

다시 사용자 인증 정보 화면으로 돌아와서, “+ 사용자 인증 정보 만들기” 링크를 클릭하고, "OAuth 클라이언트 ID OAuth 클라이언트 ID"를 클릭합니다.

![blob](https://blog.kakaocdn.net/dn/bNDt4h/btsEFgQ3any/a2k6Brh4HHds8dzKNrmTI0/img.png)

애플리케이션 유형을 '웹 애플리케이션’으로 선택하고, "승인된 자바스크립트 원본"에 `http://127.0.0.1:42813` 를 "승인된 리디렉션 URI"에는 `http://127.0.0.1:42813/callback` 를 추가합니다.

![blob](https://blog.kakaocdn.net/dn/bOTiXT/btsEExy9xxy/yjsbFOK9U5fTkXKbY0CE80/img.png)

![blob](https://blog.kakaocdn.net/dn/y0AgS/btsEEFwZq6A/cikFGqHdpc6B0a6JgwjWkK/img.png)

이렇게 생성한 클라이언트ID(CliendId)와 클라이언트 보안 비밀번호(ClientSecret)를 옵시디언 Google Tasks 플러그인 설정에 입력하고 로그인합니다.

![blob](https://blog.kakaocdn.net/dn/LSfUW/btsEFdUehqE/CB632I5i3hpqTQjzcZSvK1/img.png)

혹시 로그인 중에 보안 경고가 나타날 경우, '계속’을 클릭하여 진행하시면 됩니다.

![blob](https://blog.kakaocdn.net/dn/n7OcT/btsEINtfL6B/ZnLX3FOeAkMrFCUFjI5tZK/img.png)

### 모바일에서 플러그인 사용하기

데스크탑에서 Google Refresh Token을 복사합니다.

![blob](https://blog.kakaocdn.net/dn/kApdn/btsEHJkdO07/deyudi8RgPloNriipUjaV1/img.png)

모바일에서 플러그인을 설치한 후, ‘로그인’ 대신 복사한 토큰을 ‘Refresh token’ 필드에 붙여넣습니다.

![blob](https://blog.kakaocdn.net/dn/FRiil/btsEEV0C3H5/pLZxuWZmPP0z2qoWVh76y1/img.png)

## 사용 방법

### Google Task View

왼쪽 사이드바에서 체크마크 아이콘을 클릭하여 뷰를 엽니다.

![blob](https://blog.kakaocdn.net/dn/oAimI/btsEELqkVxj/Zd2q0S9gi0T6HgwcSHkRJK/img.png)

왼쪽 사이드에 할 일 목록이 표시되며, 각 작업을 완료하거나 편집할 수 있습니다.

![blob](https://blog.kakaocdn.net/dn/bk4Gct/btsEFSIYroH/unK9FaMyRwUwSvd10uoxr0/img.png)

태스크 목록은 60초마다 자동으로 업데이트됩니다.

새로운 태스크를 만들기 위해서는 플러스 버튼을 사용하세요.

### 명령어

- **List Google Tasks**: 미완료 태스크 목록을 보여주고, 선택하여 완료할 수 있습니다.
- **Create Google Tasks**: 새로운 태스크를 만드는 팝업을 엽니다.
- **Insert Google Tasks**: 현재 파일에 미완료 태스크 목록을 삽입합니다. 파일 내에서 태스크를 체크하면 완료/미완료 상태로 전환할 수 있습니다.

## 마치며

옵시디언 Google Tasks 플러그인을 활용하여 생산성을 극대화하세요. 설치부터 사용까지, 단계별로 안내해드린 이 글이 여러분의 워크플로우 개선에 도움이 되길 바랍니다.

---

[![etc-image-14](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*

[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

### ' > ' 카테고리의 다른 글

| [옵시디언 Flowershow 플러그인으로 무료 퍼블리시 방법](https://anpigon.tistory.com/448) (2) | 2024.01.27 |
| --- | --- |
| [옵시디언 무료 퍼블리시 서버 비용 비교](https://anpigon.tistory.com/447) (0) | 2024.01.27 |
| [무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)](https://anpigon.tistory.com/442) (0) | 2024.01.14 |
| [무료 AI 올라마를 옵시디언에서 효과적으로 활용하는 방법(feat. Text Generator, BMO Chatbot)](https://anpigon.tistory.com/441) (0) | 2024.01.12 |
| [옵시디언 노트앱을 활용한 스팀 코인 수익 자동 기록 방법](https://anpigon.tistory.com/438) (0) | 2024.01.08 |

, ,

댓글 0