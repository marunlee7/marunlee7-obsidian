---
title: 무료 AI 올라마를 옵시디언에서 효과적으로 활용하는 방법(feat. Text Generator, BMO Chatbot)
aliases: []
published: 2024-01-12T21:46:25+09:00
status: planned
priority: medium
process: raw
source_name: 무료 AI 올라마를 옵시디언에서 효과적으로 활용하는 방법(feat. Text Generator, BMO Chatbot)
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/441
---
# 무료 AI 올라마를 옵시디언에서 효과적으로 활용하는 방법(feat. Text Generator, BMO Chatbot)

<video src="https://blog.kakaocdn.net/dn/bkFfZG/btsDpbJVdHO/V2K0ngND05MiobaoSfsfz0/%E1%84%82%E1%85%A1%E1%84%8B%E1%85%B4%20%E1%84%83%E1%85%A9%E1%86%BC%E1%84%8B%E1%85%A7%E1%86%BC%E1%84%89%E1%85%A1%E1%86%BC2.mp4?attach=1&amp;knm=tfile.mp4" controls="controls"></video>

  
이전 글에서는 올라마(Ollama)에 대한 기본적인 소개를 하였습니다(참고: [로컬에서 무료로 사용할 수 있는 LLM 도구, Ollama 활용 가이드](https://anpigon.tistory.com/434)). 이번 글에서는 올라마(Ollama)를 옵시디언 노트앱에서 어떻게 활용할 수 있는지 상세히 안내하고자 합니다.  

## 올라마와 윈도우OS 호환성 문제

올라마는 아직 윈도우OS를 지원하지 않습니다. 하지만 WSL2 또는 Docker를 이용하면 윈도우 환경에서도 올라마를 실행할 수 있습니다. 대안으로는, 윈도우를 지원하는 프로그램인 [LM Studio](https://lmstudio.ai/) 를 사용하는 것도 좋은 선택입니다. 옵시디언에서 LM Studio를 사용하는 방법에 대해서는 [\[여기\]](https://anpigon.tistory.com/442) 에 자세히 설명되어 있습니다.

## 올라마 AI모델 설치 및 실행

올라마의 설치 및 모델 다운로드는 매우 간단합니다. 먼저 [ollama.ai](https://ollama.ai/) 에서 올라마를 다운로드하여 설치합니다. 그리고 아래의 명령어를 통해 `mistral` 모델을 다운로드합니다.

```sh
ollama pull mistral
```

  
옵시디언에서 올라마를 사용하려면 Cross-Origin Rereferences Sharing(CORS) 문제를 해결해야 합니다. 방법은 환경변수를 사용하는 방법과 명령어를 사용하는 2가지 방법이 있습니다.  

### 환경변수를 설정하여 올라마 서버 실행

만약 macOS를 사용 중이라면, launchctl setenv 명령어를 사용하여 다음과 같이 OLLAMA\_ORIGINS 환경변수를 설정할 수 있습니다.

```bash
launchctl setenv OLLAMA_ORIGINS "*"
```

> **중요**: OLLAMA\_ORIGINS=\* 옵션은 옵시디언에서 CORS 오류를 방지하기 위해 필수입니다.

환경변수를 설정한 후에는 Ollama를 종료하고 다시 실행해야 합니다.

![etc-image-0](https://blog.kakaocdn.net/dn/cak2lS/btsDpyZttoZ/5fPdHQmcm9XrTcS5EuRxu1/img.png)

etc-image-0

### 명령어 사용하여 올라마 서버 실행

만약 올라마 앱을 사용하지 않고 CLI 명령어를 사용하여 올라마 서버를 시작하려면 다음 명령을 사용합니다:

```sh
OLLAMA_ORIGINS=* ollama serve
```
![etc-image-1](https://blog.kakaocdn.net/dn/xwmh6/btsDrHPVMxM/cxRj7RWewvyxAEUe6kUnUk/img.png)

etc-image-1

아래와 같이 "address already in use"라는 에러 메시지가 표시된다면, 이는 동일한 포트를 사용하고 있는 서버가 이미 실행 중이므로 실행 중인 Ollama 서버를 종료해야 합니다.

![etc-image-2](https://blog.kakaocdn.net/dn/rhIO4/btsDqbJFYg4/7lEtDt2U0PqDBXqDkXAk6K/img.png)

etc-image-2

  
올라마 서버가 성공적으로 실행되었다면, 다음과 같이 API 호출을 할 수 있습니다.

```bash
curl http://localhost:11434/api/chat -d '{
  "model": "mistral",
  "messages": [
    { "role": "user", "content": "why is the sky blue?" }
  ]
}'
```

**성공적인 API 호출 결과:**

![etc-image-3](https://blog.kakaocdn.net/dn/F85DR/btsDxg4SIi5/qfWEkeEa1Tr8fEBUbYULOK/img.png)

etc-image-3

> - OLLAMA\_HOST 환경변수를 사용하면 올라마 서버 IP와 PORT 번호를 변경할 수 있습니다. (기본값은 127.0.0.1:11434 입니다.)
> - 환경변수와 올라마 서버 설정에 대한 추가 정보는 [올라마 FAQ](https://github.com/jmorganca/ollama/blob/main/docs/faq.md#how-do-i-use-ollama-server-environment-variables-on-mac) 페이지에서 찾을 수 있습니다.

## 옵시디언에서 올라마를 활용하는 방법: Text Generator 플러그인

올라마 공식 홈페이지에서는 [obsidian-ollama 플러그인](https://obsidian.md/plugins?id=ollama) 을 소개하고 있습니다. 하지만 여기서는 제가 익숙한 [Text Generator 플러그인](https://obsidian.md/plugins?id=obsidian-textgenerator-plugin) 을 사용해서 올라마를 활용하는 방법을 설명하겠습니다. 추후에 기회가 되면 obsidian-ollama 플러그인 사용법도 소개해드리겠습니다.

### 옵시디언 Text Generator 플러그인 설치 및 설정 방법

옵시디언에서 [Text Generator 플러그인](https://obsidian.md/plugins?id=obsidian-textgenerator-plugin) 을 설치합니다. 그 후, Text Generator 플러그인 설정화면에서 아래와 같이 설정을 완료합니다.

- LLM Provider: **Ollama**
- Model: **mistral**
- Base Path: `http://localhost:11434`
![etc-image-4](https://blog.kakaocdn.net/dn/bojm4O/btsDqNuKo1t/FMWFilpNtoRAEgEwvo53S1/img.png)

etc-image-4

### Text Generator를 사용한 문장 생성

옵시디언에서 노트를 작성하다가 ollama를 호출할 때는 `/` 를 입력해 명령어 창을 불러옵니다. 그리고, "Text Generator: Generate Text!"를 선택하면 됩니다. 또는 단축키 `Cmd` + `J` 를 사용할 수도 있습니다

![etc-image-5](https://blog.kakaocdn.net/dn/uPXLg/btsDriWX2ES/bAmkNLSNeXNqsdPjAjCk6K/img.png)

etc-image-5

조금 기다리면 자동으로 텍스트가 생성됩니다.

![etc-image-6](https://blog.kakaocdn.net/dn/b3TQjJ/btsDwB9aa45/0gL9hxZklvGJkjv36Gk2C0/img.png)

etc-image-6

### Text Generator에서 프롬프트 템플릿을 활용한 고급 사용

옵시디언에서 노트를 작성하다가 `/` 를 입력해 명령어 창을 불러오고, "Text Generator: Templates: Generate & Insert"를 선택한 후, 미리 정의한 프롬프트 템플릿을 사용합니다.

![etc-image-7](https://blog.kakaocdn.net/dn/Cywmp/btsDrlfbb6p/pqJKUb5SOihnKaehdKSVOK/img.png)

etc-image-7

그리고 미리 정의한 프롬프트 템플릿을 선택합니다. 아래 화면에 보이는 "설명해주세요"는 제가 미리 정의한 프롬프트 템플릿입니다.

![etc-image-8](https://blog.kakaocdn.net/dn/3TXpR/btsDqiQGwCL/fXWrje3HWK2YYx7nMTjVn1/img.png)

etc-image-8

그리고 잠시 기다리면 정의된 템플릿에 따라 텍스트가 생성됩니다.

![etc-image-9](https://blog.kakaocdn.net/dn/cyIJoU/btsDxLi7etz/bszIDBBFyhtQLbj4uqrHpK/img.png)

etc-image-9

### Text Generator 프롬프트 템플릿 예시:

```bash
---
promptId: explain
name: 👼설명해주세요
tags:
  - thinking
  - writing
version: 0.0.1
---
다음 내용에 대해 전문적으로 설명해주세요. 

\`\`\`
{{tg_selection}}
\`\`\`
```

> 템플릿 문법에 대한 자세한 설명은 [Text Generator 플러그인 문서](https://docs.text-gen.com/_notes/3-+Templates/01+Understanding+Context) 에서 확인하실 수 있습니다.

### 올라마 한국어 답변 가능성

프롬프트 템플릿에서 한국어로 대답을 요청하면 한국어로 대답이 제공됩니다. 그러나, 한국어 답변의 퀄리티는 많이 부족합니다.

![etc-image-10](https://blog.kakaocdn.net/dn/NYuqp/btsDqgL8ODb/bkCLVSiOAYaWfqy0ywPj60/img.png)

etc-image-10

일단은 영어로 답변을 받고 구글 번역기나 DeepL과 같은 번역 서비스를 이용하는 것이 더 나을 수 있습니다.

## 옵시디언에서 올라마를 활용하는 방법, 2번째: BMO Chatbot 플러그인

옵시디언 BMO Chatbot 플러그인은 OpenAI, Ollama, [LocalAI](https://github.com/go-skynet/LocalAI) 를 연동하여 LLM와 상호 작용이 가능합니다. 그리고 열려있는 노트를 참조하여 봇과 대화가 가능합니다. 채팅UI에서 `/save` 명령을 사용하면 대화 내용을 저장할 수 있습니다.

### 옵시디언 BMO Chatbot 플러그인 설치 및 설정 방법

옵시디언에서 [BMO Chatbot 플러그인](https://obsidian.md/plugins?id=bmo-chatbot "BMO Chatbot") 을 설치합니다. 그 후, BMO Chatbot 플러그인 설정화면에서 다음과 같이 설정을 완료합니다.

- OLLAMA REST API URL: `http://localhost:11434`
![etc-image-11](https://blog.kakaocdn.net/dn/0HFK6/btsDxfrn4mI/HZkIOBdpCkMBEjicnxViFk/img.png)

etc-image-11

### BMO Chatbot 사용 방법

가장 간단한 사용하는 방법은 옵시디언에서 텍스트(프롬프트)를 선택하고, 명령어 창에서 "BMO Chatbot: Prompt Select Generate"를 선택하는 것입니다. 이렇게 하면 선택한 프롬프트가 실행되고, 그 결과가 자동으로 노트에 기록됩니다.

![etc-image-12](https://blog.kakaocdn.net/dn/OwQuV/btsDxhQe6Tf/Z0ByybvLfBygMgKb4A7E91/img.png)

etc-image-12

![etc-image-13](https://blog.kakaocdn.net/dn/zSOzQ/btsDuyY8zg8/BmBofiI8ZP2iO8INEOVNok/img.png)

etc-image-13

### BMO Chatbot Chat UI 사용하기

옵시디언 명령어 창에서 "BMO Chatbot: Open BMO Chat"를 선택하면 채팅UI 화면이 나타납니다.

![etc-image-14](https://blog.kakaocdn.net/dn/FoDn2/btsDs1mTKox/goGROe9svDrDckSTpHX2KK/img.png)

etc-image-14

  
BMO 채팅UI에서는 AI와 대화를 할 수 있습니다.

![etc-image-15](https://blog.kakaocdn.net/dn/UFHPv/btsDrh4MsZ7/3djPkHkl7FZDkt9pdXvZ31/img.png)

etc-image-15

이 채팅UI에서는 다양한 명령어을 사용할 수 있습니다. 이를 통해 사용자 정의 프롬프트를 설정하거나 채팅 내용을 저장하는 등의 작업이 가능합니다. 사용 가능한 명령어에 대한 자세한 정보는 [\[여기\]](https://github.com/longy2k/obsidian-bmo-chatbot?tab=readme-ov-file#commands) 를 참조하세요.

## 마치며

이 글은 옵시디언 사용자들이 효과적으로 Text Generator 플러그인을 활용하는 방법을 소개하기 위해 작성되었습니다. 옵시디언과 관련된 다른 유용한 플러그인이나 기능들에 대해서도 알아보시는 것을 추천드립니다.

---

[![etc-image-16](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*  
[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

### ' > ' 카테고리의 다른 글

| [옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!](https://anpigon.tistory.com/446)(0) | 2024.01.19 |
| --- | --- |
| [무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)](https://anpigon.tistory.com/442) (0) | 2024.01.14 |
| [옵시디언 노트앱을 활용한 스팀 코인 수익 자동 기록 방법](https://anpigon.tistory.com/438) (0) | 2024.01.08 |
| [티스토리 Open API 종료에 따른 옵시디언 티스토리 플러그인 대응 계획](https://anpigon.tistory.com/432) (6) | 2023.12.24 |
| [옵시디언 코파일럿 - 옵시디언을 위한 최고의 ChatGPT 플러그인](https://anpigon.tistory.com/393) (4) | 2023.04.26 |

, ,

댓글 0