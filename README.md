# Git & GitHub Cheatsheet

Hi there, just trying to learn git :)


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
> see status of files, tracked or not (add), commited or not

``` 
git push -u origin main 
```
> set upstream default to origin master, allow typing just 'git push' in future (no need to type 'origin master" for current repo)



## How to Create Branch & save changes in the New Branch in Git
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
git checkout
git commit -am "updated readme.md"
git push -u origin create-branch
```
> saved changes into the new branch

```
git branch -d create-branch
```
> delete the branch "create-branch", ususally delete old branch after merging the pull request