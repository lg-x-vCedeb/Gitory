Git Bash

git init

git commit

git branch <branchname> ()
 + git checkout <branchname> 
or
git checkout -b <branchname>

git merge <branchname>

git rebase <branchname> (Rebasing essentially takes a set of commits, "copies" them, and plops them down somewhere else.)

HEAD:

git checkout <hash>

git log (to check the hash of the data)

git checkout HEAD^ / HEAD~<num>

git branch -f <branchname> <hash> / HEAD^ / HEAD~<num>

git reset HEAD^ / HEAD~<num> / <branchname> / <hash> (to the local repository)

git revert HEAD / <branchname> (the HEAD point to the reverted repository)(in order to reverse changes and share those reversed change with others)

git tag <tag> <hash> / <branchname>

git describe <ref> (<hash> / <branchname> etc..)
- output: echo <tag>_<numCommits>_g<hash> (<tag> is the closest ancestor tag in history and <numCommits> is how many commits away that tag is)

about the operator ^ / ~ :
	 ~ <num>: point to the <num> previous commit
	 ^ <num>: point to the <num> father commit

	 they can be used in the string form.



Moving work:

git cherry-pick <hash 1 > <hash 2 > <hash 3 > <hash 4 > ... <hash n > / <branchname> (generate the new historial branch: father of all the picked hash or brach <- hash1 <- hash2 <- hash3 <- ... <- hashn / branchname)
	*git cherry-pick does not detach your HEAD


git rebase -i / --interactive <branchname>(from the HEAD to the branch) / HEAD^ / HEAD~<num> (release a UI window which can change the order of the parameters. The UI )
	*git rebase / git rebase -i <ref1> <ref2> (the usage of this is to be described with the illustration of its function: 
						  	- Rebasing essentially takes a set of commits[From the next commit of the origin commit to the <ref2>], "copies" them, and plops them down somewhere[<ref1>] else.)
	*git rebase / git rebase -i does detach your HEAD from the up-to-date <ref>.




git commit --amend 

git clone <url>

git fetch

git pull = (the up-to-date branch is local master) git fetch + git merge <remote>

git push (related to the push.default setting, make sure to check this setting before pushing the project)


*make your work base on the up-to-date remote repository which has already been updated.
*As the up-to-date remote repository is different from the local modified repository.

git pull; git push
or git fetch; git merge <remote>; git push
(The remote and the local are totally the same and they have all version items of the project)

git pull --rebase; git push
or git fetch; git rebase <remote>; git push
(The remote and the local are different. The remote just gets the rebased version items and the local remains the modified items which have not been rebased)





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
