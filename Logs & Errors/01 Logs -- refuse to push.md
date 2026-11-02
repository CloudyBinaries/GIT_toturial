# Local Logs
```bash

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git reset HEAD@{2}
Unstaged changes after reset:
M       file1.txt

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git commit -am "reset the head agian"
[master d3d87e9] reset the head agian
 1 file changed, 3 insertions(+), 1 deletion(-)

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git log
commit d3d87e986b0fe9dee5574e41807737747ea7ef49 (HEAD -> master)
Author: CloudyBinaries <cloudy_binaries09@gmail.cmo>
Date:   Sun Nov 1 15:28:26 2026 +0200

    reset the head agian

commit 34f9ef7c84e67907b6437d57497971d4838e234c (origin/master, origin/HEAD)
Author: CloudyBinaries <cloudy_binaries09@gmail.cmo>
Date:   Sun Nov 1 13:53:51 2026 +0200

    4th commit in remote

commit 94af8869deae8661086e7c4c09b7823b85b2a586
Author: CloudyBinaries <cloudy_binaries09@gmail.cmo>
Date:   Sun Nov 1 13:37:53 2026 +0200

    3rd commit in repo


Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ graph
bash: graph: command not found

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ alias graph="git log ---oneline --graph --all --decorate"

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ graph
fatal: unrecognized argument: ---oneline

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ alias graph="git log --oneline --graph --all --decorate"

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ graph
* d3d87e9 (HEAD -> master) reset the head agian
* 34f9ef7 (origin/master, origin/HEAD) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git diff d3d87e9..34f9ef7
diff --git a/file1.txt b/file1.txt
index 5506436..f21a60c 100644
--- a/file1.txt
+++ b/file1.txt
@@ -1,6 +1,4 @@
 line 1 in file1_remote
 line 2 in.
 line 3 in remote.
-line 4 in remote.
-5 from local.
-5 from local _ 2.
\ No newline at end of file
+line 4 in remote.
\ No newline at end of file

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git reset --hard HEAD@{1}
HEAD is now at 34f9ef7 4th commit in remote

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git push -u origin
branch 'master' set up to track 'origin/master'.
Everything up-to-date

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ graph
* 34f9ef7 (HEAD -> master, origin/master, origin/HEAD) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git fetch | git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git branch feature

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git branch -r
  origin/HEAD -> origin/master
  origin/master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git branch 
  feature
* master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git switch 
fatal: missing branch or commit argument

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ ls
file1.txt

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git branch
* feature
  master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git commit -am "new commit from feature branch!!"
git commit -am "new commit from feature branchgit branch"
[feature b31e970] new commit from feature branchgit branch
 1 file changed, 2 insertions(+), 1 deletion(-)

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push origin
fatal: The current branch feature has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push origin feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 335 bytes | 167.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/
 * [new branch]      feature -> feature

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git fetch

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git fetch

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git branch -r
  origin/HEAD -> origin/master
  origin/feature
  origin/master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git fetch 

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git fetch 

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git remote -v
origin  D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/ (fetch)
origin  D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/ (push)

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git branch -r
  origin/HEAD -> origin/master
  origin/feature
  origin/master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git switch master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git fetch

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git switch 
fatal: missing branch or commit argument

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git commit -am "2nd commit in feature branch~~"
[feature 3f78121] 2nd commit in feature branch~~
 1 file changed, 2 insertions(+), 1 deletion(-)

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git fetch 

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ graph
* 3f78121 (HEAD -> feature) 2nd commit in feature branch~~
* b31e970 (origin/feature) new commit from feature branchgit branch
* 34f9ef7 (origin/master, origin/HEAD, master) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push origin feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 317 bytes | 158.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: error: refusing to update checked out branch: refs/heads/feature
remote: error: By default, updating the current branch in a non-bare repository
remote: is denied, because it will make the index and work tree inconsistent
remote: with what you pushed, and will require 'git reset --hard' to match
remote: the work tree to HEAD.
remote: 
remote: You can set the 'receive.denyCurrentBranch' configuration variable
remote: to 'ignore' or 'warn' in the remote repository to allow pushing into
remote: its current branch; however, this is not recommended unless you
remote: arranged to update its work tree to match what you pushed in some
remote: other way.
remote: 
remote: To squelch this message and still keep the default behaviour, set
remote: 'receive.denyCurrentBranch' configuration variable to 'refuse'.
To D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/
 ! [remote rejected] feature -> feature (branch is currently checked out)
error: failed to push some refs to 'D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push -u origin
fatal: The current branch feature has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.


Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push -u origin feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 317 bytes | 317.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: error: refusing to update checked out branch: refs/heads/feature
remote: error: By default, updating the current branch in a non-bare repository
remote: is denied, because it will make the index and work tree inconsistent
remote: with what you pushed, and will require 'git reset --hard' to match
remote: the work tree to HEAD.
remote: 
remote: You can set the 'receive.denyCurrentBranch' configuration variable
remote: to 'ignore' or 'warn' in the remote repository to allow pushing into
remote: its current branch; however, this is not recommended unless you
remote: arranged to update its work tree to match what you pushed in some
remote: other way.
remote: 
remote: To squelch this message and still keep the default behaviour, set
remote: 'receive.denyCurrentBranch' configuration variable to 'refuse'.
To D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/
 ! [remote rejected] feature -> feature (branch is currently checked out)
error: failed to push some refs to 'D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git push origin feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 317 bytes | 158.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: error: refusing to update checked out branch: refs/heads/feature
remote: error: By default, updating the current branch in a non-bare repository
remote: is denied, because it will make the index and work tree inconsistent
remote: with what you pushed, and will require 'git reset --hard' to match
remote: the work tree to HEAD.
remote: 
remote: You can set the 'receive.denyCurrentBranch' configuration variable
remote: to 'ignore' or 'warn' in the remote repository to allow pushing into
remote: its current branch; however, this is not recommended unless you
remote: arranged to update its work tree to match what you pushed in some
remote: other way.
remote: 
remote: To squelch this message and still keep the default behaviour, set
remote: 'receive.denyCurrentBranch' configuration variable to 'refuse'.
To D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/
 ! [remote rejected] feature -> feature (branch is currently checked out)
error: failed to push some refs to 'D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git pull origin
You asked to pull from the remote 'origin', but did not specify
a branch. Because this is not the default configured remote
for your current branch, you must specify a branch on the command line.

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git pull origin feature
From D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote
 * branch            feature    -> FETCH_HEAD
Already up to date.

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tut
```


# Remote Logs

```bash


Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git log --oneline
34f9ef7 (HEAD -> master) 4th commit in remote
94af886 3rd commit in repo
dbd1a5a the 2nd commit in remote repo
5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git branch
* master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git branch
  feature
* master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git switch master
Switched to branch 'master'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git status
On branch master
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ cat file1.txt
line 1 in file1_remote
line 2 in.
line 3 in remote.
line 4 in remote.
5 in local Feature Branch!!.
Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git log --oneline
b31e970 (HEAD -> feature) new commit from feature branchgit branch
34f9ef7 (master) 4th commit in remote
94af886 3rd commit in repo
dbd1a5a the 2nd commit in remote repo
5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ 

```

 