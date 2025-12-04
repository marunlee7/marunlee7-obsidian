---
cover_url: https://yt3.googleusercontent.com/WZjIacAUqQYoMPk8iH3e6voix295sUe2T79aUg69MTm5lDLN1Eb8dsVZeqggw2M2nY39HvQMRQ=w2120-fcrop64=1,00005a57ffffa5a8-k-c0xffffffff-no-nd-rj
publisher:
category: 앱스
title: "Paul Dickson's Ko-fi Shop"
published:
level: T02
file_role: article_atom
status: planned # 최종 확정: planned. Task 관리 기본값.
priority: medium
process: "" # T01은 process 필드 사용 안 함 (빈 값 유지)
source_name: Paul Dickson's Ko-fi Shop
source_author: "[[폴 딕슨]]"
source_type: "book"
references:
  - https://www.youtube.com/channel/UCkIzFxrhWbf2Crr-BBYtdgw
  - https://obsidianaitools.com/
  - https://ko-fi.com/motion2082/shop
tags: [출처/외부_정보/도서_단행본]
---
# Paul Dickson's Ko-fi Shop
```table-of-contents
style: nestedList
minLevel: 0
maxLevel: 0
includeLinks: true 
debugInConsole: false
```
## 📕 작업노트
```dataview
TABLE WITHOUT ID
  link(file.path, substring(file.name, 1, 10)) AS "제목",
  작업노트
FROM ""
WHERE 작업노트 != null
  AND contains(file.tags, "옵시디언/템플릿/PaulDickson")
SORT file.mtime DESC
```

## 📕 사색
```dataview
TABLE WITHOUT ID
  link(file.path, substring(file.name, 1, 10)) AS "제목",
  사색
FROM ""
WHERE 사색 != null
  AND contains(file.tags, "옵시디언/템플릿/PaulDickson")
SORT file.mtime DESC
```

## 📕 MOC
```dataview
table without id
	link(file.path, substring(file.name, 0, 44)) as "제목",  
	choice(checkbox, "❗", "") AS "❗",
	choice(read, "✓", "") AS "✓",
	dateformat(created "yy-MM-dd") as "시작일",
	dateformat(modified, "yy-MM-dd") as "종료일"
FROM "" 
WHERE contains(file.tags, "옵시디언/템플릿/PaulDickson")
	AND !contains(file.folder, "90-Settings")
	AND !contains(file.folder, "40-아카이브")
	AND !contains(file.tags, "moc") 
	AND !contains(file.tags, "toc")
SORT file.mtime desc
//SORT file.name desc
//SORT file.name asc
```
%% 정규식으로 10번째 글자부터 4글자만 추출 %%

## 📕 소개

옵시디언 툴 개발자.
몇가지 다운로드 해서 적용해야 함. :: 인상적인 구절 <br>이 볼트를 구매하시면 채널을 후원하는 동시에 <br>성공으로 가는 길을 빠르게 열 수 있습니다.

## 📕 목차


