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


   
