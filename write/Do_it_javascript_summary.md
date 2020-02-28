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

<h1> 02 자바스크립트 기초 문법</h1>
<hr/>

<h4> 2-1. 자바스크립트 기초 문법</h4>
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

<h4> 2-2. 변수</h4>
<br>

<b>변수의 기본개념</b>
<ul>
<li>변하는 데이터(값)을 저장할 수 있는 메모리 공간</li>
<li>변수에 저장할 수 있는 값은 문자형(String), 숫자형(Number), 논리형(Boolean) 그리고 Null이 있다.</li>
<li>변수명에는 영문, 숫자 그리고 일부 특수 문자(_,$)만 포함할 수 있다.</li>
<li>변수명에 여러 단어가 같이 오게되면 각 단어의 첫글자는 대문자로 쓴다(Camel표기법)</li>
<li>변수명으로는 예약어(document, location, window 등)를 사용할 수 없다.</li>
<li>변수명은 의미를 부여하여 신중하게 작성한다.</li>
<li>var 변수명; var 변수명 = 값;</li>
</ul>
<br>

<h4> 2-3. 자바스크립트 자료형</h4>
<br>

<b>문자형</b>
<ul>
<li>문자형(String) 데이터는 문자나 숫자를 큰따옴표 또는 작은따옴표로 감싸고 있다.</li>
<li>문자형 데이터에 HTML 태그를 포함하여 출력하면 태그로 인식한다.</li>
<li>var 변수 = "사용할 문자나 숫자";</li>
</ul>
<pre><code>    var s = "javascript";
    var num = "100";
    var tag = "&lt;h1&gt; String &lt;/h1&gt;";
</code></pre>
<br>

<b>숫자형</b>
<ul>
<li>숫자형(Number) 데이터는 큰따옴표나 작은따옴표로 둘러싸여있지 않은 순수한 숫자 데이터를 의미한다.</li>
<li>숫자형 데이터간에 사칙 연산이 가능하다.</li>
<li>var 변수 = 숫자; 또는 Number("숫자로 변환 가능한 문자")</li>
</ul>
<pre><code>    var s = 100;
    var t = Number("500"); // "500" -> 500
</code></pre>
<br>

<b>논리형</b>
<ul>
<li>논리형(Boolean) 데이터에는 true(참) 또는 false(거짓)가 있다.</li>
<li>var 변수 = true or false; 또는 Boolean(데이터);</li>
<li>Boolean() 메서드는 숫자 0, null, undefined, 빈 문자("")를 제외한 모든 데이터에 대해 true를 반환한다.</li>
</ul>
<pre><code>    var s = true; //true
    var t = 10>=100; //false
    var k = Boolean("hello"); //true
    var y = Boolean(0); //false
</code></pre>
<br>

<b>null & undefined 데이터</b>
<ul>
<li>undefined는 변수 s에 값이 저장되기 전의 기본값이다.</li>
<li>null은 변수에 저장된 값이 null인 경우를 가리킨다.</li>
</ul>
<pre><code>    var s; //s == undefined
    var t = "hello"; //t == "hello"
    var t = null; //t == null
</code></pre>
<br>

<b>typeof</b>
<ul>
<li>typeof는 해당 데이터 또는 변수에 저장된 데이터의 자료형을 알고 싶을 때 사용한다.</li>
<li>typeof 변수 또는 데이터</li>
</ul>
<pre><code>    var num = 100;
    var str = "자바스크립트";
    document.write(typeof num, "&lt;br&gt;"); //number
    document.write(typeof str, "&lt;br&gt;"); //string
</code></pre>
<br>

<h4> 2-4. 연산자</h4>
<br>

<b>연산자의 기본 개념</b>
<ul>
<li>연산자는 다양한 계산을 계산할 때 필요한 기호이다.</li>
<li>자바스크립트에서 사용하는 연산자에는 산술, 문자 결합, 대입, 증감, 비교, 논리, 삼항 조건 연산자가 있다.</li>
<li>연산자를 활용하여 빼기, 더하기, 곱하기, 나누기, 비교 등을 하는 일련의 과정을 연산 작업이라고 한다.</li>
</ul>
<br>

<b>산술 연산자</b>
<pre><code>    +       더하기
    -       빼기
    *       곱하기
    /       나누기
    %       나머지연산
</code></pre>
<br>

<b>문자 결합 연산자</b>
<pre><code>    "baby " + "shark" = "baby shark";
    "100" + 200 = "100200";
</code></pre>
<br>

<b>대입 연산자</b>
<pre><code>    A = B       A = B
    A += B      A = A+B
    A -= B      A = A-B
    A *= B      A = A*B
    A /= B      A = A/B
    A %= B      A = A%B
</code></pre>
<br>

<b>증감 연산자</b>
<pre><code>    var a = 1;
    var b = 10;
    
    a += b++; //a == 11, b == 11, a+b를 먼저한 후 a에 대입 후 b 증가
    a += ++b; //a == (11+12), b == 12, b를 증가시킨 후 a+b를 하여 a에 대입
</code></pre>
<br>

