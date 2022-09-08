<h1>스프링5 프로그래밍 입문</h1>
<hr/>
<br>

<h4>Configuration</h4>
<br>

<b>이클립스 : 자바 및 톰캣 준비</b>
<br>

<ul>
<li>JDK 1.8, 이클립스 Java EE Developers 패키지</li>
<li>이클립스에 자바 8 런타임이 등록되어 있지 않으면, Window Preferences Java/Installed JREs 메뉴를 이용하여 자바 JRE 등록</li>
<li>UTF-8 문자 인코딩</li>
<li>[Window]-[Preferences]-[General/Workspace]에서 Text file encoding을 UTF-8로 변경</li>
<li>만약 다른 인코딩을 사용하는 프로젝트와 함께 사용하려면 프로젝트 임포트 후</li>
<li>[Project]-[Properties]-[Resources]에서 인코딩을 UTF-8로 변경</li>
<li>Tomcat 8.5</li>
<li>https://tomcat.apache.org/ 에서 8.5버전 zip이나 tar.gz 파일을 다운 및 압축 풀기</li>
<li>[Window]-[Preferences](맥 OS의 경우 [Eclipse]-[환경설정])-[Server]-[Runtime Environments]-[Add] 에서 톰캣이 설치된 폴더를 등록</li>
</ul>
<br>

<b>메이븐 프로젝트 이클립스에 임포트</b>
<br>

<ul>
<li>[File]-[Import...]</li>
<li>Maven/Existing Maven Projects 선택 후 [Next>]</li>
<li>[Browse...] 버튼을 눌러 임포트 할 프로젝트를 Root Directory 값으로 지정</li>
<li>[Finish] 버튼을 눌러 이클립스 프로젝트로 임포트 된 것을 확인</li>
</ul>
<br>

<h1>Chapter 01. 스프링</h1>
<hr/>
<br>

<h4>1.1. 스프링의 주요 특징</h4>
<br>
<ul>
<li>의존 주입(Dependency Injection, DI) 지원</li>
<li>AOP(Aspect-Oriented Programming) 지원</li>
<li>MVC 웹 프레임워크 제공</li>
<li>JDBC, JPA 연동, 선언적 트랜잭션 처리 등 DB 연동 지원</li>
</ul>
<br>

<h4>1.2. 이 책에서 다루는 범위</h4>
<br>
<ul>
<li>메이븐과 그레이들을 이용한 스프링 프로젝트 생성</li>
<li>스프링을 이용한 객체 생성과 의존 주입 처리</li>
<li>스프링 자바 설정</li>
<li>스프링을 이용한 AOP 프로그래밍 기초</li>
<li>JDBC 프로그래밍과 선언적 트랜잭션 처리</li>
<li>스프링의 MVC 프레임워크를 이용한 웹 어플리케이션 개발 기초</li>
</ul>
<br>

