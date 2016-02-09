Git Tutorial
Git is a Distributed Version Controle System.

A VCS or VSC is a controle system that retains a history of version file.

What it's not. Basic version controle structures are ususally created using directories with several versions :

Project-v1
Project-v2

Version control systems keep track of these files over time.

Centralized VSC (Subversion and CVS) and Distributed VSC (Git and others)

Centralized
Version (user1) -x-\
Version (user2) -x- |  <-> Central repository.
Version (user3) ---/

Files in a centralized system are checked out until they are checked back in by the users ensuring that the originals are not ovewritten.

Distributed
Version (user1) --- Repo <-> | 
Version (user2) --- Repo <-> |
Version (user3) --- Repo <-> |

Files in a distributed system are independant and are merged into each other as the files are changed ans 'committed' originals can be ovewritten nut restored to older versions per user.

More info :
Takes snapshots each time you save it's current state - when you 'commit' to the change.  Each snapshot can then be restored to an earlier vesion.

This diagram shows the logic of Git distributed version control as a system that always points back to the older or original states(S).  That is each state can have additional files or modified files but nonetheless refer to the original strucutre and content.
S1    <    S2    < S3    < S4

Commiting
Each committed states are assigned a special code  (md5 hashcode) that identifies the state of commits.
In git files processed in a commit are split into three stages unmodified || modified || staged
That files move towards a commit (saved state).

This allows for users to commit all files ready for use while working on files that are is not ready for production.

Branching - this introduces branching.
At any point you can take an individual commit (state of files) and create a branch from it.  Branches allow users to work independantly from the main body of files (Master) and make changes and test them away from the main project or to create a new master from the files extracted from the main project.





To retain Git commands

Windows Power Shell (or other)

Set user name and password
git config --global user.name "example"
git config --global user.email "example@example.com"

List configurations.
git config --list 

Creating a repo
git init

Initalises the git system in the directory placing a .git system folder heirarchy allong with the files that are being controled by git.

Adding files to git
git add filename.ext (tell git to track the files status and puts it in the 'saged' category.)
git add *.ext (tell git to track all the status of all the files with that extention 'saged' category)
git add . (tell git to track all files within the present folder including subdirectories 'saged' category)


Commiting
git commit 

Commits all your files and sends you into VIM editor in order to comment on you commit. In PC/WIN flavor the commit text is handled by note pad.




