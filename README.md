# Git & GitHub Cheatsheet

Hi there, just trying to learn git :) 

Here're some notes I made for quick reference.


# Git Commands
## How to push local files to GitHub using Git 

1. Create a new respository on GitHub

2. Use the following commands in terminal:

``` 
git init 
```
> open a .git file in current folder

``` 
git add .
```
> ask git to track all files within the folder

``` 
git remote add origin "SSH link of the github repository" 
```
> add location of GitHub repo & allow Git to know where to upload files to

``` 
git remote -v 
```
> ensure current git repo is connected to remote repo

``` 
git commit -m "commit message" -m "description box message" 
```
> save changes in git locally

``` 
git push origin main 
```
> push it to live on GitHub

### Tips: 

``` 
git status 
```
> see status of files, tracked or not (add), committed or not

``` 
git push -u origin main 
```
> set upstream default to origin master, allow typing just 'git push' in future (no need to type 'origin master" for current repo)
```
git pull origin master --allow-unrelated-histories
```
> when git pull origin master doesn't work, use this command to tell git allow the action (git stops it default when two repo doesn't seem to connect with each other)


## How to create branch & save changes in the new branch in Git
```
git branch
```
> view all branch in current repo

```
git checkout -b new-feature
```
> create a new branch called 'new-feature'

```
git checkout main
```
> switch to branch named "main"

```
git checkout new-feature
git commit -am "updated readme.md"
git push -u origin new-feature
```
> saved changes into the new branch

```
git branch -d create-branch
```
> delete the branch "create-branch", ususally delete old branch after merging the pull request

## How to submit a pull request
PR = merge your branch (changes) into the main branch

Before submitting a PR, Within your own branch, You can:
```
git diff main
```
> show diffence between your current branch and the main branch

```
git merge main
```
> to make sure your current branch is up-to-date with main branch

Then Push your changes in your repo/branch, Submit a pull request via GitHub interface via clicking the 'Compare & pull request' button & "Create pull request"

You can also fork a project, makes changes & submit a PR to contribute to open-source projects:D

## How to undo in git
```
git log
```
> show the log all the commits made before

```
git reset --hard theHashCodeInLog
```
> go back to the specified commit without any changes made afterwards ( changes made after the commit are invisible)

```
git reset theHashCodeInLog
``` 
> unstaged changes made after the specified commit (but changes made are still visible but not saved in git)

## How to update your local copy (fetch the latest version copy from GitHub to your local machine)

```
git ls-remote origin
```
> view all available branches
> 
```
git fetch
```
> fetch all branches references from remote repo
> 
```
git pull origin [branch_name_here]
```
> Get the latest copy of file from GitHub

> git pull = git fetch + git merge
> 

## Merge others code

```
git checkout [branch you wanna merge]
git pull
git checkout [your own branch]
git merge [branch you wanna merge]
```

## When being asked about entering msg during merge

```
press "i" (i for insert)
write your merge message
press "esc" (escape)
write ":wq" (write & quit)
then press enter
```

## Getting single commit from other branch

```
git cherry-pick [commit ID]
```

## Reset back to specific commit & abort all local changes
```
git reset --hard [commit ID]
```

when push again after reset:
```
git push -f origin MyBranch
```

## Delete branches locally & remotely
local
```
git branch -d branch_name
```

remote:
```
git push -d origin <branch_name>
```

## Rename Branches
On the branch you want to rename:
```
git branch -m new-name
```

Delete the old-name remote branch and push the new-name local branch.
Stay on the target branch and:
```
git push origin :old-name new-name
```

Reset the upstream branch for the new-name local branch.
Switch to the target branch and then:
```
git push origin -u new-name
```

## Change remote origin
Check current origin
```
git remote -v
```

Change remote origin to another git repo
```
git remote set-url origin git@github.com:snowiewdev/xxxx.git
```

Then just git add, commit & push to the new place