<h4>1.3 JDK 설치 및 JAVA_HOME 환경변수 설정</h4>
<br>
<ul>
<li>스프링 5 버전은 자바 8 이상을 사용한다.</li>
<li>스프링 5, 자바 8, 서블릿 3.1/JSP 2.3</li>
<li>JDK 1.8 설치 후 윈도우 탐색기의 [내 PC]-[속성]-[고급 시스템 설정]</li>
<li>[고급] 탭-[환경 변수]의 PC에 대한 사용자 변수(내 계정에만 적용)에서 새로만들기</li>
<li>JAVA_HOME을 변수명으로 하고 JDK 경로를 값으로하는 환경변수 등록</li>
<li>사용자 변수에서 Path 값에 %JAVA_HOME%\bin; 을 추가해 준다.</li>
<li>cmd에서 java를 입력해서 경로가 나오면 성공</li>
<li>could not open `C:\Program Files\Java\jre1.8.0_241\lib\amd64\jvm.cfg'</li>
<li>다음과 같은 에러 시, path 다 삭제하고 window32에서 java 관련 .exe 삭제</li>
<li>프로그램 제거 또는 변경에서 java 8 관련 파일 삭제 후 재설치</li>
</ul>
<br>

<h4>1.4. 메이븐 설치</h4>
<br>
<ul>
<li>http://maven.apache.org/ 방문 후 [Download]를 눌러 Binary zip archive 다운</li>
<li>압축을 푼 뒤 \bin에 mvn.bat이 존재하는지 확인</li>
<li>명령 프롬프트에서 메이븐을 실행할 수 있도록 PATH에 "[메이븐 설치 경로]\bin"을 추가</li>
<li>명령 프롬프트에 [mvn -version]으로 버전 확인</li>
<li>JAVA_HOME 환경변수 정보가 옳바르지 않으면 error 발생</li>
</ul>
<br>

<h4>1.5. 그레이들 설치</h4>
<br>

<ul>
<li>"https://gradle.org/releases/"에서 그레이들 다운로드</li>
<li>압축이 잘 풀리면 "[그레이들설치경로]\bin"에 gradle.bat 존재</li>
<li>PATH 환경변수에 "[그레이들설치경로]\bin" 추가</li>
<li>명령 프롬프트에서 gradle -version으로 설치 확인</li>
</ul>
<br>

<h4>1.6. 이클립스 설치</h4>
<br>

<ul>
<li>"Eclipse IDE for JAVA EE Developers" 패키지를 다운로드</li>
<li>[Window]-[Preferences]-[General/Workspace] 설정에서</li>
<li>"Text file encoding"을 UTF-8로 설정</li>
</ul>
<br>

<h1>chapter 02. 스프링 시작</h1>
<hr/>
<br>

<h4>2.1. 메이븐 프로젝트 생성</h4>
<br>

<ul>
<li>"[메이븐 프로젝트 경로]\src\main\java" 해당 경로 생성</li>
<li>[메이븐 프로젝트 경로]에 pom.xml 파일을 아래와 같이 작성한다.</li>
</ul>

<pre><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;project xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
        http://maven.apache.org/xsd/maven-4.0.0.xsd"&gt;
    &lt;modelVersion&gt;4.0.0&lt;/modelVersion&gt;
    &lt;groupId&gt;spring5_book&lt;/groupId&gt;
    &lt;artifactId&gt;chap02&lt;/artifactId&gt;
    &lt;version&gt;0.0.1-SNAPSHOT&lt;/version&gt;
    
    &lt;dependencies&gt;
        &lt;dependency&gt;
            &lt;groupId&gt;org.springframework&lt;/groupId&gt;
            &lt;artifactId&gt;spring-context&lt;/artifactId&gt;
            &lt;version&gt;5.0.2.RELEASE&lt;/version&gt;
        &lt;/dependency&gt;
    &lt;/dependencies&gt;
    
    &lt;build&gt;
        &lt;plugins&gt;
            &lt;plugin&gt;
                &lt;artifactId&gt;maven-compiler-plugin&lt;/artifactId&gt;
                &lt;version&gt;3.7.0&lt;/version&gt;
                &lt;configuration&gt;
                    &lt;source&gt;1.8&lt;/source&gt;
                    &lt;target&gt;1.8&lt;/target&gt;
                    &lt;encoding&gt;utf-8&lt;/encoding&gt;
                &lt;/configuration&gt;
            &lt;/plugin&gt;
        &lt;/plugins&gt;
    &lt;/build&gt;

&lt;/project&gt;
</code></pre>
<br>

<h4>2.2. 메이븐 의존 설정</h4>
<br>

<ul>
<li>pom.xml은 메이븐 프로젝트에 대한 설정 정보를 관리하는 파일이다.</li>
<li>프로젝트에서 필요로하는 의존 모듈이나 플러그인에 대한 설정을 담는다.</li>
<li>메이븐은 한 개의 모듈을 아티팩트 단위로 관리한다.</li>
<li>소스코드를 실행할 때 각 아티팩트(아티팩트이름-버전.jar)를 클래스 파일 PATH에 추가한다.</li>
</ul>
<br>

<h4>2.3. 메이븐 리포지토리</h4>
<br>

<ul>
<li>아티팩트 파일은 메이븐 local repository에 .jar파일이 존재하는지 확인한다.</li>
<li>존재하지 않으면, 메이븐 remote central repository에서 해당 파일을 다운로드 후 local repository에 복사하여 파일을 사용한다.</li>
<li>메이븐은 기본적으로 [사용자홈폴더]\.m2\repository 폴더를 local repository로 사용</li>
<li>실제 아티팩트 파일은 [그룹ID]\[아티팩트ID]\[버전] 폴더에 위치한다.</li>
<li>아래 의존 설정에서 아티팩트 파일이 위치하는 경로는 [사용자홈폴더]\.m2\repository\org\springframework\spring-context\5.0.2.RELEASE</li>
<li>해당 경로(local repository)에 jar파일이 존재하지 않는 경우, 명령 프롬프트에서 해당 프로젝트로 이동 후 "mvn compile"을 해준다.</li>
</ul>

<pre><code>&lt;dependency&gt;
    &lt;groupId&gt;org.springframework&lt;/groupId&gt;
    &lt;artifactId&gt;spring-context&lt;/artifactId&gt;
    &lt;version&gt;5.0.2.RELEASE&lt;/version&gt;
&lt;/dependency&gt;
</code></pre>
<br>

<h4>2.4. 의존 전이(Transitive Dependencies)</h4>
<br>

<ul>
<li>"mvn compile" 실행 시 spring-context-5.0.2.RELEASE.jar 파일 외에 다양한 아태팩트 파일을 다운한다.</li>
<li>spring-context-5.0.2RELEASE.jar 파일을 다운하기 전 spring-context-5.0.2.RELEASE.pom 파일을 다운하는데</li>
<li>이는 해당 아티팩트가 다시 의존하는 파일들이 포함되어 있다.</li>
</ul>

<pre><code>spring-context          spring-core             spring-jcl
                        spring-beans
                        spring-aop
                        aspectjweaver
</code></pre>
<br>

<h4>2.5. 메이븐 기본 폴더 구조</h4>
<br>

<ul>
<li>src\main\java에는 자바 소스 코드가 위치</li>
<li>src\main\resources에는 자바 소스 이외의 다른 자원 파일</li>
<li>src\main\webapp는 웹 어플리케이션을 개발할 때 사용</li>
<li>해당 폴더에 JSP 소스 코드나 WEB-INF\web.xml 파일을 작성한다.</li>
</ul>
<br>

<h4>2.6. 메이븐 프로젝트 임포트</h4>
<br>

<ul>
<li>[File]-[Import...]-[Maven/Existing Maven Projects]를 선택 후 [Next] 클릭</li>
<li>[Browse]에서 앞에서 생성한 메이븐 프로젝트를 Root Directory로 선택 후 [Finish]</li>
<li>임포트를 완료하면 src/main/java 폴더가 소스 폴더로 지정되었고 Maven Dependencies들이 클래스 패스에 추가된 것을 확인할 수 있다.</li>
</ul>
<br>

<h4>2.7. 그레이들 프로젝트 생성</h4>
<br>

<ul>
<li>그레이들 프로젝트는 메이븐 프로젝트의 pom.xml과 달리 build.gradle 파일을 작성한다.</li>
<li>그레이들은 메이븐과 마찬가지로 "src\main\java"를 자바 소스 폴더로 사용</li>
<li>"src\main\resources"를 XML이나 프로퍼티 같은 자원 파일을 위한 소스 폴더로 사용</li>
<li>[해당 그레이들 프로젝트 경로]에 build.gradle 파일 생성</li>
<li>명령 프롬프트에서 [해당 그레이들 프로젝트 경로]로 이동 후 "gradle wrapper" 명령어로 래퍼 파일 생성</li>
<li>명령 성공 시 gradlew.bat, gradlew 파일과 gradle 폴더가 생성됨</li>
<li>gradlew compileJava 명령어 실행</li>
</ul>

<pre><code>apply plugin: 'java'
           
sourceCompatibility = 1.8
targetCompatibility = 1.8
compileJava.options.encoding = "UTF-8"

repositories{
mavenCentral()
}

dependencies{
compile 'org.springframework:spring-context:5.0.2.RELEASE'
}

wrapper{
gradleVersion = '4.4'
}
</code></pre>
<br>

<h4>2.8. 그레이들 프로젝트 임포트</h4>
<br>

<ul>
<li>[File]-[Import...]-[Gradle/Existing Gradle Project]-[Next]-[Next]</li>
<li>[Browse]-[해당 그레이들 프로젝트] 선택-[Next]-[Finish]</li>
</ul>
<br>

<h4>2.9. ApplicationContext</h4>
<br>
<ul>
<li>ApplicationContext는 객체를 생성하고 초기화하는 스프링의 핵심 기능이 정의된 인터페이스이다.</li>
<li>AnnotationConfigApplicationContext 클래스는 이 인터페이스를 구현한 클래스이다.</li>
<li>AnnotationConfigApplicationContext 클래스는 자바 클래스에서 정보를 읽어, 객체를 생성 및 초기화 한다.</li>
<li>이 밖에 XML파일을 이용, 객체를 생성 및 초기화하는 GenericXmlApplicationContext 클래스</li>
<li>그루비 코드를 이용해 설정 정보를 가져오는 GenericGroovyApplicationContext 클래스가 있다.</li>
</ul>

<pre><code> AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext(AppContext.class);
 //설정 정보를 이용하여 빈 객체를 생성한다.
 Greeter greeter = ctx.getBean("greeter", Greeter.class);
 //빈 객체를 제공한다.
</code></pre>
<br>

<h4>2.10. Bean</h4>
<br>
<ul>
<li>@bean로 설정하면 getBean(빈 메서드명, 반환클래스명.class)를 통해 객체를 반환한다.</li>
<li>@bean는 기본설정으로 단일 객체만 생성하며(singleton), 새로운 객체를 생성하고자 하는 경우 @bean을 하나 더 만든다.</li>
</ul>
<br>

<h1>chapter 03. 스프링 DI</h1>
<hr>
<br>

<h4>3.1. 의존이란</h4>
<ul>
<li>DI는 'Dependency Injection'의 약자로 우리말로 '의존 주입'이라고 한다.</li>
<li>여기에서 '의존'은 객체간의 의존을 의미한다.</li>
<li>아래와 같이 한 클래스의 메서드로 다른 클래스의 메서드(기능)를 실행할 때 이를 '의존'한다고 한다.</li>
</ul>

<pre><code>public class MemberRegisterService {
    //
    private MemberDAO memberDAO = new MemberDAO();
    
    public void regist(RegisterRequest req) {
        //이메일로 member 객체를 가져온다.
        Member member = memberDAO.selectByEmail(req.getEmail());
        
        if(member != null) {//해당 이메일을 가진 멤버가 존재하면 예외 발생
            throw new DuplicationMemberException("dup email "+req.getEmail());
        }
        //새 멤버 등록
        Member newMember = new Member(req.getEmail(), req.getPassword(), req.getName(), LocalDateTime.now());
        memberDAO.insert(newMember);
    }
}
</code></pre>
<br>

<h4>3.2. DI를 통한 의존 처리</h4>
<br>
<ul>
<li>다음은 의존 객체를 직접 생성하는것이 아닌 생성자를 통해서 전달받는 DI 패턴이다.</li>
<li>이렇게 '의존 주입'을 하게되면 리팩토링 시 변경할 코드가 적어진다. 유지보수가 쉬워진다.</li>
</ul>

<pre><code>public class MemberRegisterService {
    //
    private MemberDAO memberDAO;
    
    public MemberRegisterService(MemberDAO memberDAO) {//생성자를 통해 객체를 주입
        this.memberDAO = memberDAO;
    }
    
    public Long regist(RegisterRequest req) {
        Member member = memberDAO.selectByEmail(req.getEmail());
        
        if(member != null) {
            throw new DuplicatedMemberException("Duplicated email -> "+req.getEmail());
        }
        
        Member newMember = new Member(req.getEmail(), req.getPassword(), req.getName(), LocalDateTime.now());
        memberDAO.insert(newMember);
        return newMember.getId();
    }
}
</code></pre>
<br>

<h4>3.3. 예제 프로젝트 만들기</h4>
<br>
<ul>
<li>Maven project를 위한 pom.xml 작성</li>
<li>회원관련 클래스인 Member, WrongIdPasswordException, MemberDAO</li>
<li>회원 가입 처리 관련 클래스인 DuplicateMemberException, RegisterRequest, MemberRegisterService</li>
<li>암호 변경 관련 클래스인 MemberNotFoundException, ChangePasswordService</li>
<li>조립기인 Assembler 클래스로 각각의 객체들을 조립, MainForAssembler 클래스로 프로그램을 실행한다.</li>
</ul>
<br>

<h4>3.4. 스프링을 이용한 객체 조립과 사용</h4>
<br>
<ul>
<li>Assembler 대신 스프링을 사용한 코드를 작성한다.</li>
<li>ApplicationConfiguration 클래스를 @Configuration으로 등록하여 @Bean들을 생성해준다.</li>
<li>MainForSpring에서 AnnotationConfigApplicationContext 생성자를 통해 위의 ApplicationConfiguration를 등록한다.</li>
<li>각각의 빈클래스들을 getBean() 메서드로 불러온다.</li>
</ul>
<br>

<h4>3.5. DI 방식 1 : 생성자 방식</h4>
<br>
<ul>
<li>PrintEntireMemberService 클래스를 활용하여 전체 맴버를 출력한다.</li>
<li>ApplicationConfiguration에 해당 빈 객체를 생성자를 사용하여 등록하고, MainForSpring에 전체 맴버를 출력하는 메서드 생성</li>
</ul>

<pre><code>@Bean
public PrintEntireMemberService printEntireMemberService() {//Constructor DI method
    return new PrintEntireMemberService(memberDAO());
}
</code></pre>
<br>

<h4>3.6. DI 방식 2 : 세터(setter) 방식</h4>
<br>
<ul>
<li>PrintSingleMemberService 클래스를 활용하여 해당 맴버를 출력한다.</li>
<li>ApplicationConfiguration에 해당 빈 객체를 생성한 후 세터를 반드시 설정한 후 반환한다.</li>
<li>setter를 통한 DI 주입을 해주지 않으면 해당 객체 사용시 NullPointerException 발생!!</li>
<li>MainForSpring에 맴버를 찾는 메서드를 등록해준다.</li>
</ul>

<pre><code>@Bean
public PrintSingleMemberService printSingleMemberService() {//Setter DI method
    PrintSingleMemberService printSingleMemberService = new PrintSingleMemberService();
    printSingleMemberService.setMemberDAO(memberDAO());
    
    return printSingleMemberService;
}
</code></pre>
<br>

<h4>3.7. 기본 데이터 타입 값 설정</h4>
<br>
<ul>
<li>생성자 방식이나 세터 방식으로 @Bean 생성 시 기본 데이터 타입을 직접 넣어주는 방법</li>
</ul>

<pre><code>@Bean
public VersionPrinter versionPrinter() {
    VersionPrinter versionPrinter = new VersionPrinter();
    versionPrinter.setMajorVersion(5);// 직접 기본 데이터 타입 부여
    versionPrinter.setMinorVersion(0);
    return versionPrinter;
}
</code></pre>
<br>

<h4>3.8. @Configuration 설정 클래스</h4>
<br>
<ul>
<li>@Bean은 기본값으로 하나의 객체만을 생성하는 싱글톤 방식을 취한다.</li>
<li>@Configuration 설정 파일의 @Bean의 개수가 늘어나면 설정파일을 분할해준다.</li>
<li>AnnotationConfigApplicationContext의 생성자는 가변 인자를 취하기 때문에 추가한 설정 파일 클래스를 매개 변수에 추가해주면 된다.</li>
<li>@Autowired 필드는 스프링의 자동 주입 기능을 위한 것이다. 해당 타입의 빈을 찾아 필드 값에 부여한다.</li>
</ul>

<pre><code>//ApplicationConfiguration2 클래스
public class ApplicationConfiguration2 {
    //
    @Autowired
    private MemberDAO memberDAO;
    @Autowired
    private MemberPrinter memberPrinter;
    ...이하생략...
}

//MainForSpring의 생성자
public MainForSpring() {
    applicationContext = new AnnotationConfigApplicationContext(ApplicationConfiguration1.class, ApplicationConfiguration2.class);
}
</code></pre>
<br>

<h4>3.9. 설정파일이 아닌 일반 의존 주입 클래스에서의 @Autowired</h4>
<br>
<ul>
<li>세터를 활용하는 일반 의존 주입 클래스의 필드에 @Autowired를 해주면</li>
<li>@Configuration 설정 파일에서 세터 의존 주입을 해주지 않아도 자동으로 찾아 주입해준다.</li>
</ul>

<pre><code>public class PrintSingleMemberService {
    //@Autowired 시 @Configuration 클래스에서 따로 세터 의존 주입을 해줄 필요 x
    @Autowired
    private MemberDAO memberDAO;
    ...중간 생략...
    public void setMemberDAO(MemberDAO memberDAO){
     this.memberDAO = memberDAO;
    }
}

public class ApplicationConfiguration2{
    ...생략...
    @Bean
    public PrintSingleMemberService printSingleMemberService() {//Setter DI method
        PrintSingleMemberService printSingleMemberService = new PrintSingleMemberService();
        /*printSingleMemberService.setMemberDAO(memberDAO); 해당 코드 생략 가능*/
        
        return printSingleMemberService;
    }
}
</code></pre>
<br>

<h4>3.10. @Import 어노테이션 사용</h4>
<br>
<ul>
<li>ApplicationConfiguration1 클래스에 @Import(ApplicationConfiguration2.class)를 등록해주면</li>
<li>AnnotationConfigApplicationContext 클래스를 생성할 때 ApplicationConfiguration1만 매개변수로 넣어주면 된다.</li>
<li>@Configuration 클래스인 ApplicationConfigurationImport 클래스를 새로 만든다.</li>
<li>해당 클래스에 2개 이상 클래스를 @Import({ApplicationConfiguration1.class, ApplicationConfiguration2.class})와 같이 임포트해준다.</li>
</ul>

<pre><code>@Configuration
@Import({ApplicationConfiguration1.class, ApplicationConfiguration2.class})
public class ApplicationConfigurationImport {
    //
}

public class MainForSpring{
    // ApplicationConfigurationImport 클래스만 등록해주면 끝
    public MainForSprint(){
        applicationContext = AnnotationConfigApplicationContext(ApplicationConfigurationImport.class);
    }
    ...이하 생략...
}
</code></pre>
<br>

<h4>3.11. getBean() 메서드 사용</h4>
<br>
<ul>
<li>VersionPrinter versionPrinter = applicationContext.getBean("versionPrinter", VersionPrinter.class);</li>
<li>위에 getBean의 인자인 versionPrinter는 등록된 빈 메서드의 이름이고 VersionPrinter.class는 반환하는 객체 타입이다.</li>
<li>만일 빈 메서드명을 versionPrinter2라고 주면 NoSuchBeanDefinitionException 발생</li>
<li>만일 빈 메서드명을 이미 존재하는 memberDAO로 바꾸면, 반환타입이 VersionPrinter.class가 아니라 BeanNotOfRequiredTypeException이 발생한다.</li>
<li>만일 해당 클래스의 빈 객체가 하나만 존재하면 getBean(VersionPrinter.class)라고 사용할 수 있다.</li>
<li>단, 해당 클래스 타입의 빈 객체가 2개 이상 존재하면 위의 메서드는 NoUniqueBeanDefinitionException을 발생</li>
</ul>
<br>

<h4>3.12. 주입 대상 객체를 모두 빈 객체로 설정해야 하나?</h4>
<br>
<ul>
<li>빈 객체가 아닌 private MemberDAO memberDAO = new MemberDAO() 다음과 같이 필드로 선언해주면</li>
<li>해당 @Configuration 파일에서는 사용가능하나 스프링 컨테이너가 관리x, 스프링 컨테이너에서 사용 불가능 하다.</li>
<li>그렇기에 스프링 의존 주입 대상은 스프링 빈으로 등록하는 것이 바람직하다.</li>
</ul>
<br>

<h1>chapter 04. 의존 자동 주입</h1>
<hr/>
<br>

<h4>4.1. @Autowired를 사용한 의존 자동 주입</h4>
<br>
<ul>
<li>프로젝트 chap04 폴더를 만든 후 pom.xml추가 및 src/main/java 폴더 추가</li>
<li>chap03에서 작성한 모든 자바 파일을 복사해온다.</li>
<li>ChangePasswordService 클래스에서 필드값에 @Autowired를 하면 @Configuration 파일에서 세터 의존 주입을 생략 가능하다.</li>
<li>또한 필드 값에 @Autowired를 하면 세터 메서드가 없어도 의존 자동 주입된다.</li>
<li>필드값이 아닌 세터 메서드에 @Autowired 해줘도 동일하게 의존 자동 주입한다.</li>
<li>이제 @Configuration 파일의 빈 메서드들은 객체 반환만 해주면 된다.</li>
</ul>
<br>

<h4>4.2. 일치하는 빈이 없는 경우</h4>
<br>
<ul>
<li>만약 @Autowired를 적용한 대상에 해당하는 빈 객체가 없으면 UnsatisfiedDependencyException이 발생한다.</li>
<li>@Autowired를 적용한 대상에 해당하는 빈 객체가 2개 이상일 경우도 UnsatisfiedDependencyException 발생</li>
</ul>

<pre><code>//@Autowired된 필드
@Autowired
private MemberDAO memberDAO;

//@Configuration 파일(해당 타입의 빈 객체가 없을 경우)
//@Bean
//public MemberDAO memberDAO() {//해당 메서드가 반환한 객체를 스프링 빈으로 설정
//    return new MemberDAO();
//}

//@Configuration 파일(해당 타입의 빈 객체가 2개 이상일 경우)
@Bean
public MemberDAO memberDAO1(){
    return new MemberDAO();
}
@Bean
public MemberDAO memberDAO2(){
    return new MemberDAO();
}
</code></pre>
<br>

<h4>4.3. @Qualifier 어노테이션을 이용한 의존 객체 선택</h4>
<br>
<ul>
<li>자동 주입 가능한 빈이 두 개 이상이면 자동 주입할 빈을 선택할 수 있는 방법이 필요</li>
<li>@Qualifier 어노테이션이 이 역할을 해준다.</li>
<li>@Bean 아래에 @Qualifier("별명")으로 등록하면 @Autowired 선언부 아래에 @Qualifier("별명")으로 매칭 가능하다.</li>
</ul>
<br>

<h4>4.4. 빈 이름을 기본 한정자로 지정한 의존 객체 선택</h4>
<br>
<ul>
<li>자동 주입 가능한 빈이 두 개 이상일 때, 하나의 빈의 이름으로 필드명을 생성한다.</li>
</ul>

<pre><code>//@Configuration 클래스
@Bean
public MemberDAO memberDAO() {//기본 한정자
    return new MemberDAO();
}

@Bean
@Qualifier("memberDAOClone")
public MemberDAO memberDAO2() {//"memberDAOClone"이 한정자가 됨
    return new MemberDAO();
}

//@필드 선언부
@Autowired
private MemberDAO memberDAO; //memberDAO()의 빈 객체를 주입한다.
@Autowired
private MemberDAO memberDAOClone; //memberDAO2()의 빈 객체를 주입한다.
</code></pre>
<br>

<h4>4.5. 상위/하위 타입 관계와 자동 주입</h4>
<br>
<ul>
<li>해당 빈 객체와 해당 빈 객체를 상속 받은 빈 객체를 반환하는 빈 메서드도 한정자를 구분해 주지 않으면 예외 발생</li>
<li>다음 예외를 해결하기 위한 방법으로 @Qualifier 어노테이션으로 한정자를 구분해 주는 방법이 있다.</li>
<li>다른 방법으로는 @Autowired 한 부분에서 상속받은 빈 객체를 사용하도록 바꾸는 방법이 있다.</li>
</ul>

<pre><code>public class ApplicationConfiguration1(){
    @Bean
    public MemberPrinter memberPrinter1(){
        return new MemberPrinter();
    }
    @Bean
    public MemberSummaryPrinter memberPrinter2(){//MemberPrinter를 상속받은 MemberSummaryPrinter
        return new MemberSummaryPrinter();
    }
}

public class MemberListPrinter(){
    ...생략...
    // MemberPrinter로 받게되면 memberPrinter1 빈 메소드와 memberPrinter2 빈 메소드 중복 주입이 가능
    @Autowired
    public void setMemberPrinter(MemberSummaryPrinter printer){//MemberSummaryPrinter로 방지
        this.printer = printer;
    }
}
</code></pre>
<br>

<h4>4.6. @Autowired 어노테이션 필수 여부</h4>
<br>
<ul>
<li>@Autowired 할 대상의 의존 주입이 필수가 아닌 경우 예외를 방지하는 방법</li> 
<li>1. @Autowired(required = false)로 지정해준다. 이 경우 세터 메서드가 호출 되지 않는다.</li>
<li>2. Spring 5 부터는 자동 주입 대상 세터 메서드에 Optional을 사용할 수 있다.</li>
<li>3. @Nullable 어노테이션을 사용. 이 경우 빈이 존재하지 않아도(null) 세터 메서드가 호출된다.</li>
</ul>

<pre><code>public class MemberPrinter(){
    // required의 사용
    private DateTimeFormatter dateTimeFormatter;
    
    @Autowired(required = false) // 해당 빈 객체가 없으면 실행하지 않는다.
    public void setDateTimeFormatter(DateTimeFormatter dateTimeFormatter) {
        this.dateTimeFormatter = dateTimeFormatter;
    }
}

public class MemberPrinter(){
    // Optional의 사용
    private DateTimeFormatter dateTimeFormatter;

    @Autowired // Optional의 isPresent() 메서드를 활용한다.
    public void setDateTimeFormatter(Optional&lt;DateTimeFormatter&gt; formatter) {
        if(!formatter.isPresent())
            this.dateTimeFormatter = null;
        else
            this.dateTimeFormatter = formatter.get();
    }
}

public class MemberPrinter(){
    // @Nullable의 사용(해당 빈 객체가 존재하지 않아도 세터 메서드가 실행되어 null 주입)
    private DateTimeFormatter dateTimeFormatter;

    @Autowired
    public void setDateTimeFormatter(@Nullable DateTimeFormatter dateTimeFormatter) {
        this.dateTimeFormatter = dateTimeFormatter;
    }
}
</code></pre>
<br>

<h4>4.7. 생성자 초기화와 필수 여부 지정 방식 동작 이해</h4>
<br>
<ul>
<li>@Autowired의 required 속성을 false로 하면 빈 객체가 없더라도 자동 주입 대상에 null을 전달하지 않는다.</li>
<li>반면 @Nullable은 빈 객체가 존재하지 않으면 자동 주입 대상에 null을 전달하여 초기화 한다.</li>
<li>Optional은 매칭되는 빈 객체가 없으면 값이 없는 Optional 할당</li>
</ul>

<pre><code>public class MemberPrinter(){
    //DateTimeFormatter 빈 객체가 있을 경우만 실행, 빈 객체가 없더라도 DateTimeFormatter에 null을 전달하지 않는다.
    @Autowired(required = false) 
    public void setDateTimeFormatter(DateTimeFormatter dateTimeFormatter) {
        this.dateTimeFormatter = dateTimeFormatter;
    }
}

public class MemberPrinter(){
    //DateTimeFormatter 빈 객체가 없을 때도 실행, 빈 객체가 없으면 DateTimeFormatter에 null을 전달
    @Autowired 
    public void setDateTimeFormatter(@Nullable DateTimeFormatter dateTimeFormatter) {
        this.dateTimeFormatter = dateTimeFormatter;
    }
}
</code></pre>
<br>

<h4>4.8. 자동 의존 주입과 명시적 의존 주입 간의 관계</h4>
<br>
<ul>
<li>@Configuration 클래스에서 세터를 통해 직접 의존을 주입했는데 자동 주입 대상일 경우, 자동 주입을 통해 일치하는 빈을 주입한다.</li>
<li>그렇기 때문에 @Autowired 어노테이션을 사용했을 경우 자동 주입 기능을 사용하는 편이 낫다.</li>
</ul>
<br>

<h1>Chapter 05. 컴포넌트 스캔</h1>
<hr/>
<br>

<h4>5.1. @Component 어노테이션으로 스캔 대상 설정</h4>
<br>
<ul>
<li>스프링이 검색해서 빈으로 등록 가능하려면 @Component 어노테이션을 붙여야 한다.</li>
<li>@Component에 값을 안주면 기본값으로 클래스명의 첫 글자를 소문자로 바꾼 객체가 생성된다.</li>
<li>@Component("listPrinter")와 같이 같을 줄 경우 해당 값을 빈 이름으로 사용한다.</li>
<li>후에 MainForSpring에서 getBean()을 사용할 때 "listPrinter"라는 이름으로 불러올 수 있다.</li>
</ul>
<br>

<h4>5.2. @ComponentScan 어노테이션으로 스캔 설정</h4>
<br>
<ul>
<li>@Component 어노테이션을 붙인 클래스를 스프링 빈으로 등록하려면 설정 클래스에 @ComponentScan 어노테이션을 적용해야한다.</li>
<li>@ComponentScan(basePackages = {"spring"})와 같이 지정하면 spring 패키지와 하위 패키지들의 모든 클래스가 스캔 대상이 된다.</li>
<li>basePackages = {}의 속성값은 여러개가 될 수 있다.</li>
</ul>
<br>

<h4>5.3. 스캔 대상에서 제외하거나 포함하기</h4>
<br>
<ul>
<li>@ComponentScan 시 excludeFilters 속성을 사용하면 자동 스캔 대상에서 제외할 수 있다.</li>
<li>@ComponentScan(basePackages = {"spring"}, excludeFilters = @Filter(type = FilterType.REGEX, pattern = "*DAO"))</li>
<li>@ComponentScan(basePackages = {"spring"}, excludeFilters = @Filter(type = FilterType.ASPECTJ, pattern = "spring.*DAO"))</li>
<li>FilterType은 REGEX(정규식), ANNOTATION 또는 ASPECTJ 패턴을 사용할 수 있다. ASPECTJ의 경우 aspectjweaver 모듈을 추가해야 한다.</li>
<li>pattern 속성은 배열을 이용하여 한 개 이상 지정할 수 있다.</li>
</ul>

<pre><code>@Configuration
// 어노테이션을 등록하여
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.TYPE)
public @interface ManualBean{
}

// 해당 어노테이션을 사용한 @Component 클래스 스캔 제외
@Configuration
@ComponentScan(basePackages = {"spring"},
               excludeFilters = @Filter(type = FilterType.ANNOTATION, classes = {ManualBean.class})
               )       

// FilterType.ASSIGNABLE_TYPE을 이용한 @Component 클래스 스캔 제외
@ComponentScan(basePackages = {"spring"}, 
               excludeFilters = @Filter(type = FilterType.ASSIGNABLE_TYPE, classes = MemberDAO.class)
               )
</code></pre>
<br>

<h4>5.4. 기본 스캔 대상</h4>
<br>
<ul>
<li>@Component, @Controller, @Service, @Repository, @Aspect, @Configuration</li>
<li>위의 어노테이션을 붙인 클래스들이 @ComponentScan 대상에 포함된다.</li>
<li>@Aspect 어노테이션을 제외한 나머지는 전부 @Component 어노테이션에 대한 특수 어노테이션이다.</li>
<li>@Controller 어노테이션은 MVC와 관련이 있고 @Repository 어노테이션은 DB와 관련이 있다.</li>
</ul>

<pre><code>// @Controller 어노테이션의 선언부
@Target({ElememtType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Component // @Component 어노테이션이 붙어 컴포넌트 스캔 대상에 포함한다. 
public @interface Controller{
    @AliasFor(annotation = Component.class)
    String value() default "";
}
</code></pre>
<br>

<h4>5.5. 컴포넌스 스캔에 따른 충돌 처리</h4>
<br>
<ul>
<li>컴포넌트 스캔 기능을 사용해서 자동으로 빈을 등록할 때, 빈 이름 충돌과 수동 등록 빈과의 충돌이 있을 수 있다.</li>
<li>spring1 패키지와 spring2 패키지에 @Component를 적용한 MemberRegisterService라는 서로 다른 클래스가 존재할 때</li>
<li>@ComponentScan(basePackages = {"spring1", "spring2"}) 두 패키지를 모두 스캔하면 BeanDefinitionStoreException이 발생</li>
<li>만일 MemberDAO 클래스에 @Component 어노테이션을 붙이고 설정 클래스에 @Bean으로 memberDAO() 빈 메서드를 만들면</li>
<li>객체명이 같아, 설정 클래스에 @Bean으로 수동으로 만들어준 빈 객체만 생성된다.</li>
</ul>

<pre><code>
//설정 클래스
@Configuration
@ComponentScan(basePackages = {"spring"})
public class ApplicationConfiguration{
    //
    ...생략...
    @Bean
    public MemberDAO memberDAO(){// 수동으로 만든 빈 객체가 @Component 객체보다 우선한다.
        return new MemberDAO();
    }
}

//MemberDAO 클래스
@Component
public class MemberDAO{
    ...생략...
}
</code></pre>
<br>

<h1>Chapter 06. 빈 라이프사이클과 범위</h1>
<hr/>
<br>

<h4>6.1. 컨테이너 초기화와 종료</h4>
<br>
<ul>
<li>스프링 컨테이너는 초기화와 종료라는 라이프사이클을 갖는다.</li>
<li>AnnotationConfigApplicationContext를 생성하는 시점에 빈 객체를 생성하고, 각 빈을 연결한다.</li>
<li>컨테이너 초기화가 완료되면 컨테이너의 getBean() 등의 메서드를 사용가능하다.</li>
<li>컨테이너 사용이 끝나면 컨테이너를 종료한다.</li>
</ul>

<pre><code>//1. 컨테이너 초기화
AbstractApplicationContext applicationContext 
                          = new AnnotationConfigApplicationContext(AppConfig.class);
//2. 컨테이너에서 빈 객체를 구해서 사용
Greeter greeter = applicationContext.getBean("greeter", Greeter.class);
String msg = greeter.greet("스프링");
System.out.println(msg);
//3. 컨테이너 종료
applicationContext.close();
</code></pre>
<br>

<h4>6.2. 스프링 빈 객체의 라이프사이클</h4>
<br>
<ul>
<li>스프링 컨테이너는 빈 객체의 라이프사이클을 관리한다. 다음은 빈 객체의 라이프사이클이다.</li>
<li>객체 생성 -> 의존 설정 -> 초기화 -> 소멸</li>
</ul>
<br>

<b>스프링 인터페이스를 활용한 빈 객체의 초기화와 소멸</b>
<br>
<ul>
<li>스프링 인터페이스를 이용한 빈 객체의 초기화와 소멸</li>
<li>스프링 컨테이너는 빈 객체를 초기화하고 소멸하기 위해 지정한 메서드를 호출한다.</li>
<li>초기화와 소멸 과정이 필요한 예에는 데이터베이스 커넥션 풀이 있다. 초기화 시 Connection을 생성하고 소멸 시 close()한다.</li>
</ul>

<pre><code>//빈 객체를 초기화하고 소멸하기 위한 메서드
public interface InitializingBean{// 빈 객체 생성이 완료된 후 호출
    void afterPropertiesSet() throws Exception;
}

public interface DisposableBean{
    void destroy() throws Exception;// 스프링 컨테이너를 종료할 때 호출
}
</code></pre>
<br>

<b>커스텀 메서드를 활용한 빈 객체의 초기화와 소멸</b>
<br>
<ul>
<li>모든 클래스가 InitializingBean, DisposableBean 인터페이스를 상속받아 구현할 수 있지 않다.</li>
<li>위 인터페이스를 구현한 클래스가 아닌 다른 클래스를 스프링 빈 객체로 설정할 수 있다.</li>
<li>@Bean 태그의 initMethod, destroyMethod 속성을 이용하면 된다.</li>
<li>@Bean(initMethod="connect", destroyMethod="close") 여기서 connect()와 close() 메서드에는 매개변수가 없어야한다.</li>
</ul>
<br>

<h4>6.3. 빈 객체의 생성과 관리 범위</h4>
<br>
<ul>
<li>기본적으로 getBean()으로 빈 객체 생성 시 싱글톤(singleton) 범위(scope)를 갖는다.</li>
<li>사용 빈도가 낮으나 프로토타입(prototype) 빈 생성 범위를 설정할 수도 있다.</li>
<li>@Bean 아래에 @Scope("prototype") 범위로 설정해주면 된다.</li>
<li>prototype의 빈 객체는 스프링 컨테이너 종료 시 소멸 메서드를 실행하지 않기에, 소멸 처리 코드를 직접 작성해야 한다.</li>
</ul>
<br>

<h1>Chapter 07. AOP 프로그래밍</h1>
<hr/>
<br>

