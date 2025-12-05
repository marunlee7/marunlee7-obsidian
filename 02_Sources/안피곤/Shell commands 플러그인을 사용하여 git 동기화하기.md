---
title: Shell commands 플러그인을 사용하여 git 동기화하기
aliases: []
published: 2022-03-13T23:58:45+09:00
status: planned
priority: medium
process: raw
source_name: Shell commands 플러그인을 사용하여 git 동기화하기
action_required: link_to_t04
difficulty:	good
satisfaction: 3
references: https://anpigon.tistory.com/159
---
# Shell Commands 플러그인을 사용하여 Git 동기화하기

close

![프로필 배경](https://tistory1.daumcdn.net/tistory/3123725/skin/images/dropdown-profile_bg.jpg)

[![프로필 로고](https://tistory1.daumcdn.net/tistory/3123725/attach/c2f3bb33b5b34c3ea4b0897a7a3e1245)](https://anpigon.tistory.com/)

[안피곤 성장블로그](https://anpigon.tistory.com/)

**목차**

## Git-sync 스크립트 작성하기

logseq에서 제작한 [git-auto](https://github.com/logseq/git-auto) 스크립트를 수정하여 사용합니다.

```bash
#!/usr/bin/env bash

 

server=origin

branch=$(git rev-parse --abbrev-ref HEAD)

 

get-commit-message() {

  local commit_message=$(git diff --name-only HEAD~1..HEAD)

  commit_message=$(echo "${commit_message}" | sed -e 's/^.*\///')

  echo "${commit_message}"

}

 

auto-commit-and-push() {

  if ! [[ $(git status) =~ "working tree clean" ]]; then

    git add .

    git commit -m "$(get-commit-message)"

    git pull --rebase

    git push "${server}" "${branch}"

  fi

}

 

auto-commit-and-push
```

옵시디언 볼트 루트 폴더에 `git-sync` 파일을 작성합니다.  
그리고 실행 권한을 부여합니다.

```dart
chmod +x ./git-sync
```

## Shell Commands 플러그인 설치하기

![Shell commands|500](https://i.imgur.com/2jm0O9u.png)

  
그리고 Shell commands 플러그인을 설치하고 활성화합니다.

## Git-sync 명령어 추가하기

![Shell commands|500](https://i.imgur.com/6enmO3w.png)

  
그다음 Shell commands 설정에 들어가서 New command를 버튼을 누릅니다.  
그리고 `./git-sync` 명령어를 추가하고 단축키를 지정합니다.

이제 단축키를 누르거나 git-sync 명령어를 실행하면 git 업로드가 실행됩니다.

### ' > ' 카테고리의 다른 글

| [옵시디언 책 검색 플러그인 (Book Search Plugin v0.1.0)](https://anpigon.tistory.com/165) (8) | 2022.04.07 |
| --- | --- |
| [Digital Garden 플러그인: 나만의 디지털 가든 만들기](https://anpigon.tistory.com/164) (0) | 2022.03.30 |
| [옵시디언(Obsidian) 플러그인 개발 시작하기](https://anpigon.tistory.com/158) (0) | 2022.03.13 |
| [옵시디언 스팀잇 플러그인 개발](https://anpigon.tistory.com/156) (4) | 2022.03.05 |
| [Dropbox와 github를 사용해서 옵시디언(Obsidian) 백업 및 동기화(Sync)하기](https://anpigon.tistory.com/155) (2) | 2022.02.26 |

, , , , , ,

댓글 0