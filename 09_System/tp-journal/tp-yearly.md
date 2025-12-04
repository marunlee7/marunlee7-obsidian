---
歲: 56세
餘命: 25년
居住地: 장안읍
aliases:
  - "2025"
source_name: tp-yearly
---
# 2025

## 중요한 날

```dataview
TABLE without id
	file.link as 날짜,
	achievement as 성과
FROM "20-에어리어/Journals/Daily"
WHERE important_date = true AND contains(file.name, "遽忘觀理")
```

## 읽은 책 리스트
```dataview
TABLE without id
rows.reading_book as "책 제목",
rows.date_daily as "읽은 날짜"
FROM "20-에어리어/Journals/Daily"
WHERE contains(file.name, "遽忘觀理") AND reading_book != null
FLATTEN reading_book
GROUP BY reading_book
```

| 요일       | 내용                   |     |
| -------- | -------------------- | --- |
| 遽忘觀理-1월  | ![[遽忘觀理-01#^review]] |     |
| 遽忘觀理-2월  | ![[遽忘觀理-02#^review]] |     |
| 遽忘觀理-3월  | ![[遽忘觀理-03#^review]] |     |
| 遽忘觀理-4월  | ![[遽忘觀理-04#^review]] |     |
| 遽忘觀理-5월  | ![[遽忘觀理-05#^review]] |     |
| 遽忘觀理-6월  | ![[遽忘觀理-06#^review]] |     |
| 遽忘觀理-7월  | ![[遽忘觀理-07#^review]] |     |
| 遽忘觀理-8월  | ![[遽忘觀理-08#^review]] |     |
| 遽忘觀理-9월  | ![[遽忘觀理-09#^review]] |     |
| 遽忘觀理-10월 | ![[遽忘觀理-10#^review]] |     |
| 遽忘觀理-11월 | ![[遽忘觀理-11#^review]] |     |
| 遽忘觀理-12월 | ![[遽忘觀理-12#^review]] |     |