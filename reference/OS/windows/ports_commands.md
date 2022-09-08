# 포트 확인 및 포트 종료(See ports and release)


+ <b>See the list of ports in use</b>
  - netstat -ano
+ <b>See the specific port in use</b>
  - netstat -ano | findstr [PortNo]
+ <b>Kill the port with PID</b> 
  - taskkill /f /pid [PID]
