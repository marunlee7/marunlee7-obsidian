---
published: 2024-01-27T23:33:29+09:00
aliases: []
source_name: 옵시디언 Flowershow 플러그인으로 무료 퍼블리시 방법
references: https://anpigon.tistory.com/448
---
# 옵시디언 Flowershow 플러그인으로 무료 퍼블리시 방법

Flowershow 플러그인은 Obsidian 노트를 [Flowershow 템플릿](https://github.com/datopian/flowershow) 을 사용하여 [Vercel](https://vercel.com/) 을 통해 게시할 수 있게 해주는 도구입니다.  
  
이 글은 [Flowershow 문서](https://flowershow.app/docs/publish-howto) 를 참조하여 작성되었습니다.

## 초기 설정

### 1\. GitHub 계정이 없다면 여기에서 생성하세요.

### 2\. Vercel 계정이 필요합니다. 여기에서 GitHub 계정으로 가입하세요.

### 3\. Flowershow 저장소에 접속해 “Quick Clone and deploy” 섹션의 “Deploy” 버튼을 클릭하세요.

![etc-image-0](https://blog.kakaocdn.net/dn/bMX22m/btsD2GvX2XP/yuvZAkLqZb8EksBaRfXr6k/img.png)

etc-image-0

  
이후 Vercel의 “Create Git Repository” 페이지가 열리며, 여기서 저장소 이름(Repository Name)을 입력한 후 "Create"를 클릭해 GitHub 계정에 템플릿 저장소를 복사하고 Vercel에 배포하세요.

![etc-image-1](https://blog.kakaocdn.net/dn/buCdGL/btsD6xRQPum/JdMWekBkdAwdIwNYqUZE81/img.png)

etc-image-1

### 4\. GitHub에서 개인 액세스 토큰을 생성합니다.

GitHub에 로그인한 상태에서 [새 개인 액세스 토큰 페이지](https://github.com/settings/tokens/new?scopes=repo) 로 이동하세요. 토큰의 유효 기간을 "No expiration"으로 설정할 수 있습니다.

![etc-image-2](https://blog.kakaocdn.net/dn/dp4GZC/btsD7k5VsFO/KkxipqQKo14dr5yImaSMi0/img.png)

etc-image-2

  
"Generate token"을 클릭하고, 다음 페이지에서 표시된 액세스 토큰을 복사하세요.  

![etc-image-3](https://blog.kakaocdn.net/dn/YnsZm/btsD4vNKRtG/wKfh0IqOsUH0nYaGjNvEt0/img.png)

etc-image-3

### 5\. Obsidian에서 Flowershow 플러그인을 설치하고 활성화한 후 설정을 엽니다.

GitHub 사용자 이름과 3단계에서 생성한 리포지토리 이름을 입력하세요. 그리고 4단계에서 복사한 액세스 토큰을 붙여넣으세요.

![etc-image-4](https://blog.kakaocdn.net/dn/nqQ8N/btsD3bbrYOm/l9KGdLx3Qbpo0K4m5bcwE0/img.png)

etc-image-4

### 6\. 첫 노트를 게시해 보세요.

Obsidian에서 새 노트를 생성합니다.

### 7\. Windows/Linux에서는 +, Mac에서는 +를 눌러 명령 팔레트를 열고 “Flowershow: Publish Single Note” 명령을 찾아 실행하세요.

### 8\. Vercel 의 사이트 URL로 이동하세요.

아무 것도 보이지 않는다면 잠시 기다린 후 새로 고쳐 보세요. Visit 버튼을 클릭하면 방금 생성한 노트를 포함하는 Flowershow 사이트를 볼 수 있습니다.

![etc-image-5](https://blog.kakaocdn.net/dn/bxXvTe/btsD0IulJNK/BLpzFs2zsEmhnOamsKqKE0/img.png)

etc-image-5

  
Vercel에서 도메인을 변경하고 싶다면, Settings > Domains에 접속해 Edit 버튼을 클릭하여 수정하세요.  

![etc-image-6](https://blog.kakaocdn.net/dn/cgS7DG/btsD0IOC1Mx/eFjF89tGyBC7zepiDY1I3K/img.png)

etc-image-6

## Flowershow 플러그인

### 플러그인 명령어

- `Flowershow: Publish Single Note`: 현재 노트를 Flowershow 사이트에 게시합니다.
- `Flowershow: Publish All Notes`: 볼트에 있는 모든 노트를 Flowershow 사이트에 게시합니다.

### 플러그인 리본 명령

플러그인 설치 후 Obsidian 리본에 새로운 🌱 아이콘이 추가됩니다. 이 아이콘을 클릭하면 다음 정보를 포함하는 출판 상태 패널이 표시됩니다.

- **Published**: Flowershow 사이트에 게시된 노트의 총 수
- **Changed**: 로컬에서 편집된 후 게시된(Published) 노트의 총 수 (+ 버튼을 눌러 게시)
- **Unpublished**: Obsidian 저장소에는 있으나 아직 사이트에 게시되지 않은 새 노트의 수 (+ 버튼을 눌러 게시)
- **Deleted**: Obsidian에서 삭제되었으나 사이트에 아직 게시된 노트의 수 (+ 버튼을 눌러 게시를 취소)

### 노트 Frontmatter 설정

- `isDraft`: 노트를 Flowershow 사이트에 게시하지 않으려면 `true` 로 설정하세요. 이미 게시된 경우에는 게시를 취소합니다. (기본값은 `false`).

## 마치며

다음은 제가 Flowershow 플러그인을 사용하여 배포한 사이트입니다.  
[digital-flora-show.vercel.app](https://digital-flora-show.vercel.app/)  

## 관련 글

- [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164)
- [DGitHub과 Netlify를 사용해서 블로그 만들기 (with Obsidian Digital Garden Plugin)](https://anpigon.tistory.com/167)

---

[![etc-image-7](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=anpigon&button_colour=FFDD00&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff)](https://www.buymeacoffee.com/anpigon)

*or*  
[\[카카오페이로 후원하기\]](https://anpigon.github.io/buymeacoffee/) [\[토스페이로 후원하기\]](https://toss.me/anpigon/)

### ' > ' 카테고리의 다른 글

| [티스토리 Open API 서비스 종료 대비: 새로운 블로그 연동 방안 탐색](https://anpigon.tistory.com/451) (3) | 2024.01.30 |
| --- | --- |
| [옵시디언 무료 퍼블리시 방법(👍추천): Cloudflare, Quartz, Flowershow Plugin](https://anpigon.tistory.com/449) (17) | 2024.01.28 |
| [옵시디언 무료 퍼블리시 서버 비용 비교](https://anpigon.tistory.com/447) (0) | 2024.01.27 |
| [옵시디언 사용자 필독! Google Tasks 플러그인으로 생산성을 두 배로!](https://anpigon.tistory.com/446)(0) | 2024.01.19 |
| [무료 AI LM Studio를 옵시디언에서 활용하는 방법(feat. Copilot)](https://anpigon.tistory.com/442) (0) | 2024.01.14 |

,

댓글 2

- - [안피곤](https://anpigon.tistory.com/)
		퍼블리시 후에도 업데이트가 되지 않는 문제는 여러 가지 원인으로 발생할 수 있습니다. 아래 몇 가지 점검 사항을 확인해 보세요:  
		  
		\- GitHub 리포지토리명을 정확하게 연결했는지 확인하세요.  
		\- 연결한 GitHub 리포지토리에 업데이트한 파일이 제대로 업로드되었는지 확인하세요.  
		\- Vercel의 배포 로그에 오류 메시지가 없는지 확인하세요.  
		  
		그래도 업데이트가 되지 않는다면, 증상과 상세한 내용을 알려주시면 제가 도움드릴 수 있을 것 같습니다.
		2024\. 8. 4. 20:37 [답글](https://anpigon.tistory.com/#)
		- [신고](https://anpigon.tistory.com/#)
		- [링크복사](https://anpigon.tistory.com/#)