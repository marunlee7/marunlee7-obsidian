---
title: 옵시디언에서 MOC(Master of Control) 자동 생성
aliases: []
status: planned
priority: medium
process: raw
source_name: 옵시디언에서 MOC(Master of Control) 자동 생성
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/454
---
# MOC(Master Of Control) 자동 생성 및 폴더 노트 활용 가이드

**목차** 반응형

Obsidian은 효율적인 지식 관리와 노트 테이킹을 위한 강력한 도구입니다. 여기서는 Obsidian에서 MOC 자동 생성과 폴더 노트 사용을 최적화하는 데 도움이 되는 플러그인과 그 설정 방법에 대해 상세히 소개하겠습니다.

## 필요한 플러그인

Obsidian에서 더욱 효율적인 노트 관리를 위해 다음과 같은 플러그인을 사용할 수 있습니다:

- **[Zoottelkeeper](https://obsidian.md/plugins?id=zoottelkeeper-obsidian-plugin)**: MOC(Master of Control) 파일을 자동으로 생성하고 관리하는 플러그인입니다. 이를 통해 모든 노트와 문서를 쉽게 찾아볼 수 있는 인덱스 페이지를 자동으로 만들어 줍니다.
- **[Folder Notes](https://obsidian.md/plugins?id=folder-notes)**: 폴더 노트를 사용하여 각 폴더에 대한 개요나 인덱스를 설정할 수 있게 해주는 플러그인입니다. 이는 폴더 구조를 더욱 의미 있게 활용하고자 할 때 유용합니다.
- **[Force Note View Mode](https://obsidian.md/plugins?id=obsidian-view-mode-by-frontmatter)**: 특정 노트를 열었을 때 기본적으로 편집 모드가 아닌 읽기 모드로 강제 전환시켜 주는 플러그인입니다. 이는 노트를 읽거나 참고할 때 직관적인 경험을 제공합니다.

## 설정 방법

각 플러그인을 최대한 활용하기 위한 설정 방법을 단계별로 안내합니다.

### Zoottelkeeper 설정

1. Zoottelkeeper 플러그인의 설정 페이지로 이동합니다.
2. **List Style** 옵션을 **Listed link** 로 변경하여, 생성되는 MOC 페이지에서 노트 링크를 리스트 형식으로 표시하도록 설정합니다.
![etc-image-0](https://blog.kakaocdn.net/dn/bRcGQv/btsED7lRaf7/khoslBM1q2bGfi4EnT77Q0/img.png)

### Folder Notes 설정

1. Folder Notes 플러그인의 설정 페이지로 이동합니다.
2. **Folder note name** 을 `_Index_of_{{folder_name}}` 로 변경하여, 각 폴더에 대한 인덱스 노트의 이름을 해당 파일 이름으로 자동 생성되게 합니다.
![etc-image-1](https://blog.kakaocdn.net/dn/k5QIn/btsEELikect/EboBVK0ya4OHpx2v1k7NNk/img.png)

### Force Note View Mode 설정

1. Force Note View Mode 플러그인의 설정 페이지로 이동합니다.
2. **File name** 필드에 `_Index_of_` 를 입력하고, **obsidianUIMode** 옵션을 **preview** 로 선택하여, `_Index_of_` 로 시작하는 모든 노트를 열었을 때 자동으로 읽기 모드로 전환되게 합니다.
![etc-image-2](https://blog.kakaocdn.net/dn/rENS4/btsEBp8SkEm/I6KFO1wQPAsEKinrb0AN20/img.png)

설정을 마친 후, 폴더를 클릭하면 아래 이미지와 같이 폴더에 포함된 노트들이 자동 링크로 작성된 인덱스 노트가 생성되어 나타납니다. 이를 통해 관련 노트를 빠르고 쉽게 찾아볼 수 있습니다.

![etc-image-3](https://blog.kakaocdn.net/dn/C03J2/btsEECsnTvi/TXaPmFM3qKNKdfGKn5hK6K/img.png)

이 가이드를 통해 Obsidian 내에서 효율적인 노트 관리와 빠른 정보 접근을 실현할 수 있습니다. MOC 자동 생성과 폴더 노트 설정을 적절히 활용하여, 노트 테이킹 경험을 한층 더 업그레이드해 보세요.

> Zoottelkeeper 플러그인이 자동으로 생성한 파일들을 삭제하고자 한다면, “ [터미널 명령을 사용하여 특정 텍스트를 포함하는 모든 파일 삭제하기](https://anpigon.tistory.com/455) ” 글을 참조하세요.

## 연결문서

- [Zoottelkeeper 플러그인 개선된 버전](https://anpigon.tistory.com/456)

---

[![etc-image-4](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*

[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

반응형

### ' > ' 카테고리의 다른 글

| [Fleeting Notes Sync: 모바일 앱에서 빠르게 메모하여 옵시디언으로 동기화하기](https://anpigon.tistory.com/459) (7) | 2024.02.12 |
| --- | --- |
| [Zoottelkeeper: Obsidian MOC 인덱스 파일 자동 생성(개선된 버전)](https://anpigon.tistory.com/456) (0) | 2024.02.09 |
| [옵시디언에서 AI 코파일럿 무료로 사용하기](https://anpigon.tistory.com/453) (0) | 2024.02.06 |
| [옵시디언 웹 스크랩핑 가이드의 모든 것](https://anpigon.tistory.com/452) (0) | 2024.02.04 |
| [티스토리 Open API 서비스 종료 대비: 새로운 블로그 연동 방안 탐색](https://anpigon.tistory.com/451) (3) | 2024.01.30 |

## 要約 ✍︎


## 思索 🙇🏻

