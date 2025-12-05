---
title: tp-monthly
status: planned
priority: medium
process: raw
source_name: tp-monthly
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
# tp-Monthly

## 운동 습관 기르기

```tracker
searchType: frontmatter
searchTarget: exercise
folder: 20-에어리어/Journals/Daily
datasetName: 운동 습관 기르기
month:
	startWeekOn: 'sun'
	headerMonthColor: orange
	initMonth: 遽忘觀理
	mode: annotation
	annotation: 🧘🏻
```

## 독서 습관 기르기

```tracker
searchType: frontmatter
searchTarget: reading_page
datasetName: 읽은 페이지
folder: 20-에어리어/Journals/Daily
line:
	title: 책 읽는 습관
	xAxisLabel: 날짜
	yAxisLabel: 읽은 페이지
	yAxisUnit: 페이지
	lineColor: red
	pointColor: red
	pointBorderWidth: 2
	pointBorderColor: red
	showLegend: True
```

## 요약

```tracker
searchType: frontmatter
searchTarget: reading_page
datasetName: 읽은 페이지
folder: 20-에어리어/Journals/Daily
startDate: 2001-01-01
endDate: Invalid date

summary:
	template: "적게 읽은 날: {{min()::i}}페이지\n많이 읽은 날: {{max()::i}}페이지\n독서한 날: {{numDaysHavingData()::i}}일"

```
