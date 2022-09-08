<h1>CentOS7 서버 방화벽 설치(filewall installation in CentOs7)</h1><hr>
<br><br>

<h3>1. Firewall 상태 확인</h3>
<br>

<pre><code># firewall-cmd --state
</code></pre>

<p>여기서 현재 실행 중이면 running, 실행 중이 아니면 not running을 출력한다.<br>
만일 command not found가 출력된다면 firewall을 설치해야 한다.</p>
<br><br>


<h3>2. Firewall 설치 전 리파지토리로부터 yum install을 할 수 있는지 점검</h3>
<br>
<pre><code># vi /etc/yum.repos.d/[*.repo]
</code></pre>

<p>해당 명령어로 파일을 읽은 후 enabled가 1로 되어있으면, enabled를 0으로 설정</p>
<br><br>


<h3>3. Firewall 설치</h3>
<br>

<pre><code># sudo yum install firewalld
# sudo systemctl enable firewalld
# sudo systemctl start firewalld
</code></pre>

<p>첫번째 명령어로 firewalld를 설치하고 나면<br>
아래 명령어들로 매번 서버 부팅/재부팅 시 자동으로 firewalld(방화벽데몬)이 실행되게 합니다.<br>
처음 설치 실행 시 모든 서비스/포트 접속을 막습니다.</p>
<br><br>


<h3>4. 서비스/포트로 방화벽 추가/해제하기</h3>
<br>

<pre><code># http, https 서비스 추가
# sudo firewall-cmd --permanent --add-service=http
# sudo firewall-cmd --permanent --add-service=https

# http, https 서비스 제거
# sudo firewall-cmd --permanent --remove-service=http
# sudo firewall-cmd --permanent --remove-service=http

# 특정 (80, 81) 포트 추가
# sudo firewall-cmd --permanent --add-port=80/tcp
# sudo firewall-cmd --permanent --add-port=81/tcp

# 특정 (80, 81) 포트 제거
# sudo firewall-cmd --permanent --add-remove=80/tcp
# sudo firewall-cmd --permanent --add-remove=81/tcp

# 구간 (6000-9000) 포트 추가
# sudo firewall-cmd --permanent --add-port=6000-9000/tcp

# 구간 (6000-9000) 포트 제거
# sudo firewall-cmd --permanent --remove-port=6000-9000/tcp

# 특정 IP에 대해 방화벽 추가
# sudo firewall-cmd --permanent --add-source=192.168.0.100

# 특정 IP에 대해 방화벽 제거
# sudo firewall-cmd --permanent --remove-source=192.168.0.100

# IP대역에 대해 방화벽 추가
# sudo firewall-cmd --permanent --add-source=192.168.0.0/24

# IP대역에 대해 방화벽 제거
# sudo firewall-cmd --permanent --remove-source=192.168.0.0/24
</code></pre>

<p>해당 명령어로 서비스/포트를 추가/제거 할 수 있다.</p>
<br><br>


<h3>5. 변경된 firewall 구성을 적용</h3>
<br>

<pre><code># sudo firewall-cmd --reload
</code></pre>

<p>해당 명령어로 반드시 리로딩 해줘야 반영</p>
<br><br>


<h3>6. 현재 방화벽 리스트 보기</h3>
<br>

<pre><code># firewall-cmd --list-all

# 리스트 출력 
public (default) 
interfaces: sources: 192.168.2.100 192.168.0.0/24 
services: dhcpv6-client ssh 
ports: 80/tcp 6000-9000/tcp 
masquerade: no 
forward-ports: 
icmp-blocks: 
rich rules: 
rule family="ipv4" source address="192.168.0.100" 
rule family="ipv4" source address="192.168.5.100" reject 
rule family="ipv4" source address="192.168.10.101" port port="80" protocol="tcp" accept
</code></pre>
<br><br>
