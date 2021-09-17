## Checklist
### HTML 표준의 역사는 어떻게 될까요?
### HTML 표준을 지키는 것은 왜 중요할까요?
1. 소스들이 표준에 의해 통일되고 효율이 높아져 파일 크기를 줄여 서버 공간을 절약하고 수정 및 운영관리가 쉬워진다.
2. 모바일 환경, 장애인 지원용 프로그램 등에서 대응이 가능해 접근성이 향상된다.
3. 검색엔진 최적화에 도움이 된다.
4. 문서 분리에서 효율적인 마크업을 통해 로딩 페이지 속도를 개선 할 수 있다.
5. 다양한 브라우저에서 호환할 수 있게 개발할 수 있다.
<br><br>

### XHTML 2.0은 왜 세상에 나오지 못하게 되었을까요?
XHTML1.0을 더 발전 시키기 위해 작업해온 표준안으로 HTML 뿐만 아니라 CSS, DOM, Form, Frames, Event 등 다양한 웹 요소들을 완벽하게 XML로 대체하기 위해 시도하였으나, 하위 호환성에 대한 보장이 거의 없어 실패했다.
<br><br>

### HTML5 표준은 어떤 과정을 통해 정해질까요?
회원기구, 정직원, 공공기관이 협력하여 웹 표준을 개발하는 국제 컨소시엄인 W3C에서 웹 표준과 가이드라인 개발을 수행하고 있다. 
<br><br>

### 브라우저의 역사는 어떻게 될까요?
<img src="http://www.favbrowser.com/wp-content/uploads/2011/03/historyofwebbrowsers.jpg">
<br><br>

### Internet Explorer가 브라우저 시장을 독점하면서 어떤 문제가 일어났고, 이 문제는 어떻게 해결되었을까요?
IE는 2001년 8월 버전6을 출시한 후 추가적인 개발을 거의 중단하다시피 한다. 5년간 2번의 서비스 팩 업데이트 이외에는 기능 개선이 거의 이루어지지 않았다. IE의 개발 및 개선이 등한시되어 5년 간 개발이 멈추면서 HTML, CSS, JavaScript의 표준 반영 또는 각종 보안 문제에 대응이 제대로 이루어지지 않으면서 자연스레 독점이 붕괴됐다.
<br><br>

### 현재 시점에 브라우저별 점유율은 어떻게 될까요? 이 브라우저별 점유율을 알아보는 것은 왜 중요할까요?
<img src="https://presscat.co.kr/wp-content/uploads/2020/04/%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%86%B1-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EC%8B%9C%EC%9E%A5-%EC%A0%90%EC%9C%A0%EC%9C%A8-%ED%95%9C%EA%B5%AD-2020.3-%EC%A0%9C%EB%AA%A9Y.png">
브라우저마다 HTML을 읽는 방식이 달라 브라우저나 버전간의 호환성을 생각해야하기 때문이다.
<br><br>

### 브라우저 엔진(렌더링 엔진)이란 무엇일까요? 어떤 브라우저들이 어떤 엔진을 쓸까요?
모든 웹 브라우저의 핵심이 되는 소프트웨어 구성 요소이다. 브라우저 엔진의 주된 역할은 HTML 문서와 기타 자원의 웹 페이지를 사용자의 장치에 상호작용적인 시각 표현으로 변환시키는 것이다.
<br><br>

### 모바일 시대 이후, 최근에 출시된 브라우저들은 어떤 특징을 가지고 있을까요?
모바일 브라우저는 휴대용 기기의 낮은 메모리 용량과 낮은 대역폭을 수용할 수 있도록 효율적이며 작은 화면에 가장 효과적으로 웹 콘텐츠를 표시할 수 있도록 최적화되어 있다.
<br><br>

### HTML 문서는 어떤 구조로 이루어져 있나요?
```javascript
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>

  </body>
</html>
```
* <!DOCTYPE html>: doctype. DOCTYPE은 문서의 유형을 정의하기 위해 사용하는 선언문(DTD, Document Type Definition).
* <html></html>: HTML 문서의 루트 요소(root element)를 정의합니다.
* <head></head>: HTML 문서의 메타데이터(metadata)를 정의합니다.
* <body></body>: 문서의 본문을 정의합니다. <body> 요소는 HTML 문서에 단 하나만 존재할 수 있다.
* <meta charset="utf-8">: 문서가 사용해야 할 문자 집합을 utf-8로 설정한다.
<br><br>

### `<head>`에 자주 들어가는 엘리먼트들은 어떤 것이 있고, 어떤 역할을 할까요?
* <title></title>: HTML문서 전체의 타이틀 표현하기 위한 메타데이터이다. 북마크 이름으로 사용되거나 검색결과로 사용되기도 한다.
* <meta charset="utf-8">: 문서가 사용해야 할 문자 집합을 utf-8로 설정한다.
* <link rel="stylesheet" href="my-css-file.css">: rel="stylesheet", 즉 문서의 스타일 시트임을 나타냄과 동시에 스타일 시트 파일의 경로를 포함하는 href를 내포한다.
<br><br>

### 시맨틱 태그는 무엇일까요?
시맨틱 태그는 의미에 맞게 태그를 작성하는 것을 의미한다.
<br><br>

#### 시맨틱 엘리먼트를 사용하면 어떤 점이 좋을까요?
HTML4 환경이라면 <div id="main">으로 작성할 코드를 HTML5에서는 <main>으로 작성할 수 있게 되어 간편해졌다. 또한 검색엔진 최적화(Search Engine Optimization, SEO)에도 영향을 준다.
 <br><br>

### `<section>`과 `<div>`, `<header>`, `<footer>`, `<article>` 엘리먼트의 차이점은 무엇인가요?
<br><br>

### 블록 레벨 엘리먼트와 인라인 엘리먼트는 어떤 차이가 있을까요?
block 속성은 무조건 한줄을 점유하고 있고, 다음 태그는 무조건 줄바꿈이 적용된다. 대표적인 태그는 div가 있다.<br>
inline 속성은 대표적인 태그로는 span을 예로 들 수 있는데, content 크기만큼만 공간을 점유하고 줄바꿈을 하지 않는다.
   * width/height 적용불가
   * margin/padding-top/bottom 적용불가
   * line-height를 원하는대로 사용할 수 없다. 