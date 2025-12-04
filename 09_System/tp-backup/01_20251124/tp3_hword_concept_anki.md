---
<%*
const parts = tp.file.title.split('_');
// 💡 (안정성 강화) 값이 없을 경우 undefined 대신 빈 문자열("")을 할당하도록 수정
const hanja = parts[0] || "";
const sound = parts[1] || "";
const extra = parts[2] || "";
%>aliases:
  - "<% sound %>(<% hanja %>)"
level: "T03_Dictionary"
file_role: "concept_dictionary"

parent: ""
word_type: "한자어휘" 

status: "t3사용안함"
priority: "medium"
process: "raw"
 
source_name: "한자어휘사전"
source_type: "article"
source_author: "self"

references: "개념의 실제 원전 (고전 이름, 원문 링크 등)"
tags: 출처/한자어휘/일반
---
# <% sound %>(<% hanja %>)

<% extra %><%*
const newFileName = hanja + ".md";
const currentFilePath = tp.file.path;
// 파일명 변경 (현재 파일명과 다를 때만)
if (tp.file.title !== hanja) {
  await tp.file.rename(hanja);
}
// 파일명 중복 검사 (자기 자신은 중복에 포함하지 않음)
const fileExists = await app.vault.adapter.exists(newFileName);
if (
  fileExists &&
  !currentFilePath.endsWith('/' + newFileName) && // 현재 파일이 아닌 경우만 중복으로 간주
  !currentFilePath.endsWith('\\' + newFileName)   // 윈도우 경로도 고려
) {
  tR += "⚠️ 이미 같은 이름의 파일이 존재합니다. 템플릿 실행을 중단합니다.";
  throw new Error("이미 파일이 존재함");
}
%>
<% tp.file.cursor() %>