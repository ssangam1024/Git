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
                  1. Every developer (client) has a full copy of the project on their computer. which means they can work offline and still have access to the entire history of the code.
                  2. Backup of the Code is one more node - Since every developer has a full copy, each computer acts as a backup of the code.If one system crashes, the code still exists on others.
                  3. Other site is one more node - If there’s another server or another developer's system, it also has a full copy of the code. This means code can be shared and recovered from multiple sources.
                  4. Git is a Distributed Version Control System - Unlike Centralized VCS, where the code is stored on one server, Git saves a full copy of the code on every developer's computer. This makes it more reliable because if the server fails, the code is still safe on other computers, and faster since developers can work offline.

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






