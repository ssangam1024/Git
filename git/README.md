Day - 1 

* step 1 - Version Control (VCS) – Developers commit code to a Version Control System (VCS) like Git..
* step 2 - Build/Packaging – The committed code is pulled from VCS, compiled, and packaged into a deployable format.
* step 3 - System Testing – The packaged application is deployed to a system testing environment, where test cases validate its functionality.
* step 4 - Performance Testing – After system testing, performance testing is conducted to check scalability, speed, and stability under load.
* step 5 - UAT (User Acceptance Testing) / Pre-Production – The application is deployed to a UAT or pre-production environment, where end users validate if it meets business requirements before final approval.
* step 6 - Production/Live – Once approved, the application is deployed to the Production (Live) environment, making it available to users. The code here should be fully tested, stable, and bug-free.

Overview: 
Developers commit code to Version Control (VCS) → Code is built and packaged → Tested in System & Performance Testing → Verified in UAT/Pre-Prod → Finally deployed to Production (Live) for end users.

Requirements for a system to store code: 

Any system which satisfies below three points is a Version Control System
1. Common Server/Application/System to store the code from multiple developers.
2. Version should be maintained for every change.
3. Multiple users should be allowed to work on same files/code.


Architectures of VCS: 

1. Client Server Architectures: developer works with a central server to store and manage code. this system can be classified into two types. 

        a. connected : 1. Clients (developers) must stay continuously connected to the central server.
                       2. Administrators are required to take backups and also to replicate to multi-sites.
                       3. Network connectivity issues could disrupt developers in doing the work. 

        b. disconnected: 1. Clients needed to be connected to servers only for getting the latest code or to submit work. Clients can work in offline mode.
                         2. Administrators are required to take backups and also to replicate to multi-sites.  

2. Distributed Architectures: 
      *  Every developer (client) has a full copy of the project on their computer. which means they can work offline and still have access to the entire history of the code.
      *  Backup of the Code is one more node - Since every developer has a full copy, each computer acts as a backup of the code.If one system crashes, the code still exists on others.
      *  Other site is one more node - If there’s another server or another developer's system, it also has a full copy of the code. This means code can be shared and recovered from multiple sources.
      *  Git is a Distributed Version Control System - Unlike Centralized VCS, where the code is stored on one server, Git saves a full copy of the code on every developer's computer. This makes it more reliable because if the server fails, the code is still safe on other computers, and faster since developers can work offline.

Day - 2 


Git Operations on a local Node:

Create a repository :(A repository (repo) in Git is a storage location where your project’s files and their entire history of changes are tracked. It can be local (on your computer) or remote (on platforms like GitHub, GitLab, or Bitbucket))
* To create a Git repository, first, make a new folder and go inside it ( example:  mkdir learninggit ; cd learninggit). Then, run git init to set up Git in that folder, which allows Git to start tracking changes.
 
Understanding Git’s three logical areas:

* Working Tree – Where your actual project files are.
* Staging Area (Index Area) – Where you prepare changes before committing.
* Local Repository – Where commits are stored in the .git directory.

Git Workflow Overview:

* Make changes in the Working Tree. 
* Add changes to the Staging Area (git add). 
* Commit changes to the Local Repo (git commit).

Day - 3

Git Operations:

Untracked files and modified file:

* Untracked files are new files that git does not track yet. They appear when you create a but haven’t added it in Git/ local repo.
* Modified files are files that Git is tracking , but they have unsaved changes/ not yet staged to commit. 

Adding Files:

* Modified files can be added to staging with git add -u.
* Untracked files need to be added separately with git add <file>.

Committing Changes:

* After adding files to the staging area, use git commit -m "message" to save changes to the local repository.

Handling Multiple Changes:

* You can add all changes at once using git add -A or git add ., and then commit them.

Ignoring Files: 

