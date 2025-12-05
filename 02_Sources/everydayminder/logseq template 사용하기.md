---
title: logseq template 사용하기
status: planned
priority: medium
process: raw
source_name: logseq template 사용하기
action_required: link_to_t04
difficulty:	good
satisfaction: 3
---
[%article%](https://luran.me/437)

- logseq에서 template 사용하려면?
    - 외부 툴 사용하기
    - 자체 기능 사용하기
        - 템플릿 등록하기
        - 템플릿 사용하기
    - 참고

# Logseq에서 Template 사용하려면?

logseq를 사용하면서, 글마다 반복해서 같은 양식을 사용하고자 한다면 어떻게 하면 좋을까?

## 외부 툴 사용하기

많은 맥 유저들이 Alfred를 쓴다. 그러면, Alfred 혹은 그와 유사한 유틸리티를 사용하여, 특정 키워드를 템플릿으로 등록해 놓고 사용할 수 있다. 이 방식의 장점은 비단 logseq 외 obsidian 혹은 다른 프로그램 사용시에도 범용적으로 사용할 수 있다는 점이다.

Alfred > Features > Snippets에서 키워드를 다음과 같이 등록한다.

![](https://blog.kakaocdn.net/dn/bmpC37/btrdkbIyFjr/KvwoeVg4SQ6Ceu8Sb027o1/img.png)

스크린샷에서의 샘플대로 입력하면, 'tt'라고 입력하면 아래와 같이 자동으로 해당 문자열로 치환해 준다.

- [[Meeting]]
- [[Note]]
- [[Todo]]

## 자체 기능 사용하기

만약, logseq내에서 템플릿을 사용하고자 한다면 어떨까? 다음의 절차에 따라, 템플릿을 등록하고 사용할 수 있다.

### 템플릿 등록하기

임의의 bullet과 그 하위 내용을 입력한다. 그리고, bullet에 커서를 둔 후, 마우스 오른쪽 버튼을 누르면 템플릿으로 등록할 수 있는 선택지가 보인다. 향후 관리를 용이하게 하려면, 템플릿들은 한 곳에 모아 두는 것이 더 편할 것 같다.

- [[templates]]를 만든다.
- [[templates]]를 클릭하여, 해당 페이지로 이동한다.
- 원하는 템플릿을 작성한다.
    - 위에 Alfred 예제에서와 동일하게 만들어 보자.  
        ![](https://blog.kakaocdn.net/dn/shG1o/btrdgRjM2fL/TjDrHkuoLzMHgOdIFrIyR1/img.png)
    - 왼쪽 불릿에 커서를 두고, 마우스 오른쪽 버튼을 클릭한다. context menu에 뜨는 것 중에서 Make Template을 선택한다.  
        ![](https://blog.kakaocdn.net/dn/cqucOB/btrdjc83DqB/7BBXd95SdTQW6B3sK0RXWk/img.png)
    - 템플릿 이름을 지정한다.  
        ![](https://blog.kakaocdn.net/dn/bXVPw2/btrdkN1IxTq/kKXFQVJxqktQJ7MFxSh9t1/img.png)

### 템플릿 사용하기

템플릿을 사용하고자 하는 곳에서, /template이라고 입력해보자. 입력을 다 완료하지 않아도 별도의 팝업이 뜰 것이다.

![](https://blog.kakaocdn.net/dn/lt6vy/btrdkPkZAY4/jdVXsGVCh3cUTPgh5JiTz0/img.png)

본인이 등록해둔 context 메뉴 중 선택 창이 뜰 것이다. 위의 예제에서는 mytemplate으로 지정했으므로, 해당 템플릿을 선택하면 커서의 위치에 템플릿이 입력될 것이다.

![](https://blog.kakaocdn.net/dn/cBWkGa/btrdkOGjyE0/B4LQub0XORNH1y1K8pf800/img.png)