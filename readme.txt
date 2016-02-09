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

git commit -m "Add a message here"

Git like most programs have a parameter flags like most applications which is symbolised by dash  -m represents add message to commit and it's parameter in text in the brackets/quotes.

Modified files.

Modified files will show up as modified in status.

An environment note - Windows PC git seems to state on the prompt shorthand status such as the following :

D:\dev_web\repos\git-basics [master +0 ~2 -0]>

The information above found between the brackets are the repository time [master], the code listed are shortforms for new/added [  +  ] and ammount, shortform for modified [  ~  ] and amount, shortform for staging or missing [  -  ] and number.
Cheking differences.

In cases where you are working in teams or cannot r
emember the satus of your project and must verify the changed files you can compare states for these files.

git diff

This command demonstrates 'unstaged' files, that is those in the process of being edited and not added to the local workflow or staged.  Once add(ed) they become staged and ready to commit. But to find the differences between staged versions of files git diff must have additional arguments.

git diff --staged

Shows the differences in the staged versions of the files.


Advanced concepts

Git Branching.  Allows you to create conccurant developements as your workflow evolves. It begins with the main trunk or master and all changes can branch away from the project for testing purposes. Braches can even be spawned from another branch.  Example.  Branching a website trunck to test the insertion of an image gallery, during it's developement a bug fix is needed on the sit so another branch is created the bug is fixed and re-commited to the site.  Following that commit the gallery is finished and it to is merged in the site.  How this occurs depends on each branches dependencies.

git branch addfonts
git checkout addfonts

To grow a branch you must tell git to 'branch' into 'name'. But creating a branch does not put on the branch therefore you must go to branch with another command 'checkout'

git checkout -b bugfix

To grow a branch and jump immediately into it right away you can 'checkout' and non-existing branch by adding -b to the later.

git branch 

Without an expression gives you a list of all branches.





