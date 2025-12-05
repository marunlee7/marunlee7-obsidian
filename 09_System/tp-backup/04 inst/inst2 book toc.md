---
title: inst2 book toc
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
# Inst2 Book Toc
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
  link(file.path, substring(file.name, 0, 2)) AS "제목",
  작업노트
FROM ""
WHERE 작업노트 != null
  AND contains(file.tags, "T03노트생성최종완결태그마스터목록")
SORT file.mtime DESC
```

## 📕 사색
```dataview
TABLE WITHOUT ID
  link(file.path, substring(file.name, 0, 2)) AS "제목",
  사색
FROM ""
WHERE 사색 != null
  AND contains(file.tags, "T03노트생성최종완결태그마스터목록")
SORT file.mtime DESC
```

## 📕 MOC
```dataview
table without id
	link(file.path, substring(file.name, 0, 30)) as "제목",  
	choice(checkbox, "❗", "") AS "❗",
	choice(read, "✓", "") AS "✓"
FROM "" 
WHERE contains(file.tags, "T03노트생성최종완결태그마스터목록")
	AND !contains(file.folder, "90-Settings")
	AND !contains(file.folder, "40-아카이브")
	AND !contains(file.tags, "moc") 
	AND !contains(file.tags, "toc") 
	AND !contains(file.tags, "📚독서")
//SORT file.name asc
//SORT file.name desc
//SORT file.mtime desc
sort published desc
```

## 📕 소개



## 📕 목차

