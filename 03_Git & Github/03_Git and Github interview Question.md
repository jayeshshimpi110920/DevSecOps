## Git and Github Interview Question --

1) **What is Git?** - Git is a __distributed version control__ system used to track changes in source code during software development, enabling multiple developers to collaborate..
2) **what is Repository/Repo in git?** - Repo is like a file strycture that stores all files for a project. And which is continuously track changes made to these files over time, helping team work together evenly. <br>
-Git can control both **local repositories (on your own machine)** and **remote repositories (usually hosted on platform like Github, Gitlab or Bitbucket)** , allowing teamwork and backup.

3) **What is the difference between Git and GitHub?**
* **Git**: A version control tool for managing code.
* **GitHub**: A cloud-based hosting service for Git repositories.

3) **What are the advantages of Git?**
- Distributed version control
- Branching and merging
- Lightweight and fast
- Staging area for better commit control
- Reliable data integrity

<details>
<summary>4)What is Version control system and its type (expand section to see answer)--</summary>

A **Version Control System (VCS)** is a tool that helps manage changes to source code or files over time. It is commonly used in software development to track and coordinate work across multiple developers. Here are the key types and features of VCS:

---

### **Types of Version Control Systems**
1. **Local Version Control**: 
   - Maintains versions on a single local machine.
   - Example: RCS (**Revision Control System**) - stores version as patches/deltas on local disk.
   - Genrally limited to individual users
   - Cannot support collaboration betweek multiple developers.
   - Risk of losing data if the local system fails.
   - For individual project, a local VCS might suffice

2. **Centralized Version Control (CVCS)**:
   - Stores all versions in a central server.
   - Developers fetch or commit changes to the central repository.
   - Examples: **SVN (Apache Subversion), CVS(concurrent version system) -** one of oldes tool replaced by modern system.
   - Required a network connection to interact with server.
   - For small teams or organizations, a centralized version control could work well

3. **Distributed Version Control (DVCS)**:
   - Each user has a full copy of the repository, including history.
   - Allows offline work and better collaboration.
   - Examples:**Git, Mercurial.**
   - Low risk of server crash compared to centralized.
   - For modern collaborative, large-scale projects, a distributed like Git is ideal

---

### **Key Features of Version Control Systems**
- **Version Tracking**: Keeps track of changes made to files.
- **Branching and Merging**: Allows creation of independent development paths (branches) and merging them back into the main codebase.
- **Collaboration**: Multiple developers can work simultaneously without overwriting each other's changes.
- **History Management**: Records the history of changes for auditing or rollback.
- **Conflict Resolution**: Identifies and resolves conflicts when multiple users edit the same file.
- **Backup and Recovery**: Ensures code safety and provides rollback to previous versions.

---

### **Popular Tools**
1. **Git**: The most widely used DVCS, known for its speed, branching model, and distributed nature.
   - Platforms: GitHub, GitLab, Bitbucket.
2. **SVN**: A centralized system, simpler but less flexible than Git.
3. **Mercurial**: A DVCS similar to Git, with a focus on simplicity.

---
</details>


5) **What is a repository in Git?** - A repository is a storage space where your project files, along with their version history, are stored in perticular repo/directory.

6) **How do you initialize a Git repository?** - By using command ``` git init ```

---

7) **What is the difference between `git pull` and `git fetch` and 'git clone`?** -
* **git clone** - The clone command in git is used when you want to download an existing git repository to your local computer.
* **git pull** -  When you want to take changes or updates done by other developer/team member on git repository, you have to use git pull. <br>
In detail git pull is the command that fetches updates from a remote repository and merges it with the local repository/branch. It is, in actuality, a combination of `git fetch` and `git merge` called in that order.
* **git fetch** - Fetches updates from the remote repository but does NOT apply them to your local branch. used when you want to check for updates without making changes to your local branch.

