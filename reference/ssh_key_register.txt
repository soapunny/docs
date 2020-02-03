SSH 키 생성 및 등록

1. ssh키 존재여부 확인 및 생성
-id_rsa.pub 파일 존재 여부 확인
cd 지정경로/.ssh
ls
-만약 키가 없다면
ssh-keygen -t rsa -b 4096 -C "이메일주소"


2. git agent에 ssh key 등록
#ssh-agent 시작
eval 'ssh-agent -s'  
#개인키 등록
ssh-add 지정경로/.ssh/id_rsa

-Could not open a connection to your authentication agent
에러 발생 시
#ssh-agent를 시작
$ eval $(ssh-agent)
#개인키를 등록
$ ssh-add ~/.ssh/id_rsa

3. gitlab에 key 추가
-파일 복사
$ cat /Users/~~~/id_rsa.pub
-등록
오른쪽 상단 프로필 - settings - SSH Keys 에서 등록

4. 테스트
$ ssh -T git@github.com

The authenticity of host... 메시지가 나오면
yes 쓰고 엔터

Hi! You've succesfully authenticated... 뜨면 성공