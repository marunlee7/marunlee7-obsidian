---
weekly_summary: 
source_name: tp-weeklyReview
---
# tp-Weekly
## 지난 주 반성

## 이번 주 계획
### 지난 주에서 가져온 계획

없습니다😀

### 이번 주 계획

## 다음 주 계획

## 이번주 요약

|요일| 날짜 | 내용 |
|---|---|---|
|월|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |   
|화|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(1, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |   
|수|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(2, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |  
|목|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(3, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |   
|금|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(4, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |   
|토|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(5, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |   
|일|`$=moment("tp-Weekly", "YYYY-[W]WW").startOf('isoWeek').add(6, 'days').format("MM-DD")`| ![[-0NaN--NaN--NaN#^summary]] |  

## 데일리 리뷰
```dataviewjs
const currentNoteTitle = dv.current().file.name;
const weekNumberMatch = currentNoteTitle.match(/(\d{4}-W\d{2})/);

if (weekNumberMatch) {
    const weekNumber = weekNumberMatch[0];
    const dailyNoteFolder = '"20-에어리어/Journals/Daily"';
    
    dv.pages(dailyNoteFolder)
        .where(page => {
            const pageDate = moment(page.file.name, "YYYY-MM-DD");
            return pageDate.isValid() && pageDate.isoWeek() === moment(weekNumber, "YYYY-[W]WW").isoWeek();
        })
        .forEach(page => {
            const dailyReview = page.리뷰 || "없음";
            dv.paragraph(`**${page.file.name}**: ${dailyReview}`);
        });
} else {
    dv.paragraph("이 노트의 제목에 ISO 주 정보가 포함되지 않았습니다.");
}
```

