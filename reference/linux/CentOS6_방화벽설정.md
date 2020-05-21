<h1>CentOS6 방화벽 설정</h1>
<br><br>


<h3>1. 열린 포트 및 iptables 설치 확인</h3>
<br>

<pre><code># 열린 포트 확인
# service iptables status

# iptables 설치 확인
# rpm -qa | grep iptables</code></pre>
<br>

<p>INPUT - 호스트 컴퓨터를 향한 모든 패킷<br>
OUTPUT - 호스트 컴퓨터에서 발생하는 모든 패킷<br>
FORWARD - 호스트 컴퓨터가 목적지가 아닌 모든 패킷, 즉 라우터로 사용되는 호스트 컴퓨터를 통과하는 패킷</p>
<br><br>


<h3>2. IP 허용 및 차단</h3>
<br>

<pre><code># 방화벽 설정 문서 실행
# vi /etc/sysconfig/iptables

# 허용
-A INPUT -s [IP주소] -j ACCEPT
# 차단
-A INPUT -s [IP주소] -j DROP</code></pre>
<br><br>


<h3>2. Port 허용 및 차단</h3>
<br>

<pre><code># 방화벽 설정 문서 실행
# vi /etc/sysconfig/iptables

# 허용
-A INPUT -p tcp -dport 80 -j ACCEPT
# 차단
-A INPUT -p tcp -dport 443 -j DROP</code></pre>
<br><br>
