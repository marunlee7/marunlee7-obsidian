---
title: 프론트매터 관리 끝판왕 👑 플러그인 metadata menu
priority: "medium"
process: "raw"
source_name: 프론트매터 관리 끝판왕 👑 플러그인 metadata menu
source_type: " youtube"
source_author: "북트레싱"
references: https://www.youtube.com/watch?v=rcgXLPgm4xk&list=PL-KPFbwFiAWA3bR3QSK3w6r_XM0KRzEFl&index=36
links: 
---
# 프론트매터 관리 끝판왕 👑 플러그인 Metadata Menu

![](https://www.youtube.com/watch?v=rcgXLPgm4xk)  

옵시디언에서 가장 중요한 요소 중 하나는 프론트매터(Properties)라고 생각합니다. 노트를 분류할 수 있는 여러가지 방법 중 가장 강력하다고 생각이 들기도 하는데요.  
이번 영상에서 다룬 Metadata Menu 플러그인은 이 프론트매터에 집중한 플러그인입니다. Class를 만들어서 그룹화 시켜서 관리가 가능하고, 테이블을 만들어서 테이블에서 직접 프론트매터의 수정이 가능합니다.  
그리고 데이터뷰 플러그인과 연동을 통해 데이터뷰 플러그인으로 생성한 테이블에서도 사용이 가능합니다.  

⏰ 타임스탬프  
00:00 미리보기  
00:48 인트로  
01:42 플러그인 설치 및 개념 설명  
02:42 글로벌 세팅  
02:59 Field- 기본 설명  
03:56 FieldInput  
05:31 FieldNumber  
06:37 FieldSelect, Cycle  
08:08 FieldBoolean, Date, Multi, File, Media  
11:25 Field- 필드 입력 및 템플릿 활용  
12:35 Class- 기본 설명, 설정  
14:52 Class- 사용방법  
18:57 Class- 테이블 기본 설명  
19:38 Class2- 기존 자료 적용, 설정  
20:51 Class2- 테이블 뷰 설명  
21:22 Class2Field 추가하기  
23:11 Class2Table 정렬  
23:47 Class2Table 활용  
25:40 노트에 테이블 추가 (1) - mdm  
27:31 노트에 테이블 추가 (2) - dataview  
30:07 Global File Class  
32:53 버튼(아이콘) 없애기  
34:03 내용 정리  


## 要約 ✍︎

- [x] metadata menu 프론트매터 관리 ★ ⏫ ✅ 2025-04-05
- [x] LiveWiki 타임라인, 아티클, 스크립트 공부하기 📅 2025-03-25 ⏫ (@2025-03-25) ✅ 2025-03-25

✨ ==Metadata Menu== 플러그인 소개
이번 영상에서는 옵시디언에서 프론트매터를 더 직관적으로 관리할 수 있게 해주는 **Metadata Menu 플러그인**에 대해 알아봅니다. 이 플러그인을 사용하면 ==프론트매터 항목을 자동으로 삽입하거나 쉽게 편집할 수 있고, 클래스로 묶어 그룹화하여 관리할 수도 있습니다.== 플러그인의 기능이 방대하기 때문에, 이번 영상에서는 기본적인 개념과 사용법을 중심으로 설명합니다. 

⚙️ 플러그인 설치 및 핵심 개념: Field와 Class
플러그인은 설정 > 커뮤니티 플러그인에서 "Metadata menu"를 검색하여 설치 및 활성화할 수 있습니다. 옵션에서는 'Field'와 'Class'라는 두 가지 중요한 개념을 이해해야 합니다. **Field는 프론트매터의 Property (Key-Value 쌍)**를 의미하며, **Class는 이러한 Property들을 목적에 맞게 그룹으로 묶어주는 역할**을 합니다. 예를 들어, 스터디 노트, 영화 리뷰, 도서 목록 등을 관리하기 위한 필드들을 묶어 클래스를 만들 수 있습니다. 

🧰 Field 설정 및 사용법
새로운 필드는 옵션에서 추가할 수 있으며, 다양한 타입 (input, number, select 등)을 선택할 수 있습니다. 각 타입별로 추가적인 설정 (template, step, min/max 값 등)이 가능합니다. 설정된 필드는 볼트 전역에서 사용 가능하며, 새 노트에서 마우스 우클릭, 우측 상단 옵션, 명령어 팔레트 등을 통해 추가할 수 있습니다. 추가된 필드는 아이콘을 통해 쉽게 수정할 수 있습니다. Number 타입의 필드는 step, 최소값, 최대값을 설정하여 값의 범위를 제한할 수 있습니다. Select 타입의 필드는 미리 정의된 값 목록에서 선택할 수 있으며, Cycle 옵션을 통해 값을 순환시킬 수도 있습니다. Boolean (체크박스), Date (날짜 선택), Multi (다중 선택), File/MultiFile (파일 선택), Media/MultiMedia (미디어 파일 선택) 등 다양한 타입의 필드를 활용할 수 있습니다. 

📚 Class 설정 및 활용
Class는 Preset Field보다 좁은 범위에서 설정을 관리할 수 있게 해줍니다. Class를 사용하면 템플릿과 유사하지만 추가적인 기능을 활용할 수 있습니다. Class 파일 경로를 지정하고, Class를 생성한 후, 노트의 프론트매터에 `fileClass: 클래스이름`을 입력하여 노트를 해당 Class에 포함시킬 수 있습니다. 태그를 이용하여 Class를 연결할 수도 있습니다. Class에 등록된 필드만 해당 노트에서 사용할 수 있으며, 테이블 뷰를 통해 Class에 속한 노트들의 정보를 한눈에 관리할 수 있습니다. 테이블 뷰에서 필드 값을 직접 수정하거나 추가할 수도 있습니다. 기존 자료에 Class 기능을 적용하려면, 새로운 Class를 만들고 필요한 필드들을 등록해야 합니다. 파일 경로를 지정하여 특정 폴더 내의 노트들을 Class에 포함시킬 수도 있습니다. 

📊 테이블 뷰 활용 팁
테이블 뷰는 노트에 직접 삽입하여 사용할 수 있으며, `mdm` 코드 블록과 `fileClass`, `view`, `files per page`, `showAddField` 등의 속성을 사용하여 테이블의 모양과 기능을 설정할 수 있습니다. Dataview 플러그인을 함께 사용하면 Class에 포함되지 않은 프론트매터도 테이블에 추가할 수 있으며, 필요한 필드만 선택하여 표시할 수도 있습니다. `alwaysOn: true` 옵션을 사용하면 필드 수정 버튼을 항상 표시할 수 있습니다. 

🌎 Global File Class (글로벌 파일 클래스)
Global File Class는 볼트 전체를 하나의 Class로 만들어 관리할 수 있게 해줍니다. 이는 Preset Field와 유사하지만, 기존 Class의 부모 Class로 사용할 수 있다는 차이점이 있습니다. Global Class에서 설정한 필드는 하위 Class에서 상속받아 사용할 수 있습니다. 상위 개념의 Class를 만들고 하위 개념의 Class를 설정하는 방식으로 활용할 수 있습니다. 

🎨 버튼 설정 및 숨기기
Metadata Menu 플러그인은 탐색기, 검색 결과, 탭 등 다양한 곳에 아이콘을 표시합니다. 이러한 아이콘이 너무 많아 불편하다면, 플러그인 설정에서 버튼 표시 여부를 조절하여 원하는 아이콘만 표시하도록 설정할 수 있습니다. 

💡 지식 관리의 중요성 및 플러그인 선택 팁
지식 관리 방법에는 정답이 없으며, 자신만의 해결책이 필요합니다. 다양한 플러그인을 활용하여 자신만의 지식 시스템을 구축할 수 있습니다. 플러그인 선택 또한 본인의 관리 성향에 따라 달라집니다. 여러 플러그인을 직접 사용해보고 장단점을 분석하여 자신에게 맞는 플러그인을 선택하는 것이 중요합니다. 지식 관리는 자신만의 무기를 준비하는 과정이며, 이를 통해 불확실한 미래에 당당하게 맞설 수 있기를 바랍니다. 

LiveWiki, 유튜브 속 핵심 내용을 10초 만에!
https://livewiki.com/ko/content/plugin-metadata-menu-management

## 思索 🙇🏻
