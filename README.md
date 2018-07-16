Git Hub

- CLI : Command Line Interface
- GUI
- index.html 과 css파일을 나눠서



1. echo

- 표준출력 : echo ex)echo hello
- 표준입력

1. man (manual)

echo man : echo라는 명령어의 manual을 보겠다.

검색 : /를 쓰고 찾고 싶은 단어를 쓴다.

(n : next, p : prev, shift + n)

- Ctrl + a : 명령어 맨 앞 단어로 간다.(Home 키)
- Ctrl + e : 명령어 맨 뒤 단어로 간다.(End 키)
- Ctrl + l  : clear
- Ctrl + U: 명령어 전체를 지운다.
- Ctrl + w: 단어 단위로 지운다.(word)
- Alt를 쓰면 커서를 움직일 수 있다.
- > : redirect , 새 파일 생성 혹은 덮어쓰기 

$ echo 'when i was young boy' > black_parade.txt

'when i...' 의 내용이 해당 파일에 덮어써진다. 

echo 'my fater took me' >> black_parade.txt

내용이 뒤에 붙는다. (append)

- less: 해당 파일의 내용을 보여준다.
- ls : list
- pwd : present working directory
- ls -a : all. 숨긴 파일 폴더까지 다 보여줌.
- ls -l : long format
- ls -al : all long format
- touch :파일 만들기 
- cat : concatenate
- which : 파일이 있는지 확인 
- curl:

curl -I https://github.com: githum  의 head를 담아온다.

drwxr-xr-x 2

d : directory. 파일일 경우 -

첫번째 3개 : user가 할 수 있는 일

두번째 3개: 그룹원이 할 수 있는 일

세번째 3개: 게스트가 할 수 있는 일

- wc : word count
- head : 첫번째 10줄(option 으로 지정가능(줄 수))
- tail : 끝에서 10줄
- | : 명령어 조합  (ex) head sonnets.txt | wc . sonnets.txt의 head를 word count
- tail -f : 로그 파일이 계속해서 찍힐 때. 
- space bar : 한 페이지 단위로 넘어감.
- grep: 문자열을 찾아줌. 
- ps : process status
- ps aux : 

ps aux | grep puma : puma 라는 status 만 출력

- ~: home
- / : root
- .: 현재 내 위치 그대로(pwd)
- ..: 한 단계 위로
- - : 이전에 있던 곳으로 간다. 뒤로가기
- find . -name  '*.txt': 내 위치 아래에 있는 name을 다 찾겠다.  .txt로 끝나는 파일은 다 가져와라.
- ; : 앞에 명령어를 수행한 후에 뒤 명령어를 수행한다. (앞 명령어가 정상 수행되지 않아도 뒤 명령어를 수행한다. )
- &&: 앞에 명령어가 정상 수행되야 뒤 명령어를 수행.

Git 버전 관리

- git
- github

~ $ vi .gitconfig

    [core]
    [core]
        editor = vim # nano를 vim으로

~ $ git config --global user.name "aram"

Ctrl + shift tab : 이전상태로  돌아감

~ $ git config --global user.email "aram0030@naver.com"

:~/workspace $ mkdir repos

~/workspace/repos $ mkdir website

~/workspace/repos/website

~/workspace/repos/website $ git init

Initialized empty Git repository in /home/ubuntu/workspace/repos/website/.git/

:~/workspace/repos/website (master) $ ls -a

:~/workspace/repos/website (master) $ cd .git

~/workspace/repos/website/.git (GIT_DIR!) $ ls

HEAD  branches/  config  description  hooks/  info/  objects/  refs/

~/workspace/repos/website (master) $ rm -rf .git  : git 이 더이상 관리하지 않는다. 

~/workspace/repos/website $ git init

cat .git/config

~/workspace/repos $

~/workspace/repos/website (master) $ : git init을 한 순간부터  repo. 버전관리가 가능한 repository

git add index.html : 여러 파일 중 index.html을 tracking 시작

git status

git commit  : 버전 생성

git log : log에 남는다.

git rm --cached foo.html L tracking에서 사라짐.(기본 rm일경우 tracking 가능)

git add . : 내 아래 모든 파일을 다 넣는다.

