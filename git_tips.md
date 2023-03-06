### Initiialize local git Repo for first time: ###
- $ git config --global init.defaultBranch main
- $git init --> after first time, you can just use this, no need to config.

**This effectively turns our current directory into a git repo**

### Configure Identity (Also only needs to be done first time) ###
- $ git config --global user.name "Brandon Corey"
- $ git config --global user.email "bcorey3660@gmail.com"
  - To look at config settings do :
- $ git config --list

gitignore
  - Any files or directories passed into this hidden directory will not be shown in repository
ex)
- $ mkdir db
- $ touch db/development.sqlite3
- $ touch gitignore
- $ code .gitignore --> in VSccode --> db/*.sqlite3
  - This puts all sqlite 3 files into gitignore

### FUNDAMENTALS ###
- $ git add <file> --> adds to staging
- $ git commit -m "Commits with a mesage here!"
- $ git log --> shows commit history
- $ git status --> shows status of staged/unstaged files/directories

### GITHUB FUNDAMENTALS ###
(NOTE, YOU MUST FIRST SET UP THE REMOTE REPO ON GITHUB BEFOER ANY OF THIS)
- $ git remote add origin <remote repo URL> --> Link remote repo (origin) --> you CANNOT setup a remote repo like this if you aren't in a local repo WITH commit history
- $ git push -u origin main --> we are creating a local branch that tracks the remote branch (origin/main) --> does NOT track in real time
- $ git fetch --> will fetch/pull all/any changes in remote to your local copy of the remote reposity (origin/main) --> updates it basically
- $ git pull --ff-only || git pull --f-only origin main --> pulls straight from remote repo to main branch and merges. Also updates origin/main.
- $ git clone <remote repository URL> <local directory name> --> Pulls from remote repo, creates origin alias, creates origin/main, turns specified local directory into local git repo.
- $ gh auth refresh --> Will re-log you into to gh
- $ gh auth login --> will do the same as refresh
- $ git remote set-url origin <insert github repo url> --> Change the url of your remote repo

### BRANCHES: ###
- $ git branch <insert new branch name> --> creates to branch
- $ git checkout <insert branch name> --> switches to specified branch
- $ git checkout -b <new branch name> --> creates new branch and switches to it all at once
- $ git branch -d <insert branch name> --> deletes a branch (cannot delete branch that is currently checked out)

**NOTE:** Before merging new branch with main branch, must stage and commit changes on new branch to local repo

**NOTE:** After commiting changes on new branch, switch back to main branch, then execute the command below
- $ git merge <insert branch name> --> merges specified branch with current branch

**IF YOU WANT NEED TO RENAME MASTER TO MAIN**
- $ git branch -m master main
- $ git branch -M main

### NICE TO KNOW: ###
main --> local main branch
origin --> remote repository
origin/main --> a local copy of the main branch in origin

- $ git log --oneline --> makes commit history one line each commit
- $ git log --stat --> shows more info for commit history
- $ git commit --amend --> If working tree is clean, you can modify the PREVIOUS commit message, and add/change files/directories (must be staged alredy).
- $ git remote --> will show you the alias of your remote repository.
- $ git diff origin/main main --> compares differences between old code and new code. Usually old code will be origin/main and new will be main.
