---
date_daily: <% tp.file.title.slice(0,10) %>
tags:
  - DailyNotes
근무: 
감정: 
외식: 
생각: 
기타: 
리딩: <%*
const weekdays = {
    "월": "전광진 하루한자격언",
    "화": "정민교수 점검",
    "수": "정민교수 다선생 지식경영법",
    "목": "정석원 한자여행",
    "금": "고사성어 일촌맺기",
    "토": "북트레싱 작가방",
    "일": "박원길 한자암기박사"
};

// 요일 계산 함수
function getKoreanDay(dayNumber) {
    const koreanDays = ["일", "월", "화", "수", "목", "금", "토"];
    return koreanDays[dayNumber];
}

// 파일 제목에서 날짜 추출
const fileDate = tp.file.title.slice(0, 10); // YYYY-MM-DD 형식의 날짜
const dayNumber = moment(fileDate, "YYYY-MM-DD").day(); // 요일 번호 (0: 일요일, ..., 6: 토요일)
const todayKorean = getKoreanDay(dayNumber); // 한글 요일 계산

const keyValue = weekdays[todayKorean] || "키값 없음"; // 한글 요일에 해당하는 값 찾기

tR += keyValue;
%>
---
# <% tp.file.title.slice(0,10) %> <% todayKorean %>
<%*
const currentMoment = moment(tp.file.title, "YYYY-MM-DD");
tR += '❮ ';
tR += '[[' + currentMoment.format('YYYY|YYYY년') + ']]' + ' / ';
tR += '[[' + currentMoment.format('YYYY-MM|MM월') + ']]' + ' / ';
tR += '[[' + currentMoment.format('gggg-[W]ww') + '|' + currentMoment.format('ww[주]') + ']]';
tR += ' ❯';
tR += '\n';
tR += '❮❮ ';
currentMoment.add(-1, 'days');
tR += '[[' + currentMoment.format('YYYY-MM-DD') + ']]' + ' | 📆 ';
currentMoment.add(1, 'days');
tR += currentMoment.format('YYYY-MM-DD') + ' | ';
currentMoment.add(1, 'days');
tR += '[[' + currentMoment.format('YYYY-MM-DD') + ']]';
currentMoment.add(-1, 'days');
tR += ' ❯❯';
%>

## Quote
<% tp.web.random_picture("500", "Brompton") %>
<% tp.web.daily_quote() %>

## 오늘 생각정리 思日

- 
## 내일 기억할 일

- 

## 오늘 기억할 일

<%*
let yesterday = "20-에어리어/Journals/Daily/" + tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD");
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

## 오늘 끝내야 할 일
```tasks
due on or before <% tp.file.title.slice(0,10) %>
filter by function !task.file.folder.includes("90-Settings")
not done
sort by priority
```
### 업무 할 일 | 한자, 영어, 독서, 앱, 작업노트
```tasks
tag include #작업노트 
not done
```
### 개인할일 | 인생노트, 생각노트, 무비, 뮤직
```tasks
tag include #인생노트
```
### 반복 할 일
```tasks
is recurring
not done
has tags
```
### 언젠가 할 일
```tasks
# 이 쿼리는 계획 단계에 있는 구체적인 작업을 찾습니다.
# 마감일이 설정되지 않은 태스크만 선택
no due date

# 아직 완료되지 않은 태스크만 선택
not done

# 설명이 비어있지 않은 태스크만 선택
# ^$ 는 빈 문자열을 의미하는 정규표현식입니다.
# 이 정규표현식과 일치하지 않는 (즉, 내용이 있는) 태스크를 선택합니다.
description regex does not match /^$/

# 이 쿼리는 마감일이 없고, 완료되지 않았으며, 설명이 있는 모든 태스크를 표시합니다.
# 주로 아직 일정이 정해지지 않았지만 해야 할 일로 인식된 작업을 찾는 데 유용합니다.
# 생성일 기준으로 오름차순 정렬 (가장 최근 생성된 항목이 아래로)
sort by created
```
### 오늘 완료한 일
```tasks
done <% tp.file.title.slice(0,10) %>
```

## 오늘 작성한 노트
```dataview
List FROM "" WHERE file.cday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.ctime desc
limit 5
```
## 오늘 수정한 노트
```dataview
List FROM "" WHERE file.mday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.mtime desc
limit 5
```