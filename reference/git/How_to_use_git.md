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
  1. Open the git bash(right click and choose the "execute git bash" on the local repository folder)
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
  1. git log : Show your commit history.
  2. git checkout [파일명]: Rollback the file.
  3. git reset [commit hashcode] : Rollback to the previous commit.
  4. git rever [commit hashcode] : Cover the latest commit with the last commit.
  5. rm -r .git : Cancel the git init command and delete the .git folder
  6. git reset : Cancel the git add command
</code>
</pre>
<br>

<h3>5. Git Branch & Merge</h3>
<pre>
<code>
  1. git branch [Branch Name] : create a branch with it's name
  2. git checkout [Branch Name] : change the branch with it's name
  3. git merge [TargetBranch] : change the current location of the branch into the target branch's location(fast-forward)
</code>
</pre>
<br>
