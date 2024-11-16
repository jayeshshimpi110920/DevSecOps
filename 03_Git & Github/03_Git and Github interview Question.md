1) **What is Git?** - Git is a __distributed version control__ system used to track changes in source code during software development, enabling multiple developers to collaborate.

2) **What is the difference between Git and GitHub?**
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




   
