<h1>CentOS7 Repository 변경</h1><hr>
<br><br>

<h3>1. 리파지토리 변경 이유</h3>
<br>

<ul>
  <li>CentOS를 설치하고 업데이트 할 때 좀 더 빠른 속도로 다운받기위해</li>
  <li>기본 리포지토리보다 국내 서버로 운영하는 미러가 더 효과적</li>
  <li>많이 사용하는 Daum을 예제로 진행</li>
</ul>
<br><br>

<h3>2. 기본 리파지토리 위치로 이동</h3>
<br>

<pre><code># cd/etc/yum.repos.d/
# ls
</code></pre>

<p>해당 명령어로 기본 리파지토리로 이동 및 .repo 파일들을 확인한다.<br>
기존 *.repo 파일들은 백업해준다.</p>
