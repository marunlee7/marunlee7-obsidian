---
published: 2020-05-20
title: 노코드 All-in-one 플랫폼 리뷰  10x Lessons
aliases: []
level: T02
file_role: article_atom
parent: "10x Lessons"
word_type: t3전용 # T03 전용 필드 (빈 값 유지)
status: planned
priority: medium
process: raw
source_name: 노코드 All-in-one 플랫폼 리뷰  10x Lessons
source_author: "김태현"
source_type: "web"
references: "https://tkim.co/2020/05/no-code-platform/"
tags: [출처/외부_정보/아티클_웹]
---
# 노코드 All-in-one 플랫폼 리뷰 10x Lessons

| *[AI 사업 오픈 채팅방](https://open.kakao.com/o/gX9r01vf) (암호: gpters)를 운영하고 있습니다. AI와 프로덕트 마켓 핏에 대해서 대화를 나눠요!* |
| --- |

노코드 모임을 하면서 여러 종류의 웹앱 혹은 모바일 앱 빌더, 여러 가지 소프트웨어를 연동해서 자동으로 일련의 소프트웨어를 구동하는 워크플로 자동화툴을 살펴보고 있다. 하지만 각각의 툴들이 제공하는 기능을 몽땅 모아서 하나의 플랫폼으로 대기업에 제공하는 노코드 플랫폼 또한 존재한다.

사실 이러한 노코드 플랫폼이 역사가 훨씬 오래되었다. 대기업이 회사 내부에서 필요한 백오피스 소프트웨어를 개발하는데 그들만의 니즈가 있는 것을 처리하기 위해서 보통 외부 SI를 해 왔었다. 하지만 비즈니스 프로세스가 일부 바뀌거나 할 때 매번 구축한 소프트웨어를 수정하기는 시간도 많이 걸리고 비용도 높았을 것이다. 그리고, 각 부서마다 필요한 소프트웨어를 모두 구축하기도 비용이 많이 들었을테고.

이러한 페인 포인트를 공략한 것이 노코드 플랫폼이다. 노코드 플랫폼은 일반인이 개발자가 될 수 있는 시각적으로 소프트웨어를 만들 수 있는 툴을 제공했다. 사실 일반인이 하기는 좀 무리였던 것 같고, 어느 정도 컴퓨터가 돌아가는 로직에 대해서 이해가 있는 사람들을 대상으로 한 모양이다. 그래서 코딩의 요소가 0은 아니어서, Low-Code Platform이라고 카테고리가 만들어졌다 (지금은 그런 플랫폼들이 대부분 노코드를 지원한다, 즉 코딩 없이 앱 개발하고 배포할 수 있다).

그 중에 Microsoft Power Platform, OutSystems, AppGyver 세 가지 주요 플랫폼을 살펴 보았다. 사실 AppGyver의 경우는 주요 플랫폼으로 볼 수는 없으나 … 매출이 120억원 미만이라면 다 꽁짜로 쓸 수 있다고 해서 … 살펴 보았다.

[*노코드 정보 공유 오픈 채팅방*](https://open.kakao.com/o/gIEwXLhc)

![](https://lh5.googleusercontent.com/AZyTFRqPvI6umuqtP-F4IFWniBP3mn7Xo7VJi67ya-T3K6Ta7bCl-DMLB0pDBUzjLho_rqXBZE0RkFiX-dD1VP4APuDY4D3qHig5E_c1a76b_6f_Hgbk4OFYfjBzVwngw2yMneBz)

Microsoft Power Apps UI Builder

## 1\. Microsoft Power Platform

Power Platform은 세 가지 주요 툴로 구성된다. (1) 데이터 소스와 연결해서 시각화를 하는 Business Intelligence 툴은 Power BI, (2) 웹앱과 모바일 앱을 구축할 수 있는 Power Apps, (3) 소프트웨어를 연동하여 자동화할 수 있는 Power Automate (구 Microsoft Flow)이다.

Power BI는 패스하고, Power Apps를 살펴보면 간략하게 나의 이전 글에서 다룬 Bubble, Webflow, Adalo, Glide와 기능은 유사하다. 화면을 구성하는 요소, 즉 컴포넌트를 끌어다가 캔버스위에 넣고 속성을 편집하는 방식으로 앱을 개발할 수 있다. 앱이 사용하는 데이터는 여러 데이터 원본과 연결이 가능하다. 테이블 형태의 데이터를 저장할 수 있는 엑셀 파일, SQL 서버, 구글 스프레드시트 등을 다양하게 지원한다

엑셀을 잘 사용하시는 분은 엑셀의 함수로 로직을 구성하여 컴포넌트 속성에 연결하거나 액션을 정의할 수 있다. 위의 그림에 보면 중앙의 캔버스 바로 위쪽의 함수창이 이런 역할을 한다. 어찌보면 파워포인트 쓰듯이 UI를 만들고 엑셀을 쓰듯이 앱의 로직을 넣을 수 있게 되는 것이다. 이 방식은 Glide 앱에서도 사용되는데, 앱의 UI와 간단한 액션은 Glide 앱에서 만들지만 복잡한 로직의 경우 Glide 앱에 연결된 구글 스프레드 시트에서 따로 구성할 수 있다.

Power Apps는 캔버스에서 그려가며 만들어 가는 방법 외에도 Model-Driven Development라고 하는 옵션을 제공하는데, 이건 많이들 쓰는 비즈니스 앱들이 이미 템플릿화되어 있어서 Property만 수정하면 금방 앱을 만들어 낼 수 있다. 실제 익숙해 지면 이런 식으로 개발하는 것이 훨씬 효율적일 것으로 보인다.

Power Apps의 현재 한계는 모바일 앱의 경우 Power Apps Mobile이라고 불리는 모바일 앱에서만 실행될 수 있다는 것이다. 즉, 별개의 독립적인 앱으로 스토어에 출시를 할 수가 없다.

![](https://lh5.googleusercontent.com/hUxp9VH29K9XnpWW3TdYReDqlNtyMZt5r_5g0CPK6OwrqT67nzEkLUPVqGmmwmiOTn65YH9INLVwC_ktIYTx4Q2I6HxOnpuIcZM7B6c7KDUT2l9nMCfiyFHI8EoJcbMBdK9GQ0T7)

Microsoft Power Automate (ex. Microsoft Flow)

Power Automate는 Zapier의 마이크로소프트 버전이라고 보면된다. 다만 윈도 OS 개발사 답게 웹앱 뿐만 아니라, 윈도 프로그램들도 자동화하는 대상에 넣을 수 있다.

## 2\. AppGyver

AppGyver는 Gartner Magic Quadrant for Low-Code Application Platforms에서 나오지 않지만 웹앱과 모바일 앱을 개발하는 주요 기능을 대부을 가지고 있으면서, 120억원의 매출을 내기 전까지는 꽁짜이다!

AppGyver는 노코드 플랫폼이라 부르기엔 무리가 있는것이 비즈니스 프로세스, 즉 웹앱이나 모바일 앱을 개발한 뒤에 다른 외부의 여러 소프트웨어와 연동하여 프로세스를 구축하고, 프로세스를 모니터링하는 기능들이 빠져있다. 그래서 이 부분은 외부의 툴과 연동하여 사용해야 하는 것 같다.

![](https://lh6.googleusercontent.com/3cTe5a4lSaN8-VGDteBr5o1p3NDl5HV1ql2JkDtuKLo_YVO-Ukl4Ecmfbebswx9dj7yqnmbJgr9vNvfHwClsT-1K2GQlvouFlWyrQlU_xOQ_7EYbIFLUVYpuPTbY8trFWICnGMr-)

AppGyver UI Builder

AppGyver의 UI 빌더는 React Native를 기반으로 하기 때문에 웹앱과 모바일앱 그리고 TV앱을 개발할 수가 있다. 빌더의 사용방법은 다른 노코드 툴들과 유사하다. UI를 구성하는 컴포넌트들을 드래그-앤-드랍으로 캔버스에 넣고, 컴포넌트들의 속성 (Property)를 수정하여 모양새를 바꾸거나 데이터베이스에 있는 값(예: 상품명, 이미지, 가격 등)을 기반으로 컴포넌트를 보여줄 수 있다.

AppGyver는 일반적인 소프트웨어 개발에 대한 배경지식을 요구한다. 예를 들어 Variables (변수)와 Name Space에 대한 개념을 이해하여야 잘 쓸수 있다. 이런 변수들은 데이터베이스와 연동되어 다이내믹하게 바뀔 수도 있고, 사용자가 앱을 어떻게 쓰냐에 따라 앱의 현재 상태 (UI의 변화 등)을 저장하게 된다. 그리고 이런 변수들을 가지고 연산을 할 수있는 Formula도 제공하는데 이는 엑셀에서의 셀 내에서 값을 계산하는데 쓰이는 함수들이라고 생각하면 된다.

![](https://lh6.googleusercontent.com/yMcLXbcOMparzng8_a32AyfIvCUvpROjuxzVqqD24TRH-hYoEJFdCYdZ5GiBFmq1lwc4yIjB5hKT6SZJfXj4DI20as9k_UiOTiDqlXhEaz47_pJ7-UBw0YiyJ9m8ef7j76xSUkTh)

AppGyver Logic Builder

변수의 값에 따라 컴포넌트가 다르게 보이도록 조건을 설정할 수도 있고, 그 외의 복잡한 로직은 로직 빌더를 통해서 구성할 수 있다. 예를 들면 사용자가 버튼을 누르면 데이터베이스와 연동된 변수 값을 수정하고, 애니메이션을 보이고 팝업을 띄워라 — 이런 로직을 만들 수 있다.

변수와 Formula, 로직 빌더를 쓰는 것이 소프트웨어 개발에 대한 지식이 있는 사람들에게는 훨씬 직관적이고 편하게 보일 듯 하다. 반면에 Bubble.io와 같은 웹 빌더들은 자연어로 로직을 글로 쓰게 되는데 이게 일반인에게는 더 직관적일 수는 있으나 로직이 복잡해 질수록 가독성이 떨어지고 관리가 힘들어질 것 같은 느낌이다. 즉, 일반인이 가지기 어렵지않은 개발 지식 수준을 기본으로 가정하고 효율적으로 앱을 개발할 수 있는 툴인 것이다.

AppGyver의 특징 중에 하나는 기본 제공되는 컴포넌트와 JavaScript 커스텀 코드를 섞어 사용하면서 복합 컴포넌트를 만들 수 있다는 것이다. 즉, 빌더 내에서 제공하지 않는 기능이 있다면 이를 개발자와 협업하여 복합 컴포넌트 형태로 만들어 쓸 수 있다. 이런 확장성이 있기 때문에 개발할 수 있는 앱의 범주가 매우 넓어 진다. 다만, 소스 코드를 다운로드 받을 수는 없다.

백엔드 데이터베이스의 경우, 무료 버전은 REST API를 통해서 외부 데이터베이스와 연결하거나 기본으로 제공되는 Airtable 연동 기능을 통해서 Airtable을 데이터베이스로 쓸 수 있다.

## 3\. OutSystems

![](https://lh5.googleusercontent.com/wMvJO7ry1GghE81of-bXtNw88J87Xy3BiBk2EU_3xUUCDgcm7CaD37LU6YwTDo6MkWmso5uzFI_XgCRGuDOane0TGRqLhSboOtGONbiAHwQq6fUqHtZhraeBdRBi8rpOPFfmhPas)

2009년도에 OutSystems가 제공하던 비주얼 개발 툴 — 그때부터 제공했다는 게 놀랍다

OutSystems은 노코드 플랫폼 중에서 No. 1 플레이어 중에 하나이다. 위의 그림은 현재 제공되는 툴은 아니니 너무 놀라진 말고 … 사실 2009년부터 저런 툴을 제공해 왔다는 사실을 얘기하기 위함이다. 물론 지금은 훨씬 세련되었다. OutSystems의 만족도는 여러 SaaS 비교 사이트를 통해서 봐도 압도적으로 다른 플랫폼보다 높다.

![](https://lh6.googleusercontent.com/ZDqb4ejaQ-8i7S9AISwlzawByMgWyTFprXqgxXgoIlIO5wyaZavfSHDtjo2tETrAKvfDH1uxFOyl5kf8FX_-hoUfEDo-bMVtQDW0hBgpOFtFV90bWYf7TO5q_KlqqUXd9MYkHVnQ)

현재의 OutSystems의 Visual Development Environment

기본적으로 제공되는 UI 레이아웃 자체도 미려하고 기능적인 면에서 부족함이 없다. 컴포넌트를 드래그-앤-드랍으로 UI를 만들고, 로직 에디터를 통해서 로직을 만들어 추가할 수 있고, 다양한 데이터 소스와 연동할 수 있다. 필요하면 커스텀 JavaScript 코드를 넣어서 없던 컴포넌트도 만들어 낼 수 있다.

OutSystems는 윈도 프로그램까지 제작이 가능하며, 플랫폼을 사용하다가 중단하는 경우에 한해서 Java 혹은 JavaScript로 소스 코드를 뽑아낼 수 있다. OutSystems 자체가 회사 내부에서 원래 쓰던 윈도 소프트웨어 스택 및 기타 On-Premise 소프트웨어와 연동이 매우 잘되는데 이는 오래전부터 대기업의 사내 소프트웨어 구축을 도우며 기능을 확장해 왔기 때문인 듯 하다. 그래서 전통적인 산업을 하는 대기업에서 내부 소프트웨어 구축을 위해서 가장 선호할만큼 빈틈없는 기능의 플랫폼을 제공한다. 그래서 가장 싼 Basic 플랜이 한달에 480만원이고.. Standard 플랜은 월 12,000만원이다 … Enterprise 플랜은 견적내어 준다고 하니 그보다 더 비쌀테고 …

이런 플랫폼들 외에도 QuickBase, Betty Blocks 등을 살펴보았지만 대부분이 제공하는 기능은 대동소이하다. 큰 회사에서 도입할 때 어떤 필수 사항이 있을 텐데 거기에 맞는 툴을 선택하거나 가격이 자신이 만드려는 앱에 따라 유리한 플랫폼을 선택할 수 있을 것 같다.

## 노코드 플랫폼들을 둘러 보니 …

노코드 플랫폼을 둘러 보면서, 이런 플랫폼들이 개별 툴로 제공되는 노코드 툴들에 대비해서 All-in-one 솔루션으로 제공되고 그 완성도 또한 월등히 나은 느낌을 받았다. 하지만, 개인이 감당할 수 있는 수준의 가격이 아니라 정말 대기업에서나 도입할 수 있을 것으로 보인다.

그럼에도 불구하고 향후 일반인이 소프트웨어를 만드는 것이 대중화되고, 그런 소프트웨어를 통해서 연간 수억원에서 수십억원 정도의 개인 사업을 만들어 내는 시장이 형성되면 — 이미 영어문화권에는 이런 성공 사례가 많이 나오고 있다 — 그런 시장이 크게 형성된다면 개인이나 소상공인이 감당할 수 있는 가격 모델이 나오지 않을까 싶다.

| *[AI 사업 오픈 채팅방](https://open.kakao.com/o/gX9r01vf) (암호: gpters)를 운영하고 있습니다. AI와 프로덕트 마켓 핏에 대해서 대화를 나눠요!* |
| --- |