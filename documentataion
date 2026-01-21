# Git commits to commit
create a main directory named work using the command:
`mkdir work`.
Change the current working directory rune the command:
`cd work`.
In the work directory create a sub folder named `hello` by running the command:
`mkdir hello`
`cd hello` and while inside, run the command:
`git init` to initialize a git followed by the repository status:
`git status` 
run `nano hello.sh` to create a shell file and write the following content to the file
`echo "Hello, World"`
Save it using the button control + x and then select `yes` and then enter
Afterwards edit the file using by running the `nano hello.sh` command. Change the content to be as shown below.

```#!/bin/bash

echo "Hello, $1"
```

Stage the changes by running the command
`git add hello.sh`
After staging commit the changes using the ccommand:
`git commit -m "initial commit"`
Update the hello.sh file again by running the command `nano hello.sh`.
and update the content side to be as shown below

```
#!/bin/bash

### Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```
stage the changes and then make two commits for the changes by running the command:
`git add -p hello.sh` edit and then commit the firt changes, then git add the whole file then commit.
****
Run git add -p hello.sh.
Git asks to stage the specific "hunk". Type y for the comment block and n for the code block (or use s to split if they are close together).
Commit the comments: git commit -m "Add comments to script"
Stage the remaining code changes: git add hello.sh
Commit the code: git commit -m "Set default value for name"
****

# History
show the history of commits, only one line for easy reading. the comand to run is:
`git log --oneline`

### Controlled history Entries
To view the last 2 entries rune the command:
`git log -2`
To view the commits made within the last 5 min, run the command:
`git log --since="5 minutes ago"`

### Personalized history Format
To view the commit rersonalised format run the command:
`git log --pretty=format:"%h %ad | %s (%d) [%an]" --date=short`

# Check it out
Evert the working tree to its initial state, run the command:
` git checkout (hash of the commit) (name of the file)`
Restore Second Recent Snapshot use the coma use the command above and verify the content using the command:
`cat hello.sh`
To return to the latest without the use of hashes, run the command 
`git checkout main`

# TAG me
To tag the currect/latest commit as v1 run the command
`git tag v1`
Tagging the previous commit version as v1-beta
`git tag v1-beta HEAD^`
Switch to v1-beta by runnind `git checkout v1-beta` and then back to v1 by running `git checkout v1`
When listing the tagged versionns, run the command:
`git tag`

# Changed your mind?

### Reverting changes
Incase you made some errors and would like to go back to the previous version you can use the revert command as shown below:
`git restore hello.sh`
or
`git restore <hash of the commit>` to revert a specific commit

### Staging and Cleaning
Run the command below to unstage a file and clean the changes
`git reset HEAD hello.sh`
` git checkout -- hello.sh`

#### Committing and Reverting
Incase you committed unwanted changes that you'd like to undo the commit run the command below
`git revert HEAD`

### Tagging and Removing Commits:
First, tag your current commit as "oops"
`git tag oops`
Check where your "v1" tag is, by running
`git tag -l`
Reset your project to the v1 version (throws away newer commits)
`git reset --hard v1`

#### Displaying Logs with Deleted Commits:
To see the commits that no longer appear in the main history run the command:
`git log --oneline --graph --all`
To fucus on one specific ,oops, commit run
`git show oops`

#### Cleaning Unreferenced Commits:
Remove the tag keeping the commit alive:
`git tag -d oops`
Run garbage collection /Command to clean up history
`git gc`

#### Author Information
Include the email without making a new commit, but include the change in the last commit:
`git commit --amend --no-edit`
****
Author Information: Commit with specific author attribution: git commit -m "Add author comment" --author="Jim Weirich <jim@example.com>"
Fixing Author Email (Amend): To update the previous commit without generating a new one: git commit --amend --author="Jim Weirich <jim.weirich@example.com>" --no-edit
****

# Move it
Make lib directory by running the command : 
`mkdir lib`
When moving the the hello. sh to `lib/` run the command bellow:
git mv hello.sh lib/
Then commit the move by running the command 
`git commit -m "Move hello.sh to lib directory"`
Ccreating a `Makefile` in the root   