* Use a .gitignore file to tell Git which files or folders to ignore (example: bin/* to ignore the bin/ folder).

Moving Changes Back to Working Directory:

* If you want to remove a file from staging, use git reset <file>.
* To discard all changes, use git reset --hard.

Removing Files:

* Delete a file with rm <file>, then use git add . and git commit to remove it from the repo.
* Use git clean -fd to remove all untracked files.


Day - 4 

Git Basics:

* Commit: When you move changes from the staging area to the local repository, it’s called a commit. Each commit gets a unique ID.
* HEAD: It’s a pointer that shows which commit you are currently working on. If you want to move to a previous commit, you can use its commit ID
* Use git log or git log --oneline to see commit history.
    * Example: git checkout <commit-id> moves the HEAD to that commit.
    * To return to the latest commit: git checkout master.

Reverting Changes:
* If you made changes to a file (e.g., 6.txt) and want to undo them: Use git checkout -- 6.txt to revert the changes in the working tree (the file gets reset).

Git Branches:

Default Branch: The default branch in Git is usually called master.

Create a Branch:
    * Create a new branch called sprint-1 with: git branch sprint-1
    * Move to the new branch with: git checkout sprint-1
    * Or create and move to the branch in one step with: git checkout -b sprint-1

1. Working on Branches:
    * You can commit changes on the sprint-1 branch, like adding features and tests: bash CopyEdit 
2. Switching Between Branches:
    * To go back to the master branch: git checkout master
    * To go back to sprint-1: git checkout sprint-1

Example Workflow:
* Set up the ecommerce app directory, create files, and commit the changes.
* Create the branch sprint-1 to work on new features.
* After making commits for sprint-1, you can switch between master and sprint-1 branches.

Day - 5

Merging: 

Merging means taking changes from one branch and bringing them into another.

There are 2 types of merges:

 Fast-Forward Merge

* Happens when the main branch hasn’t changed.
* Git just moves the pointer forward—no extra commit is made.
* Clean and simple.
Regular Merge

* Happens when both branches have new changes.
* Git creates a new commit to combine them.
* Used more often in real-world work.

Merging branch-1 into master

* You switch to the master branch.(we need to switch to master branch before merging because that's the branch we want to apply the changes to. )
* You merge branch-1 into it.
* Since master had no changes, Git does a fast-forward merge.

Create a new branch called branch-2

* You start working on new features from the updated master.

Make a quick fix on master

* You go back to master.
* You add some info to the file.
* You save and commit the change.

Continue working in branch-2
* Add new code in branch-2.
* Save and commit the changes.

Merge branch-2 into master 
* Go to master.
* Now Git sees changes in both branches, so it creates a merge commit.

Merge conflicts:

Conflicts happen when:
* Two branches modify the same line of a file
* Or a file was modified in one and deleted in another

Can happen during:
* merge
* rebase
* pull
We need to resolve conflicts manually. 

For viewing difference use “git diff”

Git uses SHA-1 hashing to create commit IDs. Each commit is a hash of:
* The snapshot of the files
* Metadata (author, timestamp, message)
* The parent commit ID
To inspect a commit:

git cat-file -p <commit-id>

It will show:
* tree – snapshot of files
* parent – link to previous commit
* author, committer
* message

Day - 6

Remote Repository
A Remote Repository is a Git project saved on another computer / server(like online platforms). It lets you and your team work together on the same code from different places.

Two Key Actions:
* Push = Send changes from your computer → to GitHub
* Pull = Get changes from GitHub → to your computer

Changing Commit History
Rebase (Advanced):
* Lets you clean up or reorder your commits

Cherry-Pick:
* It lets you Copy a specific commit from one branch and apply it to another
Syntax: 
git cherry-pick <commit-hash>

Bare Repositories
* A Bare Repository is a repo with only the .git folder (no actual files to edit).
* Used on servers or for backup
Syntax:
git clone --bare <url>

One Local Repo → Multiple Remotes
You can link one local project to many remote repositories (like GitHub + GitLab):








