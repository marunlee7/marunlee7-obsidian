---
priority: medium
process: raw
source_name: 모든 작업을 통합, 자동화를 구현하는 QuickAdd 플러그인
source_type: web
source_author: 다다
references: https://kaminik.tistory.com/entry/%EB%AA%A8%EB%93%A0-%EC%9E%91%EC%97%85%EC%9D%84-%ED%86%B5%ED%95%A9-%EC%9E%90%EB%8F%99%ED%99%94%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-QuickAdd-%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8
links:
---
# 모든 작업을 통합, 자동화를 구현하는 QuickAdd 플러그인



![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2F3axyX%2FbtsFF5761Xe%2FAAAAAAAAAAAAAAAAAAAAAKHCQIzcduOnuw7poks6bl07CfZHiV4hMdMZFKdCUYqT%2Fimg.webp%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DzVSoCUS7NPIGdLlEXTWAJksAKyI%253D)

옵시디언 플러그인/커뮤니티 플러그인

---

## 개요

QuickAdd 플러그인은 옵시디언에서 고급 워크플로우를 구현하는 데 핵심적인 역할을 하는 플러그입니다. 이 플러그인을 사용하면, 하나 또는 여러 개의 쿼리을 통해 자동화된 노트를 생성할 수 있습니다. 특히, Commander 및 Templater 플러그인과 결합하여 사용할 때 그 효과가 극대화됩니다.

Plugin Info

| 플러그인 명 | QuickAdd |
| --- | --- |
| 플러그인 설명 | 모든 작업을 통합, 자동화 할 수 있는 플러그인 |
| 플러그인 분류 | [파일 관리](https://kaminik.tistory.com/pages/%EC%98%B5%EC%8B%9C%EB%94%94%EC%96%B8-%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8-%EC%82%AC%EC%A0%84#1._%ED%8C%8C%EC%9D%BC_%EA%B4%80%EB%A6%AC) |
| Github 링크 | [Github 링크](https://github.com/chhoumann/quickadd) |
| QuickAdd 문서 | [문서 링크](https://quickadd.obsidian.guide/) |
| 옵시디언 링크 | [플러그인 링크](https://kaminik.tistory.com/entry/) |
| 별점 | ⭐⭐⭐ |

---

## 기능

- **자동화된 노트 생성**: QuickAdd는 사용자가 설정한 질문들에 대한 답변을 바탕으로 자동적으로 노트를 생성합니다. 이는 일상적인 노트 작성을 자동화하고 표준화하는 데 큰 도움이 됩니다.
- **템플릿 활용**: 이 플러그인은 템플릿을 활용하여 노트의 형식을 미리 정의할 수 있게 해줍니다. 사용자는 특정한 형식이나 구조가 필요한 노트를 빠르고 일관성 있게 생성할 수 있습니다.
- **Commander와의 연동**: QuickAdd는 Commander 플러그인과 연동되어, 복잡한 명령어나 스크립트를 실행할 수 있게 해줍니다.
- **Templater와의 조합**: Templater 플러그인과 함께 사용할 때, QuickAdd는 더욱 강력해집니다. 사용자는 템플릿 내에서 동적인 콘텐츠를 생성하고, 이를 QuickAdd의 질문과 결합하여 맞춤형 노트를 자동으로 생성할 수 있습니다.

---

## 기본 사용 방법

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbFpr0o%2FbtsFkKqasRV%2FAAAAAAAAAAAAAAAAAAAAAFH6IM_yW1HIAp_aLB7A0CbzWphQ5gsW7n1kHfaHriQy%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DGfTOn6oRbhgR9CYuN%252B7VdhxD2vM%253D)

옵시디언 플러그인/커뮤니티 플러그인

설정에서 입력 상자에 명령 이름을 입력합니다.

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fbb72KD%2FbtsFmlJ66Fr%2FAAAAAAAAAAAAAAAAAAAAAIiSl1GgxwAGMJh_MOrK8Ll2uNReMTuTdJLgiPIu_Qhg%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3D8QD0ARR%252FzpUcobEL%252FwhSao2xBuQ%253D)

옵시디언 플러그인/커뮤니티 플러그인

Quickad 유형을 설정합니다.(Template, Capture, Macro, Multi)

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2F9mPxd%2FbtsFhVFUQ4b%2FAAAAAAAAAAAAAAAAAAAAAG1EHGoOdMGcSFlUaEa8EHxOgFqfyUSmZQ1a1it56Ssq%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DAcuJOoCdni20g8pOv4Itg1OLwy8%253D)

옵시디언 플러그인/커뮤니티 플러그인

Add Choice를 클릭하여 해당 유형의 명령을 추가하고, 톱니바퀴를 클릭해 해당 설정을 구성해 줍니다.

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fck93d8%2FbtsFh8SQut0%2FAAAAAAAAAAAAAAAAAAAAAGuezaPi7vLRcfoeHtXz5hZK1S7Ll-TtOC_OSwBjzfCg%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DcwYj4bCLIGX4TuV5d74oXpGTvbk%253D)