<b>비교 연산자</b>
<pre><code>    A > B       A가 B보다 크다.
    A < B       A가 B보다 작다.
    A >= B      A가 B보다 크거나 같다.
    A <= B      A가 B보다 작거나 같다.
    A == B      A와 B는 같다.(자료형 구분없이 값만 같으면 true)
    A != B      A와 B는 같지 않다.(자료형 구분없이 값이 달라야 true)
    A === B     A와 B는 같다.(갑과 자료형 모두 같아야 true)
    A !== B     A와 B는 같지 않다.(값과 자료형 모두 달라야 true)
</code></pre>
<br>

<b>논리 연산자</b>
<pre><code>    ||       or연산자       피연산자 중 하나라도 true가 존재하면 true
    &&      and연산자       양 항이 모두 true이면 true
    !       not연산자       true는 false로, false는 true로 반대의 값을 반환
</code></pre>
<br>

<b>연산자 우선순위</b>
<ol>
<li>()</li>
<li>단항 연산자(--, ++, !)</li>
<li>산술 연산자(+, -, *, /, %)</li>
<li>비교 연산자(>, >=, <, <=, ==, !=, ===, !==)</li>
<li>논리 연산자(&&, ||)</li>
<li>대입 연산자(=, +=, -=, *=, /=, %=)</li>
</ol>
<br>

<b>삼항 조건 연산자</b>
<ul>
<li>조건식의 결과에 따라 실행 결과가 달라지는 연산자</li>
<li>피연산자의 개수가 3개이다.</li>
<li>조건식 ? 코드1 : 코드2;</li>
<li>조건식이 참(true)이면 코드1, 아니면 코드2를 반환한다.</li>
</ul>
<br>

<h1> 03 제어문</h1>
<hr/>

<h4> 3-1. 제어문</h4>
<br>

<b>제어문이란</b>
<ul>
<li>프로그램의 흐름을 제어할 수 있도록 도와주는 문장</li>
<li>조건 만족 여부에 따라 코드를 제어하는 조건문(if, else if, else)</li>
<li>변수에 일치하는 경우의 값에 따라 코드를 제어하는 선택문(switch)</li>
<li>특정 코드를 여러 번 반복하여 실행하는 반복문(while, for)이 이에 해당한다.</li>
</ul>
<br>

<h4> 3-2. 조건문</h4>
<br>

<b>조건문이란</b>
<ul>
<li>조건식이 참(true)인지 거짓(false)인지에 따라 자바스크립트 코드 제어</li>
<li>조건문에는 if, else if, else가 있다.</li>
<li>조건식에 논리형 데이터(true, false)가 아닌 다른 형의 데이터가 입력되어도 true 또는 false로 인식</li>
<li>0, null, ""(빈 문자), undefined는 false, 나머지는 true이다. </li>
<li>다음은 조건문에 관한 간단한 예제이다.</li>
</ul>
<pre><code>    var num = 10;
    if(num<500){ //true
        document.write(num+" < 500는 true 입니다.");
    }
    if(0){ //false
        document.write("0은 true입니다.");
    }else if(undefined){ //false
        document.write("undefined는 true입니다.");
    }else{ //위의 두 조건식이 false이면 실행
        document.write("0과 undefined는 모두 false입니다.");
    }
</code></pre>
<br>

<h4> 3-3. 선택문</h4>
<br>

<b>선택문</b>
<ul>
<li>선택문에는 switch문이 있다.</li>
<li>switch문은 변수에 저장된 값과 switch문의 case값을 비교하여 일치하는 코드를 실행합니다.</li>
<li>if문과 비슷하나, if문은 만족하는 데이터가 여러개일 때, switch문은 여러 경우 중 만족하는 값이 1개일 때 주로 사용합니다.</li>
</ul>
<pre><code>    var 변수 = 초기값;
    switch(변수){
        case 값1: 코드1;
            break;
        case 값2: 코드2;
            break;
        case 값3: 코드3;
            break;
        default: 코드4;
    }
</code></pre>
<br>

<h4> 3-4. 반복문</h4>
<br>

<b>while문</b>
<ul>
<li>while문은 조건식을 만족할 때까지 중괄호({...}) 안에 있는 코드를 반복하여 실행합니다.</li>
</ul>
<pre><code>    var 변수 = 초기값;
    while(조건식){
        자바스크립트코드;
        증감식;
    }
</code></pre>
<br>

<b>do while문</b>
<ul>
<li>do while 문은 조건식이 마지막에 있어 무조건 한 번은 반복문을 실행한다.</li>
</ul>
<pre><code>    var 변수 = 초기값
    do{
        자바스크립트 코드;
        증감식;
    }while(조건식);
</code></pre>
<br>

<b>for문</b>
<ul>
<li>for문은 조건식을 만족할 때까지 특정 코드를 반복하여 실행</li>
<li>for문 실행순서는 
    <ol>
    <li>초기값
    <li>조건식
    <li>자바스크립트코드
    <li>증감식
    <li>조건식
    </ol>
    <li>break;를 만나면 가장 안쪽의 반복문을 빠져나간다.</li>
    <li>continue;를 만나면 중괄호의 가장 마지막으로 이동한다.</li>
