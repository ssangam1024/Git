Day 1 : 

step 1 - Version Control (VCS) – Developers commit code to a Version Control System (VCS) like Git..
step 2 - Build/Packaging – The committed code is pulled from VCS, compiled, and packaged into a deployable format.
step 3 - System Testing – The packaged application is deployed to a system testing environment, where test cases validate its functionality.
step 4 - Performance Testing – After system testing, performance testing is conducted to check scalability, speed, and stability under load.
step 5 - UAT (User Acceptance Testing) / Pre-Production – The application is deployed to a UAT or pre-production environment, where end users validate if it meets business requirements before final approval.
step 6 - Production/Live – Once approved, the application is deployed to the Production (Live) environment, making it available to users. The code here should be fully tested, stable, and bug-free.

Overview: 
Developers commit code to Version Control (VCS) → Code is built and packaged → Tested in System & Performance Testing → Verified in UAT/Pre-Prod → Finally deployed to Production (Live) for end users.

Requirements for a system to store code: 
Any system which satisfies below three points is a Version Control System
1. Common Server/Application/Sytem to store the code from muliple developers.
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

Day 2 :