옵시디언 플러그인/커뮤니티 플러그인

번개 모양 아이콘을 클릭하면 명령이 활성화됩니다. 해당 명령은 명령어 팔레트에서 불러오거나 단축키로 설정할 수 있습니다.

---

## QuickAdd의 4가지 타입

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fbb72KD%2FbtsFmlJ66Fr%2FAAAAAAAAAAAAAAAAAAAAAIiSl1GgxwAGMJh_MOrK8Ll2uNReMTuTdJLgiPIu_Qhg%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3D8QD0ARR%252FzpUcobEL%252FwhSao2xBuQ%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Template**: 템플릿을 사용하여 새 파일을 생성합니다. Templater 플러그인과 함께 작동하여 기능을 확장하고 더 많은 옵션을 추가할 수 있습니다.
- **Capture**: 입력한 내용을 특정 파일에 캡처하고 저장합니다.
- **Macro**: 매크로로, 일련의 명령 조합을 실행합니다. JavaScript와 Obsidian 함수의 기능을 사용하여 수행할 수 있습니다.
- **Multi**: 위의 세가지 타입을 관리하는 폴더 타입

### Template

템플릿 타입은 Templater 플러그인이나 템플릿 코어 플러그인를 대체하기 위한 것이 아닙니다. 오히려 이들을 보완하고, 더 많은 가능성을 추가하기 위한 것입니다. QuickAdd 형식 구문을 Templater 템플릿 안에서 사용할 수 있으며, 둘 다 작동합니다.

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FdIRb4b%2FbtsFkT2wNuT%2FAAAAAAAAAAAAAAAAAAAAAIEK300hlPjgaYacd2LK1B4HWKBE37vs6icUxRXL8dCJ%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DqrD8uiTu9umnBRnj%252FO7R57UTTGE%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Template Path**. 삽입하고자 하는 템플릿의 경로입니다.
- **File Name Format**. 파일 이름에 대한 형식을 지정할 수 있습니다.
- **Create in folder**. 파일이 생성될 폴더를 지정합니다. 지정하지 않으면 파일은 루트 디렉토리에 생성됩니다.
- **Append link**. 현재 있는 파일에 새로 생성된 파일로의 링크가 추가됩니다.
- **Increment file name**. 해당 이름을 가진 파일이 이미 존재하는 경우, 파일 이름에 숫자를 추가하여 증가시킵니다.
- **Open**. 생성한 파일을 엽니다.

### Capture