</ul>
<pre><code>    for(초기값;조건식;증감식){
        자바스크립트코드;
    }
</code></pre>
<br>

<h1> 04 객체</h1>
<hr/>

<h4> 4-1. 객체</h4>
<br>

<b>객체의 개념</b>
<ul>
<li>자바스크립트는 객체(Object)기반 언어이다.</li>
<li>객체는 기능과 속성을 가지고 있다.</li>
<li>이러한 고유한 속성이나 기능들을 갖춘 주변의 모든 사물을 객체라고 한다.</li>
<li>다음은 자바스크립트 객체의 메서드와 속성의 사용예이다.</li>
</ul>
<pre><code>    객체.메서드();
    객체.속성;          
    객체.속성 = 값;  
</code></pre>
<br>

<b>객체의 종류</b>
<ul>
<li>자바스크립트 객체는 내장 객체, 브라우저 객체모델(BOM, Browser Object Model), 문서 객체 모델(DOM, Document Object Model)로 나눠진다.</li>
<li>내장 객체에는 문자(String), 날짜(Date), 배열(Array), 수학(Math) 객체 등이 있다.</li>
<li>브라우저 객체 모델(BOM)은 브라우저에 계층 구조로 내장되어 있는 객체를 말한다.</li>
<li>브라우저 객체로는 window, screen, document, location, history, navigator 객체 등이 있다.</li>
<li>브라우저(window)는 document와 location의 상위 객체이다.</li>
<li>문서 객체 모델(DOM)은 HTML 문서 구조를 말한다.</li>
<li>문서 객체 모델의 최상위 객체로는 &lt;html&gt;이 있고 그 하위에 &lt;head&gt;, &lt;body&gt; 등이 있다.</li>
</ul>
<pre><code>    Tv.turnOn(); //TV를 켜는 메소드
    Tv.channelUp(); //채널을 증가시키는 메소드
    window.location.href='http://www.google.com';
    //브라우저의 url 위치를 이동시키는 브라우저 객체 location의 메소드 href()
</code></pre>
<br>

<h4> 4-2. 내장 객체</h4>
<br>

<b>내장 객체의 개념</b>
<ul>
<li>내장 객체(Built-in Object)란 브라우저의 자바스크립트 엔진에 내장된 객체를 의미한다.</li>
<li>필요에 따라 객체를 생성하여 사용할 수 있다.</li>
<li>내장 객체에는 String, Date, Array, Math, RegExp Object 등이 있다.</li>
<li>var 인스턴스명 = new 생성 함수();</li>
</ul>
<pre><code>    var tv = new Object();
    tv.color = "white";
    tv.price = 300000;
    tv.info = function(){
        document.write("tv 색상 : ", this.color, "&lt;br&gt;");
        document.write("tv 가격 : ", this.price, "&lt;br&gt;");
    }
    document.write("tv 객체의 info() 실행!!", "&lt;br&gt;");
    tv.info();
    var car = {
        color:"black",
        price:50000000,
        toString: function(){
            document.write("color : ", this.color, ", price : ", this.price, "원&lt;br&gt;");
    }
    document.write("&lt;br&gt;car 객체의 toString() 실행!!&lt;br&gt;");
    car.toString();
</code></pre>
<br>

<b>날짜 정보 객체</b>
<ul>
<li>날짜나 시간 정보를 제공받고 싶을 때 날짜 객체(Date Object)를 생성한다.</li>
<li>var 객체명 = new Date(); 현재 날짜 사용</li>
<li>var 객체명 = new Date("연/월/일"); 해당 연/월/일 사용</li>
<li>var 객체명 = new Date(연, 월-1, 일); 해당 연, 월, 일 사용</li>
</ul>
<pre><code> 날짜관련 메서드<br>
    getFullYear()       연도 정보를 가져온다.
    getMonth()          월 정보를 가져온다.(월-1)
    getDate()           일 정보를 가져온다.
    getDay()            요일 정보를 가져온다.(일:0 ~ 토:6)
    getHours()          시 정보를 가져온다.
    getMinutes()        분 정보를 가져온다.
    getSeconds()        초 정보를 가져온다.
    getMiliseconds()    밀리초(1/1000초) 정보를 가져온다.
    getTime()           1970년 1월 1일부터 경과된 시간을 밀리초로 표현
    toLocaleString()    운영 시스템 표기 방식으로 문자형 데이터로 반환
    toGMTString()       GMT 표준 표기 방식으로 문자형 데이터로 반환<br>
    setFullYear()       연도 정보를 수정
    setMonth()          월 정보를 수정(월-1)
    setDate()           일 정보만 수정
    요일은 날짜를 바꾸면 자동으로 바뀜
    setHours()          시 정보만 수정
    setMinutes()        분 정보만 수정
    setSeconds()        초 정보만 수정
    setMiliseconds()    밀리초 정보만 수정
    setTime()           1970년 1월 1일 부터 경과된 시간을 밀리초 단위로 수정
</code></pre>
<br>

<b>수학 객체</b>
<ul>
<li></li>
</ul>