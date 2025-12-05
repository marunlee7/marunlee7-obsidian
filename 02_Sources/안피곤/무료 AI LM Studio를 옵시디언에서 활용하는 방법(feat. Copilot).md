---
title: 무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)
aliases: []
published: 2024-01-14T23:40:45+09:00
status: planned
priority: medium
process: raw
source_name: 무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/442
---
# 무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)

옵시디언에서 AI를 효과적으로 사용하는 방법을 찾고 계신가요?  
  
이전 글 ‘ [올라마(Ollama)와 옵시디언(옵시디언 노트앱)을 효과적으로 활용하는 방법](https://anpigon.tistory.com/441) ’ 에서는 올라마(Ollama)를 중심으로 설명했습니다. 하지만, 올라마(Ollama)는 윈도우를 지원하지 않아서 윈도우 사용자에게는 아쉬운 점이 있었습니다. 이번에는 윈도우, 맥OS, 리눅스를 모두 지원하는 LM Studio를 소개하려 합니다

## LM Studio 설치 및 AI 모델 다운로드

먼저, LM Studio 홈페이지([https://lmstudio.ai/](https://lmstudio.ai/))를 방문하여 LLM Studio 프로그램을 다운로드하여 설치합니다. 그런 다음, 왼쪽 사이드 메뉴의 🔎 아이콘을 클릭하여 'mistral’이라는 키워드로 AI 모델을 검색하고, 가장 인기 있는 모델을 선택하여 다운로드합니다.

![etc-image-0](https://i.imgur.com/rQUsGrE.png)

## AI 채팅 사용하기

AI와의 채팅 기능은 LM Studio의 핵심입니다. 왼쪽 메뉴의 💬 아이콘을 클릭하면 AI와 대화를 시작할 수 있습니다. 이 기능을 통해 다양한 질문에 대한 AI의 응답을 받아볼 수 있습니다.

![etc-image-1](https://i.imgur.com/a6IgEf1.png)

## 로컬 서버 설정

LM Studio는 로컬 서버의 API를 통해 AI와의 통신을 가능하게 합니다. 왼쪽 메뉴의 ↔️ 아이콘을 클릭하여 로컬 서버 설정 화면으로 이동합니다. 여기서 CROS 옵션을 활성화하고 “Start Server” 버튼을 클릭하여 서버를 시작합니다.

![etc-image-2](https://i.imgur.com/2hp1u4a.png)

  
아래와 같이 터미널 명령어를 사용하여 API 서버가 정상적으로 작동하는지 확인할 수 있습니다.

![etc-image-3](https://blog.kakaocdn.net/dn/lksTG/btsDrlywYCc/KlkTXV4dM9CgRiAe8ezW8k/img.png)

etc-image-3

## Obsidian Copilot 플러그인

Obsidian Copilot Plugin은 ‘ [옵시디언 코파일럿 - 옵시디언을 위한 최고의 ChatGPT 플러그인](https://anpigon.tistory.com/393) ’ 글에서 한번 소개한적이 있습니다. Copilot 플러그인을 사용하면 Obsidian 노트앱 내에서 ChatGPT 인터페이스를 통해 AI를 사용할 수 있습니다. [Copilot 플러그인](https://obsidian.md/plugins?id=copilot) 을 설치한 후, Copilot 설정에서 Default Model을 "LM STUDIO (LOCAL)"로 변경합니다. (Copilot 플러그인은 올라마(Ollama)도 사용가능합니다.)

![etc-image-4](https://i.imgur.com/Ik94pUW.png)

  
그러고나서 Copilot Settings 에서 스크롤을 아래로 내려서 LM Studio server port 가 LM Studio server 와 일치하는지 확인합니다. 기본 포트는 1234입니다.

![etc-image-5](https://i.imgur.com/ajNSfai.png)

  
이제 옵시디언 명령어 창에서 "Copilot: Toggle Copilot Chat Window"를 선택하면, 오른쪽 사이드에 Copilot 채팅창이 나타납니다.

![etc-image-6](https://blog.kakaocdn.net/dn/beaYLa/btsDrFDs7Hm/DakabnmDUZ9sBaHU3yYzPk/img.png)

etc-image-6

  
이 채팅 창을 통해 AI와 대화를 나누거나, 열려 있는 노트에 대한 질문을 할 수 있습니다.

![etc-image-7](https://i.imgur.com/1jmRRdq.png)

  
특히, 노트 작성 중 텍스트를 선택하고 “Copilot: Apply custom prompt to selection” 명령어를 사용하면, 사용자 정의 프롬프트로 AI에 요청을 보낼 수 있습니다.

![etc-image-8](https://blog.kakaocdn.net/dn/byqmW3/btsDs0gmbhN/nD0yGGNPPJHse09VhEJkU0/img.png)

etc-image-8

  
아래에 제가 정의한 프롬프트 목록입니다. 제가 사용하는 프롬프트는 ' [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) '를 참고하여 작성하였습니다. 여러분도 이를 참고하여 자신만의 프롬프트를 만들어보세요.

![etc-image-9](https://blog.kakaocdn.net/dn/bZQlyh/btsDqjHVxQD/JpzE1dgFU1Hp3ICvphBQk1/img.png)

etc-image-9

  
예를 들어 노트 작성 중에 “Effective note-taking” 텍스트를 선택하고, "이어서 작성해주세요."라는 프롬프트를 요청하면 아래 화면과 같이 Copilot 화면에 응답이 출력됩니다.

![etc-image-10](https://i.imgur.com/kJN4rjB.png)

## 마치며

LM Studio와 옵시디언을 사용하여 AI 기능을 최대한 활용하는 방법에 대해 알아보았습니다. 이 글이 여러분의 작업 효율성을 높이는 데 도움이 되기를 바랍니다. 더 자세한 정보나 질문이 있으시면 언제든지 댓글로 남겨주세요.

---

[![etc-image-11](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*  
[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

### ' > ' 카테고리의 다른 글

| [옵시디언 무료 퍼블리시 서버 비용 비교](https://anpigon.tistory.com/447) (0) | 2024.01.27 |
| --- | --- |
| [옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!](https://anpigon.tistory.com/446)(0) | 2024.01.19 |
| [무료 AI 올라마를 옵시디언에서 효과적으로 활용하는 방법(feat. Text Generator, BMO Chatbot)](https://anpigon.tistory.com/441) (0) | 2024.01.12 |
| [옵시디언 노트앱을 활용한 스팀 코인 수익 자동 기록 방법](https://anpigon.tistory.com/438) (0) | 2024.01.08 |
| [티스토리 Open API 종료에 따른 옵시디언 티스토리 플러그인 대응 계획](https://anpigon.tistory.com/432) (6) | 2023.12.24 |

, , , ,

댓글 0