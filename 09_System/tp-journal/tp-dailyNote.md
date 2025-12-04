---
date_daily: <% tp.file.title.slice(0,10) %>
achievement: ""
reading_book: <%*
const weekdays = {
    "월": "전광진 하루한자격언",
    "화": "다산선생 지식경영법",
    "수": "박원길 한자암기박사",
    "목": "정석원 한자여행",
    "금": "김병기의 알쏭어 달쏭사",
    "토": "옵시디언 저널 점검",
    "일": "정민교수 점검"
};
function getKoreanDay(dayNumber) {
    const koreanDays = ["일", "월", "화", "수", "목", "금", "토"];
    return koreanDays[dayNumber];
}
const fileDate = tp.file.title.slice(0, 10);
const dayNumber = moment(fileDate, "YYYY-MM-DD").day();
const todayKorean = getKoreanDay(dayNumber);
const keyValue = weekdays[todayKorean] || "키값 없음";
tR += keyValue;
%>
emotion: ""
important_date: ""
---
# <% tp.file.title.slice(0,10) %>
<%*
    const currentMoment = moment(tp.file.title, "YYYY-MM-DD");
    tR += '❮ ';
	tR += '[[' + currentMoment.format('YYYY|YYYY년') + ']]' + ' / ';
	tR += '[[' + currentMoment.format('YYYY-MM|MM월') + ']]' + ' / ';
	tR += '[[' + currentMoment.format('gggg-[W]ww') + '|' + currentMoment.format('ww[주]') + ']]';
	tR += ' ❯';
	tR += '\n';
    tR += '❮❮ ';
    // 어제
    currentMoment.add(-1,'days');
    tR  += '[[' + currentMoment.format('YYYY-MM-DD') + '|' + currentMoment.format('YYYY-MM-DD(ddd)') + ']]' + ' | 📅 ';
    // 오늘
    currentMoment.add(1,'days');
    tR += currentMoment.format('YYYY-MM-DD(ddd)') + ' | ';
    // 내일
    currentMoment.add(1,'days');
    tR += '[[' + currentMoment.format('YYYY-MM-DD') + '|' + currentMoment.format('YYYY-MM-DD(ddd)') + ']]';
    // currentMoment 원위치
    currentMoment.add(-1,'days');
    tR += ' ❯❯';
%>

<% tp.web.daily_quote() %>
## 내일 기억할 일

- 
## 오늘 기억할 일

<%*
let yesterday = "07_Journal/Daily/" + tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD");
let section = "## 내일 기억할 일";
let should_include = false;
let sectionContent = "";

let yfile = tp.file.find_tfile(yesterday);
if(yfile) {
    const content = await app.vault.read(yfile);
    if(content.includes(section)) {
        let startIndex = content.indexOf(section) + section.length;
        let endIndex = content.indexOf('\n##', startIndex);
        endIndex = endIndex === -1 ? content.length : endIndex;
        sectionContent = content.substring(startIndex, endIndex).trim();
        should_include = sectionContent.length > 0;
    }
}

tR += should_include ? sectionContent : "없습니다😀";
%>

## 아침
### 오늘의 확언
- 
### 오늘의 목표
- 
- 
- [ ] 
- [ ] 

### 할 일 추가하기

- [ ] 

## 오늘 끝내야 할 일
```tasks
due on or before <% tp.file.title.slice(0,10) %>
filter by function task.file.folder.includes("07_Journal/Daily")
filter by function !task.file.folder.includes("09_System/tp")
not done
sort by priority
```
### 업무 할 일
```tasks
tag include #업무 
```
### 개인 할 일

### 반복 할 일
```tasks
is recurring
not done
has tags
```

### 언젠가 할 일
```tasks
no due date
not done
description regex does not match /^$/
```

### 오늘 완료한 일
```tasks
done <% tp.file.title.slice(0,10) %>
```

## 독서
- 읽은 책
- 읽은 페이지

## 운동
- 

## 하루 마무리
### 오늘 배운 것들
- 
- 
### 오늘 감사한 일
>[!note]
>
### 일기

## 오늘 작성한 노트
```dataview
List FROM "" WHERE file.cday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.ctime desc
limit 10
```

## 오늘 수정한 노트
```dataview
List FROM "" WHERE file.mday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.mtime desc
limit 10
```