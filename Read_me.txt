Git Bash

git init

git commit

git branch <branchname> ()
 + git checkout <branchname> 
or
git checkout -b <branchname>

git merge <branchname>

git rebase <branchname>

HEAD:

git checkout <hash>

git log (to check the hash of the data)

git checkout HEAD^ / HEAD~<num>

git branch -f <branchname> <hash> / HEAD^ / HEAD~<num>

git reset HEAD^ / HEAD~<num> / <branchname> / <hash>

git revert HEAD / <branchname> (the HEAD point to the reverted repository)



git cherry-pick <hash 1 > <hash 2 > <hash 3 > <hash 4 > ... <hash n > / <branchname> (generate the new historial branch: father of all the picked hash or brach <- hash1 <- hash2 <- hash3 <- ... <- hashn / branchname)

git rebase -i / --interactive <branchname>(from the HEAD to the branch) / HEAD^ / HEAD~<num>



git clone <url>

git fetch

git pull




git status

git config --global user.name <yourname>

git config --global user.email <youremail>

git diff


touch + [filename] : create new file.

vi + [filename] : create new file and edit the file.

vi + [filename] : edit the file


Editing mode :

ESC : get into the command mode
i : edit the file (insect)
q or quit : quit without save
w or write : don't quit but save
wq : save and quit
yy (yank): copy the whole characters line
p (paster): paster what we just copy
d : delete the whole characters line
