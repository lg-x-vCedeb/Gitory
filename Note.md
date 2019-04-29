# The Note of Learning Git
## Git Bash
	git init

	git commit

`git branch <branchname>` ()
\+ `git checkout <branchname>` 

or `git checkout -b <branchname>`

    git merge <branchname>  
    

    git rebase <branchname> 

Rebasing essentially takes a set of commits, "copies" them, and plops them down somewhere else.

### HEAD

	git checkout <hash>

    git log 
    //(to check the hash of the data)

    git checkout HEAD^ / HEAD~<num>

    git branch -f <branchname> <hash> / HEAD^ / HEAD~<num>

    git reset HEAD^ / HEAD~<num> / <branchname> / <hash> 
    //(to the local repository)

    git revert HEAD / <branchname> 
    //(the HEAD point to the reverted repository)
    //(in order to reverse changes and share those reversed change with others)

    git tag <tag> <hash> / <branchname>

    git describe <ref> (<hash> / <branchname> etc..)
    - output: echo <tag>_<numCommits>_g<hash> 
        //(<tag> is the closest ancestor tag in history and <numCommits> is how many commits away that tag is)

### About the operator ^ / ~ :
- ~ `<num>`: point to the `<num>` previous commit 
- ^ `<num>`: point to the `<num>` father commit
	 * They can be used in the string form.



### Moving work:

    git cherry-pick <hash 1 > <hash 2 > <hash 3 > <hash 4 > ... <hash n > / <branchname> 
   - Generate the new historial branch: father of all the picked hash or brach <- hash1 <- hash2 <- hash3 <- ... <- hashn / branchname
    `git cherry-pick` does not detach your HEAD   

    git rebase -i / --interactive <branchname> / HEAD^ / HEAD~<num>
    //(from the HEAD to the branch) 
    //(release a UI window which can change the order of the parameters. The UI )
	
        *git rebase / git rebase -i <ref1> <ref2> 
        //(the usage of this is to be described with the illustration of its function: 
    		- Rebasing essentially takes a set of commits[From the next commit of the origin commit to the <ref2>], "copies" them, and plops them down somewhere[<ref1>] else.)
	    *git rebase / git rebase -i 
        // it does detach your HEAD from the up-to-date <ref>.

### Remote Repository:
The `<remote>` is 'origin' in most cases.
    
    git commit --amend 

    git clone <url>

    git fetch 
   - argument mode: 
    * `git fetch <remote> <source>`
    * `git fetch <remote> <source>:<destination>`  
      * (`<source>` can be the string-code denoting the specific `<ref>`; if the `<destination>` isn't exist, the command would create a new `<destination>`)

   `git pull = `(the current branch) `git fetch` + `git merge <remote>` 
   - (The remote commits are fetched to the local remote branch (e.g. origin/master) and then merged into the current branch which the HEAD points to)
	

   `git push` (related to the push.default setting, make sure to check this setting before pushing the project)
  - argument mode:
     * `git push <remote> <place>`
         * Example: `git push origin master`
           * which means that "Go to the branch named 'master' in the repository, grab all the commits, and then go to the branch 'master' on the remote named 'origin'. Place whatever commits are missing on that branch and then tell me when you're done."
     * `git push <remote> <source>:<destination>` 
       * (Some facts are as above mentioned.)


- make your work base on the current remote repository which has already been updated.
- As the up-to-date remote repository is different from the local modified repository.

`git pull; git push` or `git fetch; git merge <remote>; git push` 
  - (The remote and the local are totally the same and they have all version items of the project)

`git pull --rebase; git push` or `git fetch; git rebase <remote>; git push`
  - (The remote and the local are different. The remote just gets the rebased version items and the local remains the modified items which have not been rebased)


### remote-tracking branches:
	
"During a clone, git creates a remote branch for every branch on the remote (like `origin/master`). It then creates a local branch that tracks the currently active branch on the remote, which is `master` in most cases. (default case)."
	
It explains why the following command output as cloning: 
  >'local branch "master" set to track remote branch "origin/master"'
    
  (The connection between `master` and `origin/master` is explained simply by the "remote tracking" property of branches.)
	
Which can be set with two methods:
  1. `git checkout -b <theBranchtoTrackRemote> <remote>` e.g `git checkout -b totallyNotMaster origin/master`
  2. `git branch -u <remote> <theBranchtoTrackRemote>` e.g. `git branch -u origin/master totallyNotMaster`

The difference of them is that "checkout" command can create a new branch as `<theBranchtoTrackRemote>` not existing.

### git config
    git status

    git config --global user.name <yourname>

    git config --global user.email <youremail>

    git diff //(TBD)
    
    ssh-keygen -t rsa -C "youremail@example.com" 
    //(Login your Github account in different devices e.g. Public PC in School, Company etc)

### Editing
    touch + [filename] : create new file.

    vi + [filename] : create new file and edit the file.

    vi + [filename] : edit the file


### Editing mode :

`ESC` : get into the command mode

`i` : edit the file (insect)

`q` or `quit` : quit without save

`w` or `write` : don't quit but save

`wq` : save and quit

`yy` (yank): copy the whole characters line

`p` (paster): paster what we just copy

`d` : delete the whole characters line

### REMARK: 
Some sentences are quoted from:
  - [Learning Git Branching](https://learngitbranching.js.org "Learning Git Branching")
