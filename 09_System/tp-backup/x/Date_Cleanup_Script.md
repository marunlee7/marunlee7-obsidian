---
title: Date_Cleanup_Script
status: planned
priority: medium
process: raw
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
# Date_Cleanup_Script
<%*
// 1. 현재 노트의 프론트매터(YAML)를 가져옵니다.
//    'rawInput' 필드의 값은 rawInput 변수에 저장됩니다.
const rawInput = tp.frontmatter['rawInput']; 
const filePath = tp.file.path(true);

tR += `\n\n--- 디버깅 시작 ---\n`;
tR += `원시 rawInput 값: ${rawInput}\n`;

if (rawInput) {
    // 2. 정규 표현식으로 'YYYY/MM/DD' 패턴만 추출합니다.
    //    이 패턴은 날짜와 / 문자만 포함하며, 시간 부분은 제외합니다.
    const dateMatch = rawInput.match(/(\d{4}\/\d{2}\/\d{2})/);

    let cleanDate = '';

    if (dateMatch && dateMatch[1]) {
        // 3. 추출된 날짜에서 '/'를 '-'로 바꾸고 공백을 제거합니다.
        cleanDate = dateMatch[1].replace(/\//g, '-').trim();
        
        tR += `추출된 날짜: ${cleanDate}\n`;

        try {
            // 4. 파일 매니저를 통해 프론트매터 필드를 갱신/삭제합니다.
            app.fileManager.processFrontMatter(filePath, (frontmatter) => {
                // published 필드를 정리된 날짜로 갱신
                frontmatter.published = cleanDate;
                // 원본 필드 'rawInput' 삭제 (선택 사항)
                delete frontmatter['rawInput']; 
            });
            
            tR += `✅ 날짜 정리 완료: published가 ${cleanDate}로 업데이트되었습니다.\n`;
        } catch (error) {
            tR += `❌ 프론트매터 업데이트 중 에러 발생: ${error.message}\n`;
        }
        
    } else {
        tR += `❌ 날짜 패턴을 찾을 수 없습니다.\n`;
    }
} else {
    tR += `⚠️ 'rawInput' 필드를 찾을 수 없습니다. (값이 없거나 필드명이 다름)\n`;
}
tR += `--- 디버깅 종료 ---`;
_%>