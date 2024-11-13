git - software <br>
github - service (once git repo ready to push into services like cloud, github is once of the services)

version control system - track files for changes , in a collaborative way

Repository -  folder 

.git - **hidden folder** to keep history of of all file and sub-folder
> To check files/folder inside a perticular folder we do `ls` <br> `ls -la` to check it for the hidden folder/files <br>
Inside the folder we have
> Head/config/hook/refs/description/objects  - (we not doing any here manually)

`git status` - check git repo ,which shows us tracked and untracked file.
> tracked file - are those we added into staging area, by `git add` <br>
> untracked file - are those file in folder not added into staging area

`git init` - TO initiat a git repo which is track by git (one time per project)



commit - check points
`git commit -m "file updated"`

`Write` -> `Add` -> `Commit`

`git log` -> gives all log like who commited author and which directory and commit code to uniqually identify 
`git log --oneline` short way to get a log oneliner

By doing `git log` how it knows about our name?
`git config --global user.name "jayesh shimpi"` to set name

![image](https://github.com/user-attachments/assets/5669f01a-68d4-4d7b-86e0-b1ce8dc30b18)

1) Staging
`git init`
create files or folder
`git add file1 file2` || `git add .`
`git status`

2) Commit
   `git commit -m "a good descritive message"
   git status


**git ignore** - create a file with name .gitignore 
its a file which ignore the sensitive files to add or push it to environment.
like .env and API keys and other-> how to ignore just inside .gitignore file add respective file name in each line one name and all set.

<img width="226" alt="{C1BA217D-ECF4-4CC5-8E2A-597480B7A1C2}" src="https://github.com/user-attachments/assets/338be38b-8b6d-4d19-8bf5-d5e4c812f816">

Commit behind the scence :
<img width="313" alt="{C646D215-F1BA-498C-BA7E-4CF5A3B2D085}" src="https://github.com/user-attachments/assets/977b5868-8d8a-4b86-b3b2-08c73d1a2e34">

---
## Branch (master/main)

`git branch` - just to check which branch its pointing to <br>
*master by default
<img width="337" alt="{6ADDC826-8482-4BC6-B744-A911AA1755BE}" src="https://github.com/user-attachments/assets/79c0b4bf-5cfd-498d-9da9-131e48d346fd">
Head - head points to where a branch is currently at 

how to create a new branch - <br>
`git branch newBranchNamehere`

how to move to other branch - <br>
`git checkout newBranchNamehere` or `git switch newBranchNamehere`

-> commit before switching to another branch
-> go to .git folder & checkout HEAD file
-> while working with branches they totally unaware about what is going on with other branch 

shortcuts:
`git switch -c dark-mode` (create a brANCH AND move there)
`git checkout -b pink-mode` (create a branch and move there)


## Merging the branches 

<img width="282" alt="{9B588DA0-18AC-401A-B449-C39854530492}" src="https://github.com/user-attachments/assets/2e4b580e-451e-4743-8ec0-966baf784016">

go to master/main branch - <br>
`git merge newBranchNamehere`

to delete `newBranchNamehere` our branch now 
`git branch -d newBranchNamehere`

Note: keep whatever you want , remove markers & Save :)

---
## Git Diff :

<img width="314" alt="{07BEDA88-2266-4E80-A2E6-F3C40B0E65BC}" src="https://github.com/user-attachments/assets/e48143ef-bb6c-4178-8be3-3fd700dbdc09">

Git diff : 
git a unique commit code by doing <br>
`git log --oneline` <br>

`git diff --staged` ->> to compare the changes in the staged area to the last commit
`git diff 9dd38fa 83ja99a`  ->> to check the difference between two commit of file 

---
## Git Stash
`git stash` is a command used to temporarily save uncommitted changes in your working directory without committing them. This allows you to work on something else (like switching branches) and return to your saved changes later.

> sometimes you want to switch the branches , but you are working on an incomplete part of your current project. <br>
> You don't want to make a commit of half-done work. Git stashing allows you to do so.
>  Note : Normally if we want to switch branch we need to commit the code and switch to the new branch.. and if you switch branch without committing.
> Two things Will happen -<br>
> 1) Switching to the branch carrying the changes. <br>
> 2) Git will not allow to switch the branch and asks commit or stash the changes.

**git stash command enable you to switch branches without committing the current branch.**

- create a repo, work & commit on main
- switch to another branch & work
- conflicting changes do not allow to switch branch, without commits

<img width="318" alt="{B013072A-9301-430A-A49E-3998D4C2E709}" src="https://github.com/user-attachments/assets/e9d7c6b8-807a-444c-acf6-4797e0775095">

`git checkout 9hj33u3` -> to go specific commit point
to go back used `git checkout master`

---
## Git Rebase

**git rebase** is a Git command used to integrate changes from one branch into another by moving or "rebasing" the base of a branch onto another commit. It helps to create a linear history in a repository, which can make it easier to follow the project's development.

<img width="268" alt="{20E9E8B9-D789-4114-BCCA-322A56497EE4}" src="https://github.com/user-attachments/assets/d653b696-2dd6-4885-bcf6-65e23eccfb6f">
















   
