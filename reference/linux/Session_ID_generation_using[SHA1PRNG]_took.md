<h1>org.apache.catalina.util.SessionIdGeneratorBase.createSecureRandom Creation of SecureRandom instance for session ID generation using [SHA1PRNG] took [8,110] milliseconds.</h1><hr>
<br>

<p>해당 오류는 톰캣의 bin디렉토리의 catalina.sh 스트립트 중 JAVA_OPTS="$JAVA_OPTS $JSSE_OPTS 를 JAVA_OPTS="$JAVA_OPTS $JSSE_OPTS -Djava.security.egd=file:/dev/./urandom"과 같이 고치면된다.
