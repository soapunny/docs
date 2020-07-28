<h1>01. krinc2 환경설정</h1><hr>
<br>

<h4>1-1. 사용한 tool과 버전정보</h4><br>
<pre><code>사용툴                버전
eGov-version          3.9
eclipse-javaee        Photon Release (4.8.0)
tomcat-version        8.5.55
jdk-version           jdk-8u251
</code></pre>
<br>

<h4>1-2. 서버 url 주소</h4><br>
<pre><code>서버종류          url
로컬             http://localhost:45080/krinc2/
테스트           http://test.mtaxrefund.com/krinc2/
</code></pre>
<br>

<h4>1-3. krinc2 서버 변경</h4><br>
<ol>
<li><b>이클립스</b>를 연다.
<li>src/main/java의 kr.co.unipatro.krinc.config.<b>ServerConfig.java</b> 파일을 연다.</li>
<li>currentServer() 빈 메서드 내부에 new CurrentServer(<b>"서버명"</b>) 객체 선언 시 생성자의 매개변수로 <b>"서버명"</b>을 넣어준다.</li>
<li>서버명은 다음 중 하나를 선택하여 서버를 설정할 수 있다.<br>
로컬&emsp; -> <b>로컬</b> or <b>local</b> or <b>로컬서버</b> or <b>localserver</b><br>
테스트 -> <b>테스트</b> or <b>test</b> or <b>테스트서버</b> or <b>testserver</b><br>
실&emsp;&emsp; -> <b>실</b> or <b>real</b> or <b>실서버</b> or <b>realserver</b>
</li>
</ol>
