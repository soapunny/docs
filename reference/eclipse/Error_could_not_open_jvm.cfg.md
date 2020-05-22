<h1>Error: could not open [잘못된 경로]\jvm.cfg 해결방안</h1><hr>
<br><br>

<ol>
  <li>JDK 폴더 위치에서 파일 탐색기로 jvm.dll을 찾는다.</li>
  <li>찾은 파일 중 \jdkx.x.xx\jre\bin\server 경로에 있는 파일을 찾아 경로 복사</li>
  <li>eclipse.ini 파일을 연 후 중간 쯤에 -vm 엔터치고 [복사한경로]\jvm.dll 을 추가해준다.</li>
  <li>이클립스가 잘 작동하는지 확인한다.</li>
</ol>