Obsidian에서 현재 창 구성을 떠나지 않고 어디서든 빠르게 입력을 캡처하고 저장할 수 있습니다.

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2ForduY%2FbtsFsaalfVC%2FAAAAAAAAAAAAAAAAAAAAAFdvyu9N40eBFzwZsQiTV9F_ph9WBfWpUu3FcT-Fu0uo%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DWt0TklQLAe%252F%252B90vcmAlWLXSUpAY%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Capture To**: 캡처하는 파일의 이름입니다.
![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2Fdgl1hj%2FbtsFm8xWDFX%2FAAAAAAAAAAAAAAAAAAAAADtDrhIEkVp5Xmx0ym5B4fHR4fKwIRLI12U5dLv5G1va%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3D9KptdhUcScQxPOkWSR5oOIMRwkI%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Create file if it doesn't exist**: 파일이 없으면 파일을 생성합니다. 템플릿을 지정할 수도 있습니다.
- **Task**: 캡처된 텍스트를 Task로 형식화합니다.
- **Write to bottom of file**: 입력한 내용을 파일의 가장 아래에 배치합니다.
- **Append link**: 캡처하는 파일에 현재 열려 있는 파일의 링크를 추가합니다.
![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2F6mWd6%2FbtsFm8EHS3y%2FAAAAAAAAAAAAAAAAAAAAANFhNigeVYqeNagtKl1ox9OFnUgl49oiywjp9B360DEv%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DM6Da4fXDHQFGi9yg%252B7dkknYViN0%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Insert After**: 지정된 텍스트가 있는 줄 다음에 텍스트를 삽입할 수 있게 합니다.
- **Consider subsections**:

`Consider subsections` 비활성화시

```markdown
## 1. First heading

**Insert after** comes here.

-   content 1

-   content 2

-   content 3

    **Insert at end**은 여기에 옵니다.

### 1.1. Nested heading 1

Content

## 2. Another heading

Content
```

`Consider subsections` 활성화

```markdown
## 1. First heading

**Insert after**은 여기에 옵니다

-   content 1

-   content 2

-   content 3

### 1.1. Nested heading 1

Content

**Insert at end**은 여기에 옵니다. 

## 2. Another heading

Content
```
![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FbygMHo%2FbtsFm34Ev2G%2FAAAAAAAAAAAAAAAAAAAAAJ4itUJhmOB0KUYylwHWUi9B277KGyMHpU7XyHI8eGEe%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3DKBa34dDGV9OgJMhOQFEk8N6SX2g%253D)

옵시디언 플러그인/커뮤니티 플러그인

- **Capture Format**: 캡처하는 내용이 삽입될 정확한 형식을 지정할 수 있습니다.

### Macro

Macro는 여러 명령어들을 조합하여 하나의 처리 흐름을 형성할 수 있습니다. 이 명령어들에는 사용자 정의 스크립트가 포함되며, 로컬 소프트웨어의 사용자 정의 스크립트는 시스템 명령어를 통해 Python, Rust 등 다른 언어로 작성된 스크립트를 호출할 수 있습니다.

### Multi

![옵시디언 플러그인/커뮤니티 플러그인](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdna%2FRvtM5%2FbtsFm16OQZc%2FAAAAAAAAAAAAAAAAAAAAAOGHi7RBwcOPDg8PuCBffptzvEsv542Ow3fJnnCujoXj%2Fimg.png%3Fcredential%3DyqXZFxpELC7KVnFOS48ylbz2pIh7yKj8%26expires%3D1764514799%26allow_ip%3D%26allow_referer%3D%26signature%3D5Xx8b31SgGtuVRCUShdwf%252BXP3nk%253D)

옵시디언 플러그인/커뮤니티 플러그인

위의 세가지 타입을 관리하는 폴더 역할을 합니다.

---

## Format Syntax

- `{{DATE}}`: 현재 날짜를 `YYYY-MM-DD` 형식으로 출력합니다. 3일을 추가하려면 `{{DATE+3}}` 로 작성할 수 있습니다.
- `{{DATE:<DATEFORMAT>}}`: `<DATEFORMAT>` 을 [Moment.js 날짜 형식](https://momentjs.com/docs/#/displaying/format/) 으로 대체합니다. 3일을 추가하려면 `{{DATE<DATEFORMAT>+3}}` 로 작성할 수 있습니다.
- `{{VDATE:<변수 이름>, <날짜 형식>}}`: 날짜를 입력하라는 메시지가 표시되며, 입력된 날짜가 주어진 날짜 형식으로 파싱됩니다.
- `{{VALUE}}` 또는 `{{NAME}}`: 서로 바꿔 사용할 수 있습니다. 입력 프롬프트에서 주어진 값을 나타냅니다.
- `{{VALUE:<변수 이름>}}`: 값에 변수 이름을 사용할 수 있습니다.
- `{{LINKCURRENT}}`: 템플릿이 활성화된 파일로의 링크입니다. `[[링크]]` 형식.
- `{{MACRO:<MACRONAME>}}`: 매크로를 실행하고 여기에 반환 값을 작성합니다.
- `{{TEMPLATE:<TEMPLATEPATH>}}`: 템플릿을 `format` 에 포함합니다. Templater 구문을 지원합니다.
- `{{MVALUE}}`: LaTeX를 작성하는 수학 모달입니다.
- `{{FIELD:<FIELDNAME>}}`: `{{FIELD:FIELDNAME}}` 이 사용되는 어디에서나 `FIELDNAME` 의 값을 제안합니다. 필드는 YAML 필드이며, 값은 볼트에 있는 이 필드의 모든 값을 나타냅니다.
- `{{selected}}`: 현재 편집기에서 선택된 텍스트입니다.

---

## Inline Scripts

QuickAdd는 Template과 Capture에서 인라인 스크립트 사용을 지원합니다. 인라인 스크립트를 사용하면 원하는 JavaScript 코드를 실행할 수 있습니다.

사용자 스크립트와 마찬가지로 QuickAdd API가 제공됩니다. 인라인 스크립트에서는 아래 예시와 같이 `this` 로 전달됩니다.

```coffeescript
\`\`\`js quickadd

const input = await this.quickAddApi.inputPrompt("✍");

return \`입력된 내용: ${input}\`;

\`\`\`
```

인라인 스크립트를 작성할 때, Code Snippet을 삽입하는 것이 아니라면 언어를 표시할 때 `js` 가 아닌 `js quickadd` 라고 작성해야 합니다. 무언가를 삽입하고 싶다면, 그냥 `return` 하면 됩니다. 반환 타입은 **반드시** 문자열이어야 합니다.

---

## 관련 링크

- [Quicka매ㅐdd Document](https://quickadd.obsidian.guide/)

---

