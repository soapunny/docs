<h1> 01 자바스크립트 시작하기</h1>
<hr/>

<h4> 1-1. 자바스크립트의 기본개념</h4>
<br>

<b>프로젝트 개발 순서</b>
<ol>
<li>고객(클라이언트)에게 사이트 개발을 의뢰받고 이를 바탕으로 개발자가 기획안을 작성한다.</li>
<li>고객 요구에 맞게 작성한 기획안을 토대로 디자이너가 UI(User Interface)를 디자인한다.</li>
<li>완성된 디자인 파일을 전달받은 퍼블리셔가 HTML(Hyper Text Markup Language)와 CSS(Cascading Style Sheet)를 이용하여 화면의 모양을 잡아 정적인 웹 문서를 완성한다.</li>
<li>이 정적인 웹 페이지에 자바스크립트나 제이쿼리를 사용하여 이벤트나 기타 동작이 일어나게 한다.</li>
<li>완성된 HTML 문서를 백엔드 개발자가 서버언어(ASP, PHP, JSP)등을 활용하여 사용자로부터 입력받은 데이터를 가공하여 데이터베이스에 입출력할 수 있게 개발한다.</li>
</ol>
<br>

<b>자바스크립트의 탄생배경</b>
<ul>
<li>넷스케이프에 근무하던 브렌드 아이크(Brendan Eich, 1961~)가 모카(Mocha)라는 이름으로 개발, 이후 라이브스크립트(LiveScript)라는 이름으로 변경</li>
<li>넷스케이프는 JAVA로 유명한 썬마이크로 시스템스(Sun Microsystems)와 제휴하여 자바스크립트라는 이름을 사용</li>
</ul>
<br>

<b>자바스크립트의 표준화</b>
<ul>
<li>넷스케이프는 국제 정보통신(ECMA, European Computer Manufacturers Association)에 표준화를 요청하였고, 1996년 11월 ECMA-262라는 표준 명세가 만들어졌으며, 1997년 7월 ECMA 1 버전이 완성되었다.</li>
<li>자바 스크립트는 ES1(ECMA-262 1st edition)부터 기능이 점차 추가되어 현재 ES6(ECMA-262 7st edition)이 널리 사용되고 있다.</li>
<li>아직까지 일부 브라우저는 ES5만 지원하기 때문에 브라우저 지원 여부를 체크하고 사용해야 한다.</li>
</ul>
<br>

<b>자바스크립트로 할 수 있는 것</b>
<ul>
<li>HTML5에는 Geolocation, Canvas, Drag & Drop 등 풍부한 API(Application Programming Interface)가 내장되어 있다.</li>
<li>위 API들은 자바스크립트 언어를 기반으로 제작된 함수이며, 이를 활용하기 위해 자바스크립트를 반드시 알아야 한다.</li>
<li>최근에는 제이쿼리(Jquery), 앵귤러(Angular)JS, 리액트(React, 서버에서도 작동)JS, 폰갭(PhoneGap)등 자바스크립트로 제작된 다양한 라이브러리가 등장했다.</li>
<li>사이트, 모바일 웹, 스마트 TV 등 다양한 UI 개발에 사용한다.</li>
</ul>
<br>

<h4> 1-2. 개발 환경 설정</h4>
<br>

<b>크롬 브라우저 개발자 도구 패널</b>
<pre><code>Elements    HTML(Element) 요소에 적용된 스타일(CSS)을 검사할 수 있다.
Console     자바스크립트 오류 체크는 물론 디버깅(debugging)을 할 수 있다.
Source      브라우저가 자바스크립트 소스를 파싱(parsing, 저장된 값을 원하는 형식을 값으로 가공해 읽어오는 것을 말한다.)해오는 과정을 보여준다. 소스 패널도 오류 체크와 디버깅(debugging)을 할 수 있다.
</code></pre>
<br>

<h1> 02. 자바스크립트 기초 문법</h1>
<hr/>

<h4> 2-1 자바스크립트 기초 문법</h4>
<br>

<b>자바스크립트 선언문</b>
<ul>
<li>&lt;script&gt;가 시작되는 부분부터 종료되는 부분까지를 스크립트 영역이라고 한다.</li>
<li>일반적으로 스크립트 영역은 &lt;head&gt; 태그 영역에 선언한다.</li>
</ul>
<br>

<b>자바스크립트 주석 처리</b>
<ul>
<li>HTML 주석 : &lt;!-- 설명 --&gt;</li>
<li>한 줄 주석 : //설명</li>
<li>여러 줄 주석 : /*설명글*/</li>
</ul>
<br>

<b>내부 스크립트 외부로 분리하기</b>
<ul>
<li>자바스크립트를 외부를 분리하면 소스 관리가 쉽고 보안적으로도 좀 더 안전하다.</li>
<li>&lt;script src="JS 파일 경로"&gt;&lt;/script&gt;</li>
<li></li>
</ul>
<br>

<h4> 2-2 변수</h4>
<br>