git diff : 마지막 커밋과 unstaged 상태인 파일들의 차이를 보여준다. 원래 있던 것과 add안된 상태에서는 차이점이 보이지만, add후에는 차이점 x. 



Bitbucket

git remote add origin 로컬에 있는 repo가 remote repo 로.

git push -u origin master 이후에는 git push만 해주면 된다. 

~ $ cat ~/.ssh/id_rsa.pub결과물 복사후 view profile-setting- add key에 복사 + 붙여넣기

- 오류
      fatal: refusing to merge unrelated histories
- 해결
  git pull origin master --allow-unrelated-histories  후에
  git push
  항상 처음에 git pull 후에 git push 

git  branch about-page : branch 만들기

git branch -d about-page: branch 삭제

git checkout -b about-page : -b 없는 걸 생성하고 그 위치로 감?

git add . && git commit -m 'Add About page' : git add와 commit을 한번에 

git branch -D about-page : 삭제

git branch  : 현재 branch 가 어디인지.



1. 브랜치 만들고
2. 브랜치 이동하고
3. 그 브랜치에서 작업하고
4. merge : master에서 git merge <branch name>



실행 순서



    1.git checkout -b help-page

   2.cp index.html help.html

   3.git add . && git commit -m 'Add Help'

1. git diff :master branch와 차이
2. git checkout master
3. git merge help-page
4. git push
5. git checkout -f : (HEAD)상태로 돌아간다. 최근 commit상태로 

---

$ git checkout -b test-branch

 $ git add .

$ git commit -m 'WTF'

$ git checkout master

 $ git branch -D test-branch

git log 중 제일 위에가 제일 최신

---

협업 ( master branch 기준 )

- Bitbucket
  1. User and group access
  2. 이메일 검색
  3. 권한 설정(read/write/admin)
  4. Add
  5. mkdri tmp 
  6. cd tmp
  7. clone -> 주소복사
  8. git clone
  9. git clone https://Song_aram@bitbucket.org/wonwond/website_2.git website2-copy
     =>website2-copy라는 이름으로 저장됨.
  10. git init을 안해도 됨. 왜냐하면 이미 받아온 repo가 init이된 상태기 때문에
  11. 바로 git add. && git commit
  12. git push
  13. 현재 상태는 remote에 있는 repo만 바뀜
  14. 따라서 바뀐 내용을 받아와야함 git pull
  15. conflict 가 생길 경우(git pull을 하지 않은 상태에서 수정할 경우.)
      To https://bitbucket.org/wonwond/website_2.git
       ! [rejected]        master -> master (fetch first)
      error: failed to push some refs to ''
      hint: Updates were rejected because the remote contains work that you do
      hint: not have locally. This is usually caused by another repository pushing
      hint: to the same ref. You may want to first integrate the remote changes
      hint: (e.g., 'git pull ...') before pushing again.
      hint: See the 'Note about fast-forwards' in 'git push --help' for details.
  16.
      remote: Counting objects: 3, done.
      remote: Compressing objects: 100% (3/3), done.
      remote: Total 3 (delta 2), reused 0 (delta 0)
      Unpacking objects: 100% (3/3), done.
      From https://..
         4469ed3..3700222  master     -> origin/master
      Updating 4469ed3..3700222
      error: Your local changes to the following files would be overwritten by merge:
              index.html
      Please commit your changes or stash them before you merge.
      Aborting
  1. git log
  2. merge가 어디서? a? b? remote reps? => b에 수정된상태
  3. git add. && git commit -m
  4. git pull
  5. git push

---

    remote: Counting objects: 3, done.
    
    remote: Compressing objects: 100% (3/3), done.
    
    remote: Total 3 (delta 2), reused 0 (delta 0)
    
    Unpacking objects: 100% (3/3), done.
    
    From https://bitbucket.org/wonwond/website_2
    
       445bfd6..791db1c  master     -> origin/master
    
    Auto-merging index.html
    
    CONFLICT (content): Merge conflict in index.html
    
    Automatic merge failed; fix conflicts and then commit the result.
    

=> 오류난 해당 파일로 가서 선택을 한 후, 다시 git add . & git commit -m "message" 그 다음 git push

- 협업할 때 git init하기전에 항상 git pull
