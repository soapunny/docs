<h1>Project Lombok 사용법 정리</h1><hr>
<br><br>

<h3>1. 롬복 의존성 등록</h3>
<br>
<ul>
  <li>https://mvnrepository.com/ 에서 Project Lombok의 dependency를 찾아 pom.xml에 등록한다. </li>
  <li>이클립스를 종료한다. </li>
  <li>[해당 프로젝트에서 사용중인 JDK 경로]\jre\bin에 있는 java.exe로 [maven]\repository\org\projectlombok\lombok\롬복버전\lombok-버전.jar를 실행한다. </li>
  <li>cmd를 켜서 lombok.jar 위치로 이동 후 java -jar lombok버전.jar를 이용하여 설치하는 방법도 있다. </li>
  <li>설치화면에서 Specific Location ..을 클릭 후 해당 이클립스 실행파일을 찾은 후 Install/Update를 클릭하여 설치한다. </li>
</ul>
<br><br>

<h3>2. Getter, Setter, toString 자동 생성</h3>
<br>
<ul>
  <li>@Getter : 모든 필드값에 대해 Getter를 자동으로 생성해준다. </li>
  <li>@Setter : 모든 필드값에 대해 Setter를 자동으로 생성해준다. </li>
  <li>@ToString : 해당 빈 클래스에 toString() 메서드를 추가해준다. </li>
</ul>
<br><br>

<h3>3. Construction(생성자) 자동 생성</h3>
<br>
<ul>
  <li>@AllArgsConstructor : 모든 필드값을 매개변수로 받아 저장하는 생성자를 생성한다. </li>
  <li>@NoArgsConstructor : 필드값을 매개변수로 받지 않는 기본 생성자를 생성한다. </li>
  <li>@RequiredArgsConstructor : 필요한 필드값만 매개변수로 받아 저장하는 생성자를 생성한다. 주입이 필요한 필드값 앞에 @NonNull 어노테이션을 붙인다. </li>
</ul>
<br><br>


<h3>4. Builder 간소화</h3>
<br>
<ul>
  <li>@Builder : 빌더를 간편하게 생성할 수 있도록 도와준다. </li>
</ul>
<br><br>

<h3>5. Logger 간소화</h3>
<br>
<ul>
  <li>@Slf4j : slf4j를 활용하여 log를 간편하게 사용할 수 있게 도와준다. </li>
</ul>
<br><br>

<h3>6. 보완된 @Synchronized</h3>
<br>
<ul>
  <li>기존 자바에서 @Synchronized 활용 시 데드락 발생 위험이 있는데, 롬복에서는 이 위험을 최소화 했다.</li>
</ul>
<br><br>

<h3>7. 모든 기능을 한번에 등록하기</h3>
<br>
<ul>
  <li>@Data : 해당 어노테이션을 선언하면  모든 기능을 한번에 등록할 수 있다.</li>
</ul>
<br><br>
