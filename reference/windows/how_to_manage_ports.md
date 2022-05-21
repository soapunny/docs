<h1>포트 확인 및 포트 종료</h1>

<ol>
  <li> <b>사용중인 전체 포트 확인</b> <P>netstat -ano</p></li>
  <li> <b>사용중인 특정 포트 확인</b> <P>netstat -ano | findstr [PortNo]</p></li>
  <li> <b>사용중인 포트 종료</b> <P>taskkill /f /pid [PID]</p></li>
</ol>
