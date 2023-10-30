<!-- @format -->

git status --short
git add -A / .
git --version
git commit -a -m <msg> : push without staging
git status -help : show all option
git help --all : show all commands.

- Git think leaders can merge only. So merge excute from the "main" branch(which owns by leaders) not from child(which own by a junior).

git pull = git fetch + git merge

git merge <remote.name> / <branch>

git branch . : show [[ALL]] branchs on remote and local.
-r : show only remote branch. (git remote -v ?)
-l : ?

git clone <URL> <set.name>

git remote rename <original> <new>

git remote set-url origin <url>

git log --oneline

git revert HEAD : revert final commit
git revert HEAD~1 : last 2 commit
--no-edit : w/ skip message

git reset <commit.id>
reset v revert?

■ .gitignore
temp?.log
!main.log
