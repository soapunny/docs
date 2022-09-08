<h1>자바 경로 설정</h1>

<p>[내컴퓨터 - 속성 - 고급 시스템 설정 - 환경변수]<br>
시스템 변수 - 새로만들기</p>

<pre><code>변수 이름                       변수 값
CLASSPATH                    %classpath%;.
JAVA_HOME                      jre 경로
</code></pre>

Path - 편집 <b>%JAVA_HOME%\bin</b> 추가<br>
<b>java -version</b> 을 입력하여 잘 나오는지 확인
