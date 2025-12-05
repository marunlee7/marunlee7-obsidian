---
title: 옵시디언에서 Llama3-70b 모델 사용하기
aliases: []
published: 2024-04-27T23:32:39+09:00
status: planned
priority: medium
process: raw
source_name: 옵시디언에서 Llama3-70b 모델 사용하기
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/462
---
# 옵시디언에서 Llama3-70b 모델 사용하기

옵시디언에서 GroqCloud 서비스를 통해 **Llama3-70b** 모델을 설정하고 사용하는 방법을 소개해 드리겠습니다.

이 과정은 BMO 플러그인과 Copilot 플러그인 두 가지 방법으로 진행할 수 있으며, 사용자의 선호에 따라 필요한 옵시디언 플러그인을 선택하시면 됩니다.

## GroqCloud 가입하기

[GroqCloud](https://console.groq.com/) 는 다양한 AI 모델을 클라우드에서 손쉽게 사용할 수 있게 해주는 서비스입니다.

GroqCloud에서는 다음과 같은 AI 모델을 제공하며, 무료 사용량도 제공됩니다.

![etc-image-0](https://blog.kakaocdn.net/dn/ZPkAu/btsG0SyY1no/WTC3b5N1F2SgjoEhvIUlLk/img.png)

etc-image-0

GroqCloud 서비스에 가입하고 API Key를 발급받습니다. [\[API Key 발급 받으러 가기\]](https://console.groq.com/keys)

![etc-image-1](https://blog.kakaocdn.net/dn/cVyP4o/btsG1wh8nC6/smd9kDfRODiO82PCBe3WqK/img.png)

etc-image-1

## BMO 플러그인 사용하기

[옵시디언 BMO 플러그인](https://obsidian.md/plugins?id=bmo-chatbot) 은 옵시디언 내에서 AI챗봇과의 상호작용을 가능하게 하는 플러그인입니다.

BMO 플러그인을 통해 옵시디언에서 Llama3-70b 모델을 사용하기 위한 설정 방법은 아래와 같습니다.

### 1\. REST API URL Connection 설정에서 API Key와 REST API URL을 입력합니다.

- URL: `https://api.groq.com/openai/v1`
![etc-image-2](https://blog.kakaocdn.net/dn/cilOPj/btsGY9WejQx/hJntkThgFSaSZmhOuKrzNk/img.png)

etc-image-2

### 2\. General 설정에서 llmama3-70b-8192 모델를 선택합니다.

![etc-image-3](https://blog.kakaocdn.net/dn/W8sHO/btsGY1qBV7q/QuEOhmEO9kVMVZV5L11re0/img.png)

etc-image-3

필요한 경우, 다른 옵션들(Mak Tokens와 Temperature)도 함께 설정할 수 있습니다.

### 3\. Prompts에서 시스템 프롬프트를 설정합니다.

**BMO/Prompts** 경로에 노트를 생성하고 시스템 프롬프트를 작성합니다.

```bash
당신은 매우 친절한 AI Assistant  입니다. 
상대방의 요청에 최대한 자세하고 친절하게 답합니다. 
모든 대답은 한국어(Korean)으로 대답합니다.
```

Prompts 설정에서 시스템 프롬프트를 선택합니다.

![etc-image-4](https://blog.kakaocdn.net/dn/FJO0y/btsG0SyY5AC/z7k1qj08mHnsh3A35hQ2E0/img.png)

etc-image-4

### BMO 챗봇의 현재 노트 참조 기능 활용하기

`Allow Reference Current Note` 옵션을 활성화하면, BMO 챗봇이 현재 노트의 내용을 참고하여 답변을 제공하는 것을 볼 수 있습니다. 이 기능은 특히 노트에 기록된 정보를 바탕으로 질문할 때 유용합니다.

![etc-image-5](https://blog.kakaocdn.net/dn/dix9Da/btsGZt7Zd22/ipGYlBt8KV922dKrEEgsi0/img.png)

etc-image-5

## Copilot 플러그인 사용하기

[옵시디언 Copilot 플러그인](https://obsidian.md/plugins?id=copilot) 은 BMO 플러그인과 비슷한 플러그인입니다. Copilot 플러그인은 BMO 보다 설정이 복잡하지만, 더 많은 기능을 제공하고 있습니다. 그리고 Copilot 플러그인에서는 Groq API 설정 옵션이 제공되지 않으므로, OpenAI Proxy 기능을 사용해야 합니다. OpenAI API와 Groq API 구조가 동일하기 때문에 OpenAI Proxy 기능 사용이 가능합니다.

### 1\. Advanced Settings에서 OpenAI Proxy Base URL과 OpenAI Proxy Model Name을 설정합니다.

![etc-image-6](https://blog.kakaocdn.net/dn/bGkSRz/btsG0eh1Wxo/ZnRbLC2KQCi8VYASG6F9iK/img.png)

etc-image-6

### 2\. API Settings에서 OpenAI API Key에는 Groq에서 발급받은 키를 입력합니다.

![etc-image-7](https://blog.kakaocdn.net/dn/3A0xj/btsG0bezJdx/LAKG9cKh1zdsoT8HrX0oG1/img.png)

etc-image-7

## 마치며

옵시디언에서 Llama3-70b 모델을 설정하고 활용해 보세요.

[저작자표시 비영리 변경금지](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.ko)

### ' > ' 카테고리의 다른 글

| [옵시디언 웹 클리퍼 활용: 예스24 도서 정보를 편리하게 저장하는 방법 (템플릿 공유)](https://anpigon.tistory.com/483) (7) | 2024.12.16 |
| --- | --- |
| [옵시디언 빠른 메모의 모든 것](https://anpigon.tistory.com/471) (5) | 2024.11.11 |
| [Fleeting Notes Sync: 모바일 앱에서 빠르게 메모하여 옵시디언으로 동기화하기](https://anpigon.tistory.com/459) (9) | 2024.02.12 |
| [Zoottelkeeper: Obsidian MOC 인덱스 파일 자동 생성(개선된 버전)](https://anpigon.tistory.com/456) (0) | 2024.02.09 |
| [옵시디언에서 MOC(Master of Control) 자동 생성 및 폴더 노트 활용 가이드](https://anpigon.tistory.com/454) (0) | 2024.02.08 |

댓글 0