---
published: 2024-02-12T19:25:22+09:00
aliases: []
source_name: Fleeting Notes Sync 모바일 앱에서 빠르게 메모하여 옵시디언으로 동기화하기
references: https://anpigon.tistory.com/459
---
# Fleeting Notes Sync 모바일 앱에서 빠르게 메모하여 옵시디언으로 동기화하기

**목차**

아이폰에서는 옵시디언 앱의 실행 속도가 느려 빠른 메모 작성이 어려웠습니다. 이러한 문제로 인해 여러 노트 앱과 각각에 맞는 동기화 방식을 사용했었습니다. 구체적으로는 Google Keep([Obsidian Custom Frames](https://github.com/Ellpeck/ObsidianCustomFrames) 플러그인으로 옵시디언에서 보기), Apple Notes([Apple Notes를 옵시디언으로 가져오기](https://help.obsidian.md/import/apple-notes)), UpNote([UpNote To Obsidian](https://github.com/simonoliver/UpNote_To_Obsidian)), 그리고 가장 최근까지 Logseq([Obsidian과 Logseq을 함께 사용하는 방법](https://hub.logseq.com/integrations/aV9AgETypcPcf8avYcHXQT/how-to-use-obsidian-and-logseq-together-and-why-markdown-matters/1rqp92wgow7wGXS37Ckz1U))를 사용했습니다. 하지만 이러한 방법들은 동기화 과정이 번거롭고 매끄럽지 않아 다소 불편했습니다.  
  

최근 옵시디언에서 Fleeting Notes Sync 플러그인을 발견하고 사용해보기 시작했는데, Fleeting Notes 앱은 사용이 간편하고 동기화 속도도 빨라 현재까지 매우 만족스럽습니다.  
  

이 글은 Fleeting Notes 앱과 옵시디언 플러그인의 설치 및 설정 과정을 안내합니다.

---

아래 내용은 [Fleeting Notes 가이드 문서](https://www.fleetingnotes.app/posts/sync-fleeting-notes-with-obsidian) 를 참조하여 작성되었습니다.  
  

## Fleeting Notes 앱 설치

Fleeting Notes 앱은 무료로 사용할 수 있습니다. 무료 버전에서 제공하는 기능은 다음과 같습니다: 무제한 메모 작성, 10MB 첨부 파일 제한, 모든 오프라인 기능, Obsidian MD와의 동기화를 위한 플러그인.  
  

[여기](https://docs.fleetingnotes.app/getting-started/download) 에서 Fleeting Notes 앱을 다운로드하고 설치하세요. Fleeting Notes는 다양한 플랫폼을 지원합니다. 웹 버전, 브라우저 익스텐션(크롬, 파이어폭스, 사파리), 모바일 앱(안드로이드, iOS), 데스크탑 앱(윈도우, 맥)에서 사용할 수 있습니다.  
  

## 옵시디언 Fleeting Notes Sync 플러그인 설치 및 설정

이 [링크](https://obsidian.md/plugins?id=fleeting-notes-obsidian) 를 클릭하고 Fleeting Notes Sync 플러그인을 설치하세요. 그 다음 Fleeting Notes Sync 플러그인 설정에서 Sign In 버튼을 클릭해서 로그인합니다.

![etc-image-0](https://i.imgur.com/O9aXQ9V.png)

  
실시간 양방향 동기화를 원하신다면 ‘Sync notes automatically’ 옵션을 활성화하고, 'Sync type’으로 'Realtime Two-ways sync (FN <=> Obsidian)'을 선택하세요.

![etc-image-1](https://i.imgur.com/GLG5pwS.png)

> **실시간 양방향 동기화** 란 Fleeting Notes와 옵시디언 사이에 변경 사항이 있을 때, 양쪽 모두에서 즉시 반영되는 기능을 말합니다.

  

## Fleeting Notes Sync 플러그인 사용법

1. 명령어 팔레트를 열고 `Fleeting Notes: Pull All Notes from Fleeting Notes` 를 실행합니다.
2. 메모가 Fleeting Notes와 동기화되며 알림을 받게 됩니다.  
	  

### ' > ' 카테고리의 다른 글

| [옵시디언 빠른 메모의 모든 것](https://anpigon.tistory.com/471) (5)                                   | 2024.11.11 |
| ----------------------------------------------------------------------------------------- | ---------- |
| [옵시디언에서 Llama3-70b 모델 사용하기](https://anpigon.tistory.com/462) (0)                          | 2024.04.27 |
| [Zoottelkeeper: Obsidian MOC 인덱스 파일 자동 생성(개선된 버전)](https://anpigon.tistory.com/456) (0)   | 2024.02.09 |
| [옵시디언에서 MOC(Master of Control) 자동 생성 및 폴더 노트 활용 가이드](https://anpigon.tistory.com/454) (0) | 2024.02.08 |
| [옵시디언에서 AI 코파일럿 무료로 사용하기](https://anpigon.tistory.com/453) (0)                            | 2024.02.06 |