# blobs, trees and commits
#### Exploring .git/ Directory:
To exprole `.git`
run the command:
`cd .git/`
In the core directories you will find are:-
`objects/`; it store the all file content, directory structure, and history
`config`; ext file containing project-specific settings, such as your remote Repository URLs and branch tracking preferences.
`refs`; this directory has the pointers to the commit hashes.
`HEAD`  a file that tell git which branch/commit you are currently working on.

#### Latest Object Hash
To find the latest object has run the git command:
`git rev-parse HEAD`
 
 #### Dumping Directory Tree

To dump the content of the lib/ directory and the hello.sh file run the command:
`git ls-tree HEAD lib/`
To Print type: 
`git cat-file -t <hash>`
TO Print content: 
`git cat-file -p <hash>`

# Branching
Branching from the main to a a branch named `greet`, run the command:-
`git branch greet`
Switching back to the main run the command;
`git checkout main` you can replace the main with the branch you want to switch to
****Create lib/greeter.sh, stage and commit. Update lib/hello.sh, stage and commit. Update Makefile, stage and commit.****
To check the difference of the two branches by running the command:
`git diff main greet`.
Creating a file readme file. run the command;
`nano readme.md`
You will then input the comments you want and then save it

# Conflicts, merging and rebasing
Merging the main with greet, first change the branch to main by running the command:
`git checkout greet`
Then to merge run:
`git merge main`
And finally back to main:
`git checkout main`

#### Merging Main into Greet Branch (Conflict)
After changing the content of hello.sh run the command to change the branch 
`git checkout greet`
and then merge;
`git merge main` where an error erises
To resorve the error open the hello.sh file and delete the code originally from greet branch and then remove the conflict markers leaving the script from the main file
#### Rebasing Greet Branch:
To try the rebase method, we first need to "undo" our previous merge to go back to the state before the conflict.
Reset greet to the commit before the merge by running the command:
`git reset --hard HEAD~1`
Then Rebase greet onto main
`git rebase main`
Git will pause at the conflict again. You resolve the file exactly as you did before, but instead of committing, you run:
`git add lib/hello.sh`
`git rebase --continue`
#### Merging Greet into Main
after updating the greet, we the run the commands below to merge to merge greet into main
#### Understanding Fast-Forwarding and Differences
A Fast-Forward merge occurs when there is a linear path between the two branches.
Merging is a safe option that preserves the entire history of your repository, while rebasing creates a linear history by moving your feature branch onto the tip of main .

# Local and remote repositories
to clone the hello file as cloned_hello file in the woork directory, run
`git clone hello clonned_hello`
to display name and details of the repository, change to the clonned_hello folder and run the command
`git remote -v`
to list all remote and local branches, run the command;
`git branch -a`
navigate back to the work dirctory and then itno the hello file and edit the `Readme.md` file.

go back to the clone dirctory and then run the command
` git fetch origin` to fetch updates from remote;
to show logs including the fetched commits, run:
`git log --oneline --all --decorate`
merging the main from the remote  into the local, first make sure you are in the main, by running `git checkout main`
to mergege run the command
`git merge origin/main`

adding a local greet branch tracking the remote origin/greet branch run:
`git checkout -b greet origin/greet`
which creates a greet and deets it to track origin/greet
to verify run 
`git branch -vv`
adding a remote push (Add a remote to your Git repository and push the main and greet branches to the remote.)
If this repository has no remote yet, add one:
git remote add origin <remote-url>
Push both branches:
git push -u origin main
git push -u origin greet


-u sets upstream tracking.
*** the command equivalent to what i was doing before to bring changes from the remote to the local is the `git pull` command as it fetches changes from the romote repository and merge them into the current local branch

# Bare repositories
a git bare is a repository that only contains only git data and has no working directory, it usually ends with .git

creating a bare repository:
git clone --bare hello hello.git
adding a bare repository as a remote hello
cd hello
git remote add shared ../hello.git
git remote -v
change the readme.me 
nano readme.md and then edit 
commit and push,,,
to pull the changes into the cloned ripo, first switch to the cloned-greet ripo then 
git pull
