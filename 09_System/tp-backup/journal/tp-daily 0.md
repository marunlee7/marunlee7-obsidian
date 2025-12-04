---
date_daily: <% tp.file.title.slice(0,10) %>
tags: [DailyNotes]
toRead: <%*
const weekdays = {
    "월": "전광진 하루한자격언",
    "화": "정민교수 점검, 다산선생 지식경영법",
    "수": "B-책벌레의 공부, B-황종택의 新온고지신",
    "목": "정석원 한자여행",
    "금": "고사성어 일촌맺기",
    "토": "북트레싱 작가의방",
    "일": "박원길 한자암기박사"
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
---
# <% tp.file.title.slice(0,10) %> <% todayKorean %>

## 📘 내일 기억할 일


## 📘 오늘 기억할 일

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

## 📙 오늘 끝내야 할 일
```tasks
due on or before <% tp.file.title.slice(0,10) %>
filter by function !task.file.folder.includes("90-Settings")
filter by function !task.file.folder.includes("life-disciplines-projects-main")
not done
sort by priority
hide backlink
hide task count
```
> [!quote]- 클리핑(Clipping)
> 클리핑(Clipping)
```tasks
tag include #클리핑 
not done
hide task count
hide backlink
```
> [!quote]- 작업노트
> 작업노트
```tasks
tag include #작업노트 
not done
hide task count
hide backlink
```
> [!quote]- 사색
> 사색
```tasks
tag include #사색
not done
hide task count
hide backlink
```
> [!tip]- 반복해서 할 일
> 반복해서 할 일
```tasks
is recurring
filter by function !task.file.folder.includes("life-disciplines-projects-main")
not done
has tags
hide backlink
hide task count
```
> [!important]- 언젠가 할 일
> 언젠가 할 일
```tasks
# 이 쿼리는 계획 단계에 있는 구체적인 작업을 찾습니다.
# 마감일이 설정되지 않은 태스크만 선택
filter by function !task.file.folder.includes("life-disciplines-projects-main")
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
hide task count
hide backlink
filter by function !task.file.folder.includes("가이드라인")
```
> [!important]- 오늘 완료한 일
> 오늘 완료한 일
```tasks
done <% tp.file.title.slice(0,10) %>
hide task count
hide backlink
```
## 오늘 작성한 노트
```dataview
List FROM "" WHERE file.cday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.ctime desc
limit 100
```
## 오늘 수정한 노트
```dataview
List FROM "" WHERE file.mday = date("<% tp.date.now('YYYY-MM-DD') %>") SORT file.mtime desc
limit 20
```