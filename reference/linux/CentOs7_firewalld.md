<h1>CentOs7 서버 방화벽을 활용하여 특정 IP만 접근 가능하게 설정(filewall configuration for ip restriction in CentOs7)</h1><hr>
<br><br>

<h3>Firewall 상태 확인</h3>
<br>

<pre><code># firewall-cmd --state
</code></pre>

<p>여기서 현재 실행 중이면 running, 실행 중이 아니면 not running을 출력한다.<br>
만일 command not found가 출력된다면 firewall을 설치해야 한다.</p><br>

<h3>Firewall 설치 전 yum install이 사용가능한지 점검</h3>

<pre><code># vi /etc/yum.repos.d/[*.repo]
</code></pre>

<p>해당 명령어로 파일을 읽은 후 enabled를 0으로 설정</p><br>

<h3>Firewall 설치</h3>

<pre><code># 
</code></pre>

<p></p><br>
