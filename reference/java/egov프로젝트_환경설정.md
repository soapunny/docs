<h1>egov 프로젝트 환경설정 문제 해결</h1><hr>
<br>

<h3>초기세팅</h3>
<br>

<ul>
<li>Eclipse - eGovFrame 선택</li>
<li>workspace 경로 설정</li>
<li>이클립스 내의 Maven repository 경로 설정</li>
<li>Tomcat 경로 설정</li>
</ul>
<br>

<h3>pom.xml</h3>
<br>

<ul>
<li>eclipse.ini 파일에 java 설치 디렉토리 확인</li>
<li>maven setting.xml에 로컬 디렉토리 설정 확인</li>
<li>pom.xml 확인<br>
https://repo1.maven.org/maven2/ 과 아래 둘 중 하나 repository 설정<br>
http://www.egovframe.go.kr/maven/ <br>
http://maven.egovframe.kr:8080/maven/
</li>
<li>eclipse window-preferences-general-startup-workspace 다 지우고 새로 세팅</li>
<li>eclipse window-preferences-maven-usersetting 다시 확인</li>
<li>톰캣 서버 디렉토리 재확인</li>
<li>프로젝트 우클릭-Maven-UpdateProject를 선택, Force Update에 체크후 저장소 초기화 후 재기동</li>
<li>&lt;pluginRepositories&gt;&lt;pluginRepository&gt;에 mvn2 repository를 등록해준다.</li>
</ul>
