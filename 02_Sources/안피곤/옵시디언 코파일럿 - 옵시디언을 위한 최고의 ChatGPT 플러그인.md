---
published: 2023-04-26T19:04:39+09:00
aliases: []
source_name: 옵시디언 코파일럿 - 옵시디언을 위한 최고의 ChatGPT 플러그인
references: https://anpigon.tistory.com/393
---
# 옵시디언 코파일럿 - 옵시디언을 위한 최고의 ChatGPT 플러그인

이 글에서는 옵시디언에서 사용성과 효율성을 높여주는 최고의 2가지 ChatGPT 플러그인을소개합니다. 제가 이전에 사용해본 ChatGPT 플러그인 중 몇 가지를 언급하면 다음과 같습니다:

- Text Generator: [nhaouari/obsidian-textgenerator-plugin](https://github.com/nhaouari/obsidian-textgenerator-plugin)
- Ava: [louis030195/obsidian-ava](https://github.com/louis030195/obsidian-ava)
- ChatGPT MD: [chatgpt-md](https://github.com/bramses/chatgpt-md)
- GPT-3 Notes: [micahke/obsidian-gpt3-notes](https://github.com/micahke/obsidian-gpt3-notes)
- Companion: [rizerphe/obsidian-companion](https://github.com/rizerphe/obsidian-companion)

하지만 위 ChatGPT 플러그인들은 사용성이 조금 불편하다고 생각합니다. 따라서 이에 대한 대안으로 다음에 소개하는 ChatGPT 플러그인을 사용하면 업무 효율과 생산성을 크게 향상시킬 수 있습니다.

## Obsidian Copilot

Obsidian Copilot은 옵시디언에 바로 탑재된 ChatGPT 인터페이스입니다. 미니멀한 디자인으로 사용이 간편합니다. Obsidian Copilot 플러그인에 대한 자세한 내용은 아래 링크에서 확인할 수 있습니다.  
[https://github.com/logancyang/obsidian-copilot](https://github.com/logancyang/obsidian-copilot)

![etc-image-0](https://i.imgur.com/dPP6fFU.gif)

~~현재 이 플러그인은 베타 버전이기 때문에 수동으로 설치해야 합니다. [OBSIDIAN42 - BRAT](https://obsidian.md/plugins?id=obsidian42-brat) 플러그인을 사용하여 설치하는 것을 추천합니다. BRAT 사용 방법은 [분석맨님 블로그의 BRAT 글](https://secondbrain.analysisman.com/1_WRITE/1_Obsidian/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8+%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8+%EC%B6%94%EC%B2%9C+-+Obsidian42+-+BRAT) 을 참고해주세요.~~ 👉 지금은 정식 커뮤니티 플러그인에 등록되었습니다.

플러그인 설치 방법은 [\[설치 링크\]](https://obsidian.md/plugins?id=copilot) 를 클릭하여 설치하거나, 옵시디언 커뮤니티 플러그인에서 **Copilot** 를 검색해서 설치합니다.

![스크린샷 2023-10-14 오후 9.14.20.png](https://blog.kakaocdn.net/dn/cVHQvl/btsytQKdCQx/cgjuyfkxzCKGk6yeRHXzPk/img.png)

스크린샷 2023-10-14 오후 9.14.20.png

Obsidian Copilot 플러그인을 설치하고 가장 먼저 해야하는 일은 OpenAI API Key를 셋팅하는 것입니다. [OpenAI API Key 페이지](https://platform.openai.com/account/api-keys) 에서 API 키를 생성하고 Obsidian Copilot 플러그인 셋팅 화면으로 들어가서 API Key를 입력합니다.

![etc-image-2](https://i.imgur.com/fTeM3Im.png)

현재 사용 가능한 모델은 GPT-3.5와 GPT-4입니다. GPT-4는 비용이 높기 때문에 상대적으로 저렴한 GPT-3.5를 사용하는 것을 추천합니다. Temperature는 0에 가까울수록 정확한 답변을 생성하고, 1에 가까울수록 창의적인 답변을 생성합니다. 기본값은 0.7로 설정되어 있습니다. Token limit은 사용 가능한 토큰의 최대 개수를 나타냅니다. 입력 토큰과 생성된 토큰의 총 개수입니다.

옵시디언에서 Copilot 플러그인을 활성화하면 명령어 팔레트와 리본 아이콘에서 채팅 화면을 토글할 수 있습니다.

![etc-image-3](https://i.imgur.com/m8dKhw7.png)

Obsidian Copilot 플러그인의 주요 특징은 다음과 같습니다.

- **옵시디언에서 바로 채팅하기**: 옵시디언 사용자들은 이제 옵시디언 내에서 바로 채팅GPT를 사용할 수 있습니다. 이를 통해 노트 작업에서 발생하는 다양한 질문이나 문제들을 AI 기술을 활용하여 신속하게 해결할 수 있습니다.
- **GPT-3.5 또는 GPT-4 모델 선택**: Obsidian Copilot 플러그인은 GPT-3.5 또는 GPT-4 모델 중 선택할 수 있습니다. GPT-4 모델은 더욱 정교하고 빠른 응답을 제공할 수 있습니다. 또한, ChatGPT Plus와 같이 GPT-4 사용량에 제한이 없으며, API 사용량에 따라 비용을 지불하면 됩니다. (GPT-4 API에 액세스 권한이 있는 경우에만 GPT-4 모델을 선택할 수 있습니다.)
- **손쉬운 메시지 복사**: Obsidian Copilot 플러그인은 클릭 한 번으로 AI의 개별 응답과 프롬프트를 복사할 수 있습니다. 이를 통해 사용자들은 AI의 응답을 다른 문서나 애플리케이션에서 쉽게 활용할 수 있습니다.
- **전체 대화를 원클릭으로 메모 저장**: Obsidian Copilot 플러그인은 단순한 메시지 저장 뿐만 아니라 전체 대화를 마크다운 메모로 저장할 수 있습니다. 이를 통해 사용자들은 채팅 기록을 보관하고 필요할 때 언제든지 검색할 수 있습니다.
- **활성 노트와 대화하기**: Obsidian Copilot 플러그인은 현재 열려 있는 노트의 컨텍스트를 활용하여 대화할 수 있습니다. 이를 통해 사용자들은 현재 작업 중인 노트와 관련된 질문이나 문제를 더욱 쉽게 해결할 수 있습니다.

또 다른 Copilot과 유사한 플러그인으로는 **Obsidian Weaver** 가 있습니다. Obsidian Weaver 플러그인에 대한 자세한 소개는 아래에서 다시 설명하겠습니다.

## Obsidian Weaver

Obsidian Weaver는 또 다른 Copilot과 유사한 플러그인입니다. 이 플러그인은 옵시디언 노트 필기 워크플로우에 ChatGPT/GPT-3를 통합하여, AI가 생성한 제안과 인사이트에 쉽게 액세스할 수 있게 해줍니다. 이를 통해 글쓰기와 브레인스토밍 과정을 보다 개선할 수 있습니다. Obsidian Weaver 플러그인에 대한 자세한 내용은 아래 링크에서 확인할 수 있습니다.  
[https://github.com/vasilecampeanu/obsidian-weaver](https://github.com/vasilecampeanu/obsidian-weaver)

![etc-image-4](https://i.imgur.com/szsWdbZ.png)

  
Weaver는 Copilot과 마찬가지로 BRAT를 사용하여 설치할 수 있습니다.

Weaver 플러그인 플러그인의 주요 특징은 다음과 같습니다.

- 옵시디언 내에서 채팅하기: 옵시디언 내에서 ‘Add’ 버튼을 클릭하여 AI 어시스턴트와 새 채팅 세션을 쉽게 만들 수 있습니다.
- 손쉬운 메시지 복사: Copilot과 동일하게, 한 번 클릭으로 메시지를 복사해 노트에 추가할 수 있습니다.
- 채팅 노트 자동 저장: Copilot과 달리, 채팅 노트를 수동으로 저장할 필요가 없습니다. 모든 채팅 노트가 지정된 폴더에 자동으로 저장되므로, 이전 채팅창을 다시 방문할 때의 경험이 크게 개선됩니다.
- AI 지원: 새 채팅 세션을 만든 후에는 AI 어시스턴트에게 질문하고 즉각적인 응답을 받을 수 있습니다. 따라서 옵시디언 환경을 벗어나지 않고도 모든 주제에 대한 정보와 인사이트를 쉽게 얻을 수 있습니다.

## 마치며

Obsidian Copilot와 Obsidian Weaver 플러그인 모두 훌륭한 플러그인입니다. 제가 두 가지 모두 사용해본 경험으로는 Weaver 플러그인의 사용 경험이 더 좋았습니다. 특히 Obsidian Weaver는 채팅 내용을 자동으로 저장하여 나중에 다시 채팅 창에서 액세스할 수 있는 기능이 마음에 들었습니다.

### ' > ' 카테고리의 다른 글

| [옵시디언 노트앱을 활용한 스팀 코인 수익 자동 기록 방법](https://anpigon.tistory.com/438) (0) | 2024.01.08 |
| --- | --- |
| [티스토리 Open API 종료에 따른 옵시디언 티스토리 플러그인 대응 계획](https://anpigon.tistory.com/432) (6) | 2023.12.24 |
| [AnuPpuccin 옵시디언 테마: 최고의 디자인과 다양한 옵션](https://anpigon.tistory.com/332) (15) | 2023.03.15 |
| [밀리의 서재에서 하이라이트를 노트앱으로 내보내는 방법](https://anpigon.tistory.com/331) (4) | 2023.03.15 |
| [(번역) Make.md: 옵시디언 초보에게 가장 유용한 플러그인](https://anpigon.tistory.com/328) (2) | 2023.03.11 |

,

댓글 4