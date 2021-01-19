# Git & GitHub Cheatsheet

Hi there, just trying to learn git:)

# Git Commands
## How to push local files to GitHub using Git 

Open a respository on GitHub

Use the following commands in terminal:

``` git init ```
> open a .git file in current folder

``` git add . ```
> ask git to track all files within the folder

``` git remote add origin "the SSH link of github repository" ```
> add location of GitHub repo & allow Git to know where to upload files to

``` git remote -v ```
> ensure current git repo is connected to remote repo

``` git commit -m "commit message" -m "description box message" ```
> save changes in git locally

``` git push origin main ```
> push it to live on GitHub

Tips: 
``` git status ```
> see status of files, tracked or not (add), commited or not

``` git push -u origin master ```
> set upstream default to origin master, allow typing just 'git push' in future (no need to type 'origin master" for current repo)