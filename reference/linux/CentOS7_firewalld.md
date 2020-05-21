<h1>CentOS7 서버 방화벽 설치(filewall installation in CentOs7)</h1><hr>
<br><br>

<h3>Firewall 상태 확인</h3>
<br>

<pre><code># firewall-cmd --state
</code></pre>

<p>여기서 현재 실행 중이면 running, 실행 중이 아니면 not running을 출력한다.<br>
만일 command not found가 출력된다면 firewall을 설치해야 한다.</p><br>

<h3>Firewall 설치 전 리파지토리로부터 yum install을 할 수 있는지 점검</h3>

<pre><code># vi /etc/yum.repos.d/[*.repo]
</code></pre>

<p>해당 명령어로 파일을 읽은 후 enabled를 0으로 설정</p><br>

<h3>Firewall 설치</h3>

<pre><code># 
</code></pre>

<p></p><br>