Scenario --
1. Suppose you and a teammate are working on the same branch:
Your teammate pushes some updates to the remote repository.
2. You:
* Run `git fetch` to see the updates in the remote branch without affecting your current branch.
* Run `git pull` to fetch and merge those updates into your working branch. <br>
**Summary**: <br>
`git fetch` = Look at changes. <br>
`git pull` = Fetch + Apply changes.

---
8) **What is Git branch ?** - A branch is an independent line of development. It is used to develop features, fix bugs, or experiment without affecting the main codebase. <br>
-Work on new features or fixes independently. <br>
-Switch between different version of code <br>
-Merge your changes back into the main branch once they're complete and tested

9) **How do you create a new branch in Git?** -  Use the command --  `git branch <branch_name>`
10) **How do you switch branches?** Use the command: -- `git checkout <branch_name>` or in newer git version `git switch <branch_name>`
11) **How do you merge two branches?** - Use the command -- `git merge <branch_name>`

---

12) **what is Git stash ?** - Git stash temporarily saves uncommitted changes so you can work on something else without committing those changes. and them come back with your current branch once done. <br>
Command -- `git stash` <br>
- let us say you working in one of the branch and wanna switch it to other branch..... then before switching it to other branch we definaly need to commit our code before switching it, if its completed. <br>
- Once we move to other branch without commit, your committed changes still remain in your working directory-but those changes are now associated with new branch and if we commit in new branch , then those changes will saved to newer branch instead of older one.
- There is no code loss, unless you manually discard them. <br>
- This can cause confusion because you might unintentionally commit changes to the wrong branch. <br>
- Thatttt whyyyy Git stash comes into piture.

  
- **Switch without commit**: Uncommitted changes stay in your working directory and follow you to the new branch, as long as there are no conflicts.  
- **Switch with commit**: Changes are saved in the current branch, and switching is safe without affecting the new branch.  
- **Switch with stash**: Temporarily saves your changes, allowing a clean switch, and you can reapply them later.

---

13) **What is a detached HEAD in Git?** - It occurs when you checkout a commit (not a branch), leaving your HEAD pointing to a specific commit instead of a branch. <br>
-Move `HEAD` to specific commit insted of branch.
-Checking out specific commit - `git checkout <commit-hash>`
-checking out a tag - `git checkout <tag-name>`


---
## Advanced -

Q) **what if i commited code in current state let say this one is 8th commit i made just now, i wanna go  back to detached head to 6th commit which i made, and i noticed im doing wrong i want current state should be my 6th commit beacause what ever commit i made is useless.** <br>
--> If you’re in a **detached HEAD** state and want to reset your current state to a previous commit (like the 6th commit), essentially discarding all the changes and commits you made after it, you can do this safely.

Here’s what to do:

### **Steps to Discard Changes and Set to the 6th Commit:**

1. **Move to the 6th Commit:**
   ```bash
   git checkout <6th-commit-hash>
   ```

2. **Reset the Branch to the 6th Commit:**
   If you're currently in the detached HEAD, you’ll first need to reattach to your branch and then reset it:
   ```bash
   git checkout <branch-name>  # Attach to your branch (e.g., 'main') (just to go current state, not in 6th commit)
   git reset --hard <6th-commit-hash>  # Reset to the 6th commit 
   ```

3. **Clean Up the Detached HEAD:**
   - After `git reset --hard`, your branch will now point to the 6th commit.
   - The commits you made after the 6th commit (like the 8th one) will no longer exist in the branch unless they are part of the **reflog** (reflog below) .

### **What Each Command Does:**

- **`git checkout <commit-hash>`**: Switches to the specified commit, entering a detached HEAD state.
- **`git reset --hard <commit-hash>`**: Moves the branch pointer to the specified commit and discards all changes/commits made after it.

### **Warning:**
- **Use `--hard` carefully**, as it permanently removes uncommitted changes and the history of commits beyond the specified point. 
- If you later realize you need the discarded commits, you can recover them using `git reflog`.

---

