---
title: "<% tp.file.title %>"
level: "T5"
file_role: "concept_moc"

parent: ""

source_type: "moc"
process: final
---
# 🗺️ <% tp.file.title %> 



## 1. 📂 한자어휘 목록 (T03 Dictionary)

**"한자어휘"** 유형으로 분류된 개념 노트 목록입니다. (템플릿 파일 제외)

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "개념",
  join(filter(file.tags, (t) => length(split(t, "/")) >= 3), ", ") AS "3단계 태그",
  source_name AS "출처"
FROM ""
WHERE file_role = "dictionary"
  AND word_type = "한자어휘"
  AND !contains(file.name, "tp")
SORT file.name ASC
````

## 2. 🇰🇷 순우리말 목록

"순우리말" 유형으로 분류된 개념 노트 목록입니다.

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "개념",
  join(filter(file.tags, (t) => length(split(t, "/")) >= 3), ", ") AS "3단계 태그",
  source_name AS "출처"
FROM ""
WHERE file_role = "dictionary"
  AND word_type = "순우리말"
  AND !contains(file.name, "tp")
SORT file.name ASC
```

## 3. 🌐 영어 어휘 목록

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "개념",
  join(filter(file.tags, (t) => length(split(t, "/")) >= 3), ", ") AS "3단계 태그",
  source_name AS "출처"
FROM ""
WHERE file_role = "dictionary"
  AND word_type = "영어" 
  AND !contains(file.name, "tp")
SORT file.name ASC
```

## 4. 📚 서명(책/작품) 목록

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "개념",
  join(filter(file.tags, (t) => length(split(t, "/")) >= 3), ", ") AS "3단계 태그",
  source_name AS "출처"
FROM ""
WHERE file_role = "dictionary"
  AND word_type = "서명"
  AND !contains(file.name, "tp")
SORT file.name ASC
```

## 5. 👥 인물 목록

```dataview
TABLE WITHOUT ID
  link(file.path, file.name) AS "개념",
  join(filter(file.tags, (t) => length(split(t, "/")) >= 3), ", ") AS "3단계 태그",
  source_name AS "출처"
FROM ""
WHERE file_role = "dictionary"
  AND word_type = "인물"
  AND !contains(file.name, "tp")
SORT file.name ASC
```



## 2\. 📚 [영역]별 분류 (B. [영역] 태그 기준)

(안정적인 Level 2 범주 추출 로직 적용)

```dataview
LIST
FROM ""
WHERE file_role = "dictionary"
  AND source_name = "한자어휘사전"
  AND contains(tags, "영역/")
  AND length(map(filter(tags, (t) => startswith(t, "영역/") ), (t) => split(t, "/")[1])) > 0 
GROUP BY join(map(filter(tags, (t) => startswith(t, "영역/") ), (t) => split(t, "/")[1])) AS "분류 영역 (Level 2)"
SORT "분류 영역 (Level 2)" ASC
```

## 3\. 🧠 [개념]별 기능 분류 (C. [개념] 태그 기준)

(안정적인 Level 2 범주 추출 로직 적용)

```dataview
LIST
FROM ""
WHERE file_role = "dictionary"
  AND source_name = "한자어휘사전"
  AND contains(tags, "개념/")
  AND length(map(filter(tags, (t) => startswith(t, "개념/") ), (t) => split(t, "/")[1])) > 0 
GROUP BY join(map(filter(tags, (t) => startswith(t, "개념/") ), (t) => split(t, "/")[1])) AS "처리 기능 (Level 2)" 
SORT "처리 기능 (Level 2)" ASC
```

## 6. 📊 [영역] 태그별 분류 (카테고리별 필터링)

이 섹션은 노트에 부여된 '영역/' 태그의 Level 2를 기준으로 분류합니다.

### 6.1. 🏡 영역: 생활

```dataview
LIST file.link
FROM ""
WHERE file_role = "dictionary"
  AND contains(tags, "영역/생활")
  AND !contains(file.name, "tp")
SORT file.name ASC
```

