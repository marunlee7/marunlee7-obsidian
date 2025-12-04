---
aliases:
references: "{{url}}"
raw_published: {{selector:.writer_time}} 
published: <%*
  // raw_published 필드의 값을 가져옵니다.
  const rawDate = tp.frontmatter.raw_published;
  
  // 정규 표현식을 사용하여 날짜와 시간 패턴만 추출합니다.
  // 패턴: YYYY/MM/DD + 어떤 문자 + [HH:mm]
  const dateMatch = rawDate.match(/(\d{4}\/\d{2}\/\d{2}.*\[.*\])/);
  
  let cleanDate = '';
  
  if (dateMatch && dateMatch[1]) {
      // 추출된 문자열에서 불필요한 기호를 제거하고 형식을 변경합니다.
      cleanDate = dateMatch[1]
          .replace('[', '').replace(']', '').replace(/\//g, '-').trim();
      
      // 프론트매터의 'published' 필드를 업데이트하고 원본 필드 삭제 (자동 실행)
      app.fileManager.processFrontMatter(tp.file.path(true), (frontmatter) => {
          frontmatter.published = cleanDate;
          delete frontmatter.raw_published; 
      });
      // Templater는 필드에 직접 결과를 출력하지 않고 파일 매니저로 처리
      tR = cleanDate;
  } else {
      tR = '날짜 추출 실패';
  }
_%>
created: {{date:YYYY-MM-DD}}
modified: {{date:YYYY-MM-DD}}
author: "[[{{author}}]]"
tags:
{% for tag in tags -%}
  - "{{tag}}"
{% endfor %}
series_num:
links:
checkbox: false
read: false
---