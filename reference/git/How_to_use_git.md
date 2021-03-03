<h1>Way to use Git</h1><hr>
<br><br>

<h3>1. Registration for User Infomation</h3>
<pre>
<code>
  1. Open the git bash.
  2. git config --global user.name "USER_NAME" : registrate your name to the local repository.
  3. git config --global user.email "USER_EMAIL" : registrate your email to the local repository.
</code>
</pre>
<br>

<h3>2. Push</h3>
<pre>
<code>
  1. 해당 깃파일에서 오른쪽 클릭을 한 후 git bash를 실행한다.(또는 cd 명령어로 해당 위치로 찾아간다)
  2. git add [파일명] : 해당 파일을 commit을 위한 tracked 상태로 만든다.
  3. git status : 현재 진행 상태를 확인할 수 있다.
  4. git rm --cached [파일명] : add 한 파일을 해제할 수 있다.
  5. git add . : untacked된 파일을 전부 add 한다.(git add *.txt : txt파일들을 전부 add한다)
  6. git commit -m "메시지" : 커밋을 진행한다.
  7. git push origin master : Push it to the master branch.
</code>
</pre>
<br>

<h3>3. Git Remote</h3>
<pre>
<code>
  1. git remote add origin "URL" : Add remote repository
  2. git remote remove origin : delete remote repository
</code>
</pre>
<br>

<h3>4. Git Modification</h3>
<pre>
<code>
  1. git checkout [파일명]: Rollback the file.
  2. git log : Show your commit history.
</code>
</pre>
<br>
