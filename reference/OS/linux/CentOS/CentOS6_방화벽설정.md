<h1>CentOS6 방화벽 설정</h1>
<br><br>


<h3>1. 열린 포트 및 iptables 설치 확인</h3>
<br>

<pre><code># 열린 포트 확인
# service iptables status

# iptables 설치 확인
# rpm -qa | grep iptables</code></pre>
<br>

<p>INPUT - 외부에서 호스트 컴퓨터를 향한 모든 패킷<br>
OUTPUT - 호스트 컴퓨터에서 외부로 가는 모든 패킷<br>
FORWARD - 외부에서 들어오지만 호스트 컴퓨터가 목적지가 아닌 모든 패킷, 즉 라우터로 사용되는 호스트 컴퓨터를 통과하는 패킷</p>
<br><br>


<h3>2. 외부 특정 IP에서 들어오는 접속 허용 및 차단</h3>
<br>

<pre><code># 방화벽 설정 문서 실행
# vi /etc/sysconfig/iptables

## 허용
-A INPUT -s [IP주소] -j ACCEPT
## 차단
-A INPUT -s [IP주소] -j DROP</code></pre>
<br><br>


<h3>3. 외부에서 내부의 특정 Port로의 접속 허용 및 차단</h3>
<br>

<pre><code># 방화벽 설정 문서 실행
# vi /etc/sysconfig/iptables

## 허용
-A INPUT -p tcp -dport 80 -j ACCEPT
## 차단
-A INPUT -p tcp -dport 443 -j DROP</code></pre>
<br><br>


<h3>4. 외부 IP에서 목적지 IP 해당 Port 접근 허용 및 차단</h3>
<br>

<pre><code># 방화벽 설정 문서 실행
# vi /etc/sysconfig/iptables

## 허용
-A INPUT -s 111.111.111.11 -d 222.22.22.222 -p tcp --dport 80 -j ACCEPT
## 차단
-A INPUT -s 111.111.111.11 -d 222.22.22.222 -p tcp --dport 80 -j DROP</pre></code>
<br>
<p>외부 IP 111.111.111.11에서 목적지 IP 222.22.22.222의 80 포트로 접근을 허용/차단</p>
<br><br>


<h3>5. 방화벽 정책 저장 및 재구동</h3>
<br>

<pre><code># 정책 저장
# service iptables save

# 저장 확인
# vi /etc/sysconfig/iptables

# 반영을 위해 서비스 재구동
# service iptables restart
