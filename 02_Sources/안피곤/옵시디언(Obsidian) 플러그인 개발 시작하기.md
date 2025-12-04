---
published: 2022-03-13T11:11:53+09:00
aliases: []
source_name: 옵시디언(Obsidian) 플러그인 개발 시작하기
references: https://anpigon.tistory.com/158
---
# 옵시디언(Obsidian) 플러그인 개발 시작하기

**메인 볼트에서는 플러그인을 개발하지 마세요.**  
**테스트용 볼트를 생성해서 플러그인을 개발하세요.**

## 옵시디언 팀의 공식 리소스:

- [https://github.com/obsidianmd/obsidian-sample-plugin](https://github.com/obsidianmd/obsidian-sample-plugin)
- [https://github.com/obsidianmd/obsidian-api](https://github.com/obsidianmd/obsidian-api)

## STEP 1: 옵시디언 샘플 플러그인 템플릿 사용하기

1. [깃헙 옵시디언 샘플 플러그인 리포지토리](https://github.com/obsidianmd/obsidian-sample-plugin) 에 접속합니다.
2. **Use thie template** 를 클릭 합니다.  
	![etc-image-0](https://blog.kakaocdn.net/dn/b4Z8Cl/btrvQhDLiTZ/coXcA5lEkOmvuaWureNYSK/img.png)
	etc-image-0
3. **Repository name** 에 옵시디언 플러그인 이름을 입력합니다. 옵시디언 플러그인은 보통obsidian-로 시작합니다. 예를 들면obsidian-awsome-plugin로 작성합니다.  
	![etc-image-1](https://blog.kakaocdn.net/dn/qN2Zk/btrvNHb63qG/pbEyZ10BKuC6pwHS8onHN1/img.png)
	etc-image-1
4. 마지막으로 **Create repository from template** 를 클릭합니다.

## STEP 2: 방금 만든 저장소 다운로드하기

1. 방금 만든 저장소에서 Code를 클릭하고, URL를 복사합니다.  
	![etc-image-2](https://blog.kakaocdn.net/dn/4qNFF/btrvNH4g1m5/ZNuR0pitjaUDf7rwxnfl51/img.png)
	etc-image-2
2. 터미널을 열고 옵시디언 테스트 볼트의 플러그인 폴더로 이동합니다.  
	cd path/to/vault/.obsidian/plugins
3. 플러그인 폴더에 소스 코드를 다운로드합니다.  
	git clone git@github.com:anpigon/obsidian-awsome-plugin.git

## STEP 3: 플러그인 빌드하기

1. 플러그인 폴더로 이동합니다.  
	cd path/to/vault/.obsidian/plugins/obsidian-awsome-plugin
2. npm dependencies를 설치합니다.  
	npm i또는yarn
3. 코드를 빌드합니다.  
	npm run dev또는yarn dev

## STEP 4: 옵시디언에서 플러그인 활성화하기

1. 옵시디언의 "설정 > 서드파티 플러그인"으로 이동합니다.
2. 설치된 플러그인 오른쪽에 새로고침을 누르면 **Sample Plugin** 이 나타납니다.
3. **Sample Plugin** 오른쪽에 토글 버튼을 클릭하여 플러그인을 활성화합니다.  
	![etc-image-3](https://blog.kakaocdn.net/dn/bqDeTT/btrvMIbixcf/2ELf39DQW0YS9xhAmvZ360/img.png)
	etc-image-3

## STEP 5: 플러그인 이름 변경하기

manifest.json파일을 수정하여 플러그인 이름을 변경합니다.  
매니페스트 파일은 플러그인 정보를 가지고 있는 파일입니다.  
에디터에서manifest.json파일을 편집합니다.

```json
{
    "id": "obsidian-awesome-plugin",
    "name": "Awesome Plugin",
    "version": "1.0.1",
    "minAppVersion": "0.12.0",
    "description": "This is a sample plugin for Obsidian. This plugin demonstrates some of the capabilities of the Obsidian API.",
    "author": "Obsidian",
    "authorUrl": "https://obsidian.md",
    "isDesktopOnly": false
}
```
- id는 다른 옵시디언 플러그인과 겹치지 않도록 고유값을 작성합니다.
- name는 옵시디언 플러그인 이름입니다.
- minAppVersion는 플러그인이 실행 가능한 옵시디언 최소 버전입니다.
- description는 플러그인에 대한 자세한 설명입니다.
- isDesktopOnly플러그인이 NodeJS 또는 Electron API를 사용하는지 여부를 나타냅니다. 따라서isDesktopOnly가true이면 모바일앱에서는 사용할 수 없습니다.

매니패스트 파일을 수정하고package.json파일도 매니패스트와 정보가 일치하게 수정합니다. 사실manifest.json와package.json의 정보가 일치하지 않아도 크게 문제될 것은 없습니다.

## STEP 6: 플러그인 코드 수정하기

1. VSCode에서main.ts파일을 편집합니다.
2. 아래와 같이 리본 아이콘을 추가하는 코드 라인을 찾습니다.  
	![etc-image-4](https://blog.kakaocdn.net/dn/cg43qE/btrvPgd2Br8/KItKCUEKH7r1L8LbegC6v0/img.png)
	etc-image-4
3. 위 코드를 다음과 같이 바꿔보세요.
	```haxe
	new Notice("Hello, world!");
	```
4. 플러그인 코드를 빌드합니다.npm run dev
5. 코드가 수정된 플러그인을 다시 로드하기 위해서, 옵시디언 "설정 > 서드파티 플러그인"에서 플러그인을 비활성화 했다가 다시 활성화합니다.
6. 왼쪽 사이드바에서 주사위 아이콘을 클릭합니다. Hello, world!라고 알림 메시지가 표시되는지 확인합니다.  
	![etc-image-5](https://blog.kakaocdn.net/dn/cfTbMv/btrvOgFkoaf/cN5zIEAdhvcRIC90CQSAbK/img.png)
	etc-image-5

## STEP 7: 코드 수정하면 플러그인 자동으로 다시 로드하기

- 핫 리로드 옵시디언 플러그인:[https://github.com/pjeby/hot-reload](https://github.com/pjeby/hot-reload)
1. 옵시디언 플러그인 폴더.obsidian/plugins/에 [hot-reload](https://github.com/pjeby/hot-reload) 를 다운로드합니다.
2. 그리고 서드파티 플러그인에서 **Hot Reload** 플러그인을 활성화합니다.  
	![etc-image-6](https://blog.kakaocdn.net/dn/T2ZQN/btrvRzqEaKV/CGQ5ooPRDV09r1dRE9CAs1/img.png)
	etc-image-6
3. 이제는 코드를 수정하면 플러그인이 자동으로 다시 로드됩니다.

END.

> 이 글은 스팀잇에서 작성하였습니다.  
> https://steemit.com/hive-137029/@anpigon/started-obsidian-plugin-development

### ' > ' 카테고리의 다른 글

| [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164) (0) | 2022.03.30 |
| --- | --- |
| [Shell commands 플러그인을 사용하여 git 동기화하기](https://anpigon.tistory.com/159) (0) | 2022.03.13 |
| [옵시디언 스팀잇 플러그인 개발](https://anpigon.tistory.com/156) (4) | 2022.03.05 |
| [Dropbox와 github를 사용해서 옵시디언(Obsidian) 백업 및 동기화(Sync)하기](https://anpigon.tistory.com/155) (2) | 2022.02.26 |
| [노션에서 옵시디언(Obsidian) 노트앱으로 이사 중](https://anpigon.tistory.com/153) (2) | 2022.02.21 |

, , ,

댓글 0