Q) **What is git rebase?** - git rebase is a command used in Git to integrate changes from one branch into another by reapplying commits on top of the target branch. It provides a cleaner, linear commit history compared to merging.<br>
**How it works?** <br>
- Git finds all commits from current branch that are not in the target branch.
- It replays these commit one by one on top of target branch.
- Syntax - `git rebase <branch-name>` the branch-name , the branch you want to rebase onto.
- lets say you working on `feature` branch and 'git checkout feature` and then rebase onto main `git rebase main` . Git reapplies feature branch commits on top of latest main
- if conflict occur, git pause the rebase and resolve the conflict in your editor. and then `git add <file>` and `git rebase --continue`
- Now your `feature` branch now has a clean history based on the latest `main`
<br>
**Advantage of rebase than merge**
- Cleaner commit history (linear, no merge commits)
- Easier to read and review history
**Disadvantage of rebase** -
- Use rebase for private branches and local changes, For shared branches prefer `merge` to avoid rewriting shared history.
- Rewriting history can cause issues if the branch has already been shared (e.g., force-pushing rebased changes can break others' work).

---

Q) **How do you resolve merge conflicts?** -- while merging if conflict occurs , open the conflicting file(s). manually edit to resolve conflicts. and then `git add <file>` and complete the merge with `git commit -m "merge solved"` 

Q) **what is purpose of `.gitignore` ?** -  `.gitignore` file specifies files or directories that Git should ignore, preventing them from being tracked.

Q) **How to view commit history** - Use command : `git log`

Q) **How do you delete a branch in Git?** - Locally - `git branch -d <branch-name>` and remotely `git push origin --delete <branch-name>`

Q) **What is git push command ?** - The git push command is used to share local repository changes to remote repository. It changes the remote repository with the recent commit from the fixed local branch.

Q) **What is the difference between git init and git clone?** - 
'git init' develops a new, empty Git repository in the present directory, while 'git clone' copies an existing remote repository, containing all files and history, to a local directory.

---

Q) **What is a Git bundle?** - 
A Git bundle is a collective file that wraps all data from Git repository, such as commits, branches, and tags. It acts as a handy approach for relocating a repository offline or sharing upgrades when network connection is not available. To form a git bundle, perform the following command:

`git bundle create <bundle_file> <refs>`

---
Q) **Git reflog ?** -


---

Q) **The Three-Tree Architecture ?**- 
In a typical Git repository, there is a working directory, staging area, and commit history. Each tracks the project's state at various stages.

* **Working Directory**: Refers to the current, live set of files and directories. This is the version of the project that you actively work on and modify.
* **Staging Area** (also known as the "index"): Serves as a buffer zone. Files in this area are marked for inclusion in the next commit. You control what content moves from the working directory to the staging area.
* **Commit History** (in the Git directory): Represents the timeline of commits in the form of a versioned archive. It also houses the full content of the project at relevant commit points.

Q) **What is the difference between a working directory, staging area, and repository in Git?** - 

**Working Directory**
The working directory is your playground. It's your space for experimenting, where you can edit files, merge different versions, and even create new ones.

**Staging Area (Index)**
The staging area (also known as the Index) is a kind of middle-ground. Here you can make fine adjustments to what changes will be included in your next commit. You have two types of files here:

**MDS**: Files that have been modified since your last commit  <br>
**SML**: Files that have been changed and prepared for your next commit <br>
When you're happy with your changes in the staging area, you "stage" them. Staging in this context is like flagging certain parts of your project that you want to be saved in your next commit. Notice that this step is completely optional.

**Repository (History)**
The repository is the final tier, dealing with the preservation of your work. Think of it as the local repository that serves as the safe house for all your commits. It keeps track of all changes and commits you've made, ensuring that you can still retrieve them even after major updates.

The repository is also broken down into three apparent "trees" - the Working Directory, the Staging Area, and the last one, the HEAD. The HEAD points to your most recent commit. These three trees can seem confusing at first. But really, they're straightforward to understand - they represent the current status of your project, changes that you're planning to commit, and the commits that you've confirmed you want to save in the future.























   
