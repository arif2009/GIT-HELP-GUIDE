## GIT HELP GUIDE
> Some common and advance useful GIT command

### Upload a new repositary
```bash
$ echo # ASDf >> README.md
$ git init
$ git add README.md # . for all
$ git commit -m "Initial commit"
$ git remote add origin https://github.com/arif2009/ASDf.git
$ git push -u origin master
```
### Origin
```bash
# To show the origin
$ git remote -v

# To change the origin
$ git remote set-url origin git@github.com:arif2009/OnlineRegistrationSystem.git
```
### Clear cmd 
```bash
-> press q 
#OR 
$ clear
```
### To show the git history/log
```bash
$ git log		
$ git reflog # Show the current branch history
$ git reset --hard master@{"10 minutes ago"}		
$ git reset --hard master@{1}		
$ git reset --hard master@{14:30}		
$ git log --oneline
$ git show # Show the last commit
$ gitk # Show the log of all user changes
$ git diff # show the local changes
$ git log --graph or gitk. # Both also accept --all, which will show all the branches instead of just the current one.
$ git log --all --grep='company name must be bigger' # Search the commit log (across all branches) for the given text.
$ git shortlog -s -n
$ gitk --follow [filename] # --follow : Continue listing the history of a file beyond renames (works only for a single file).
```
### Show the git command history
```bash
$ history # http://stackoverflow.com/a/14417188
```
### Show the current branch with status
```
$ git status
```
### Fetch from and integrate with another repository or a local branch
```bash
$ git pull
$ pull origin master
$ git pull origin master --allow-unrelated-histories # If you change git origin
# Note: $ git pull = $ git fetch + $ git merge
```
### To add file
```
$ git add fiename
```
### Commit(Save state. It save locally. You can create save state as much as you can)
```bash
$ git commit -m "Message" # -a for all
```
### To Push
```
$ git push origin BranchNameToPush
```
### Push NewBranch to remot
```
$ git push origin NewBranch
```
### Git Merge
```bash
# Combines the specified branch’s history into the current branch
$ git merge BranchName

# How do I merge a version of a single file from one git branch to another?
$ git diff --stat myBranch # show the difference file between current branch to myBranch branch
$ git checkout --merge develop target.txt 
#merge target.txt from develop. Ex : $ git checkout --merge develop Web/Scripts/options/options.routing.js
$ git diff --stat myBranch # now you dont see the merged file (target.txt) in the file difference.
```
### Whene conflict use this to resolve
```
$ git mergetool
```
### To show a file in command prompt
```bash
$ cat FileName
# Open file using notpad
$ start FileName
```
### Switch branch
```bash
$ git checkout BranchName # For local
$ git checkout origin/BranchName # For remote
```
### Create a branch
```
$ git checkout -b BranchName
```
### Rename Branch
```
$ git branch -m OldName NewName
```
### Create new branch and delete the old one
```bash
$ git checkout feature-2
$ git checkout -b arif/feature-2 #This branches will be create under arif directory
$ git branch -d feature-2
```
### To discard changes in working file
```
$ git checkout FileName
```
### To get local deleted file 
```
$ git checkout -- .
```
### Show the UserName
```bash
$ git config user.name
# Show the commit of current user
$ git log --author="$(git config user.name)"
$ git log --committer="Arif"
```
### Reset local repository exactly remote master repository
```bash
$ git reset --hard origin/master

# To move a individual commit / Move head to a point. This will destroy any local modifications. Don't do it if you have uncommitted work you want to keep.

$ git reset --hard #### ($git reflog to get the desire point)
Ex.
$ git reset --hard 055c61b

# Then to push remote forcefully 
$ git push Origin BranchName -f
```
### Clone a git repository :
```bash
$ git clone RepositoryAddress
Ex.
$ git clone https://github.com/arif2009/AspMvcPractice.git

# If it prints a file path, look at the contents of that file for further information. That files also ignored
$ git config core.excludesfile
```
### To show branch’s
```bash
$ git branch -a # All branch
$ git branch # Local branch
$ git branch -r # Remote branch
$ git branch -a | grep 'search keyword' # Search branch
$ git for-each-ref --format='%(committerdate:short),%(authorname),%(refname:short)' --sort=committerdate refs/heads/ | column -t -s ',' # show branch with date
```
### Save to move another branch immediately
```bash
$ git stash # Save something to move another branch
$ git stash apply
$ git stash pop = git stash apply && git stash drop
$ git stash list # Show all list of stash
```
### Remove directory from git and local
```
$ git rm -r one-of-the-directories
$ git commit -m "Remove duplicated directory"
$ git push origin master
```
### Remove directory from git but NOT local
```
$ git rm -r --cached myFolder
```
### Add .gitignore file
```bash
# Using Command Prompt
> cd E:\Documents(Programming)\Asp.Net\AspMvcPractice
> ren .gitignore.txt .gitignore

#OR
$ touch .gitignore

$ git add .gitignore
$ git commit -m "add .gitignore file"
```
#### Push using different Account
```bash
# change URL in .git/config file
# https://youruser:password@github.com/user/repo.git
```
### Configuration
```bash
# Show the author Info
$ git config --list

# Add Email and UserName
$ git config user.email "arif.rahman2009@gmail.com"		
$ git config user.name "Arif"

# --soft indicates that the uncommitted files should be retained as working files opposed to 
# --hard which would discard them.
```
### Show the difference
```bash
# To see a list of which commits are on one branch but not another, use git log
$ git log oldbranch ^newbranch --no-merges # show commit logs for all commits on oldbranch that are not on newbranch

# Viewing Unpushed Git Commits (view all commits that doesn't exist in origin/master)
$ git log origin/master..HEAD
or
$ git log --branches --not --remotes

# You can also view the diff using the same syntax
$ git diff origin/master..HEAD
$ git diff --name-only 543840a..e1aacf1

# Show local commits in a branch :
$ git log origin/BranchName..BranchName

# Get commits only for a specific branch (mybranch - develop):
$ git cherry -v develop mybranch
# This would show all of the commits which are contained within mybranch but NOT in develop.
# if you leave off the last option (mybranch), it will compare the current branch instead.
```
### Amending the most recent commit message		
```
$ git commit --amend		
```
### Unstage
```bash
# Unstages the file in the current commit.
$ git reset <file> # Example : git reset <viewmodel.js>

# Unstages the file for future commits also. It's unstaged untill it gets added again with "$git add <file>".
$ git rm --cached <file> # Example : git rm --cached <viewmodel.js>
```
### View a specific Git commit
```bash
$ git show <revhash>
$ gitk <revhash>
$ git show --pretty="" --name-only <revhash> # It will show only name http://stackoverflow.com/a/424142/3835843)
```
### TAG
```bash
# Tag is a Lighter weight machinist than branch. It represents a version of a particular branch at a moment in time. It's like save point in database.
$ git tag 1.1.0 # Create tag named 1.1.0
$ git tag -a 1.1.5 -m "New release" # Create tag 1.1.5 with a message
$ git tag # To show already created tag
$ git show-ref --tags # To ahow the tag location
$ git tag 1.1.0 -d # Delete tag 1.1.0
$ git push --tags # push tags to remote
$ git tag -n9 or git tag -l -n9 #it will list all the tags along with annotations & 9 lines of message for every tag
$ git tag -l -n9 v3.* # will only display tags starting with "v3."
```
### Troubleshooting
```bash
# If .gitIgnor gile not working
$ git rm -r --cached .
$ git add .
$ git commit -m "Fixed untracked files"
```
### Help
> -h for command help. Ex- $ git log -h  
> GIT SCM https://git-scm.com/download/win  
> GitGuys http://www.gitguys.com  
> Github Markdown Cheatsheet https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet  
> Generate SSH Key https://github.com/shibbir/notebook#generate-ssh-key  

##### License
<a href="https://opensource.org/licenses/MIT">The MIT License</a> Copyright &copy; 2017 Arifur Rahman
