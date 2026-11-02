
# Local Logs

```bash

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git log --oneline --graph --all --decorate
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
$ git branch -r
  origin/HEAD -> origin/master
  origin/feature
  origin/master

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$  git push origin feature
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 20 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 317 bytes | 317.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
To D:/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/../gitRemote/
   b31e970..3f78121  feature -> feature

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ git switch master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitLocal/gitRemote (feature)
$ 
```


# Remote logs

```bash

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git status
On branch feature
nothing to commit, working tree clean

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git log --oneline --graph --all --decorate
* b31e970 (HEAD -> feature) new commit from feature branchgit branch
* 34f9ef7 (master) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ git switch master
Switched to branch 'master'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$  git log --oneline --graph --all --decorate
* b31e970 (feature) new commit from feature branchgit branch
* 34f9ef7 (HEAD -> master) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$  git log --oneline --graph --all --decorate
* 3f78121 (feature) 2nd commit in feature branch~~
* b31e970 new commit from feature branchgit branch
* 34f9ef7 (HEAD -> master) 4th commit in remote
* 94af886 3rd commit in repo
* dbd1a5a the 2nd commit in remote repo
* 5dd4aa2 the first commit in Remote Repo

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (master)
$ git switch feature
Switched to branch 'feature'

Dell@Alfa-Zero MINGW64 /d/Ahmed/General Programming/JavaScript for anything/javascript_tutorial/git/gitRemote (feature)
$ 
```

