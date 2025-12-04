---
published: 2025-01-30T11:53:15+09:00
aliases: []
source_name: 옵시디언에서 DeepSeek R1 무료로 사용하기
references: https://anpigon.tistory.com/485
---
# 옵시디언에서 DeepSeek R1 무료로 사용하기

## 준비하기

옵시디언에서 **DeepSeek R1** 을 사용하려면  **Copilot 플러그인** 와 **Groq API** 가 필요합니다.

- **Copilot 플러그인 설치** → [설치하러 가기](https://obsidian.md/plugins?id=copilot)
- **Groq API 키 발급** → [키 발급 받으러 가기](https://console.groq.com/keys)

## 설정하기

Copilot 플러그인 설정에서 **Custom Model** 을 추가합니다.

![etc-image-0](https://blog.kakaocdn.net/dn/dN7LAZ/btsL4c6PJUR/4uSsjqVPjVXGiJ0ZGk5Ldk/img.png)

etc-image-0

- **Model Name**: `deepseek-r1-distill-llama-70b`
- **Provider**: `OpenAI Format`
- **Base URL**: `https://api.groq.com/openai/v1`
- **API Key**: `Groq API Key`

## 사용하기

**"Copilot: Open Copilot Chat Window"** 명령어를 실행하여 Copilot 채팅을 엽니다.

![스크린샷 2025-01-30 오전 11.25.27.png](https://blog.kakaocdn.net/dn/bnuexi/btsL2AgAUcx/SkPASTlyBS5PBIvizi27UK/img.png)

스크린샷 2025-01-30 오전 11.25.27.png

**참고사항**

테스트 결과, deepseek-r1-distill-llama-70b 모델의 **추론 성능은 매우 뛰어나지만 한글 출력이 뭉개지는 현상** 이 자주 발생합니다.

**💡 추가 팁**

**Ollama** 를 사용하면 **DeepSeek R1 양자화 모델** 을 로컬 오프라인 환경에서도 활용할 수 있습니다.

제 맥북(M2, 32GB)에서 ollama(deepseek-r1:32b) 모델을 사용하고 있으며 안정적으로 동작합니다.

Ollama 양자화 모델은 아래 링크에서 확인할 수 있습니다.

[https://ollama.com/library/deepseek-r1](https://ollama.com/library/deepseek-r1)

---

## Perplexity API로 DeepSeek R1 모델 사용하기

Perplexity PRO 구독자는 매달 **$5 상당의 API 크레딧** 을 받을 수 있으며, [SKT 사용자는 **Perplexity PRO** 를 1년간 무료](https://perplexity.sktadotevent.com/) 로 이용할 수 있습니다.

[→ Perplexity API Key 발급받기](https://www.perplexity.ai/settings/api)

그리고, 바로 어제 Perplexity가 DeekSeek의 추론 모델을 기반으로 한 새로운 API 제품인 **Sonar Reasoning 모델** 을 공개하였습니다.

*→ 관련 트윗: [https://x.com/perplexity\_ai/status/1884409454675759211](https://x.com/perplexity_ai/status/1884409454675759211)*

### Obsidian에서 Sonar Reasoning 모델 사용하기

Perplexity의 **Sonar Reasoning** 모델을 **Obsidian** 에서 사용하려면, **Copilot 플러그인** 에서 아래와 같이 **Custom Model** 을 설정하세요.

![etc-image-2](https://blog.kakaocdn.net/dn/SpYc2/btsL26frThk/FKHVnJXuhYpEmAYrnY7adK/img.png)

etc-image-2

- **Model Name**: `sonar-reasoning`
- **Provider**: `OpenAI Format`
- **Base URL**: `https://api.perplexity.ai`
- **API Key**: `Perplexity API Key`
- **Enable CORS**: `true`

---

## OpenRouter에서 DeepSeek R1 API 무료로 사용하기

OpenRouter에서 DeepSeek R1 API를 무료로 제공하고 있습니다.

![etc-image-3](https://blog.kakaocdn.net/dn/bmc91Y/btsL2HtrI98/lhlq3wqpsnvHqv1JuP9JR1/img.png)

etc-image-3

→ [OpenRouter API 키 발급받기](https://openrouter.ai/deepseek/deepseek-r1:free/api)

**Copilot 플러그인** 에 **Custom Model** 를 추가합니다.

- **Model Name**: `deepseek/deepseek-r1:free`
- **Provider**: `OpenAI Format`
- **Base URL**: `https://openrouter.ai/api/v1`
- **API Key**: `OpenRouter API Key`

## Links

- ["DeepSeek R1" 모델을 무료로 사용하는 다양한 방법](https://steemit.com/kr/@anpigon/20250131t153612742z)
- ["DeepSeek R1" 모델 사용 가능한 개발 IDE](https://steemit.com/kr/@anpigon/20250201t143347183z)

[저작자표시 비영리 변경금지](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.ko)

### ' > ' 카테고리의 다른 글

| [옵시디언 Note Companion AI 플러그인 셀프 호스팅으로 무료 사용하기](https://anpigon.tistory.com/488) (3) | 2025.04.12 |
| --- | --- |
| [옵시디언에서 Templater를 활용한 AI 요약 및 태그 생성](https://anpigon.tistory.com/484) (20) | 2024.12.28 |
| [옵시디언 웹 클리퍼 활용: 예스24 도서 정보를 편리하게 저장하는 방법 (템플릿 공유)](https://anpigon.tistory.com/483) (7) | 2024.12.16 |
| [옵시디언 빠른 메모의 모든 것](https://anpigon.tistory.com/471) (5) | 2024.11.11 |
| [옵시디언에서 Llama3-70b 모델 사용하기](https://anpigon.tistory.com/462) (0) | 2024.04.27 |