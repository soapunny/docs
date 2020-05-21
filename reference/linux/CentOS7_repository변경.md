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
<br>

<p>해당 명령어로 기본 리파지토리로 이동 및 .repo 파일들을 확인한다.<br>
기존 *.repo 파일들은 백업해준다. [백업폴더생성.md] 파일 참조</p>
<br><br>


<h3>3. 새 리파지토리 생성</h3>
<br>

<pre><code># vi Daum.repo

[base]

name=CentOS-$releasever - Base

baseurl=http://ftp.daum.net/centos/7/os/$basearch/

gpgcheck=1

gpgkey=http://ftp.daum.net/centos/RPM-GPG-KEY-CentOS-7

 
 
[updates]

name=CentOS-$releasever - Updates

baseurl=http://ftp.daum.net/centos/7/updates/$basearch/

gpgcheck=1

gpgkey=http://ftp.daum.net/centos/RPM-GPG-KEY-CentOS-7

 

[extras]

name=CentOS-$releasever - Extras

baseurl=http://ftp.daum.net/centos/7/extras/$basearch/

gpgcheck=1

gpgkey=http://ftp.daum.net/centos/RPM-GPG-KEY-CentOS-7

 

[centosplus]

name=CentOS-$releasever - Plus

baseurl=http://ftp.daum.net/centos/7/centosplus/$basearch/

gpgcheck=1

gpgkey=http://ftp.daum.net/centos/RPM-GPG-KEY-CentOS-7
</code></pre>
<br>

<p>다음과 같이 Daum.repo 리파지토리를 생성해준다.</p>
<br><br>

참조: https://practice.hooniworld.io/entry/Centos-Repository-변경 [practice makes perfect]
