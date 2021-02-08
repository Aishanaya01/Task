1. What is the use of github 
GitHub is a website for developers and programmers to collaboratively work on code.
The primary benefit of GitHub is its version control system, which allows for seamless collaboration without compromising the integrity of the original project.
The projects on GitHub are examples of open-source software.

2. Private repository vs Public repository
Internal repositories are not visible to people outside of the enterprise account, including outside collaborators on organization repositories.
Public Repositories : They're visible to any user on your GitHub Enterprise instance.
Private Repositories : They're only available to the repository owner. You can add collaborators of your choise to share with.

3.How to clone
Cloning is a process of creating an identical copy of a Git Remote Repository to the local machine.

Cloning Repositories
The git clone command is used to copy an existing Git repository from a server to the local machine

git clone https://github.com/Aishanaya01/Task.git clones the repo in your current directory.
git clone https://github.com/Aishanaya01/Task.git MyFolder : clones the repo into MyFolder in your current directory.

4.How to create branches
Branching
git branch <name> : create a new branch while staying on the current branch
git checkout <name> : switch to an existing branch
git checkout -b <name> : create a new branch and switch to it
git branch <name> [<start-point>] : can be another branch name, commit SHA, HEAD or a tag name Example:
git checkout-b<name> some_other_branch
git checkout-b<name> af295
git checkout-b<name> HEAD~2 // Go back 2 commits, you will lose uncommitted work
git checkout-b<name> v1.0.5
git checkout - : quick switch to previous branch
Delete a remote branch
git push origin :<branchName> : delete a branch on the origin remote repository
git push origin -d <branchName>
Delete a local branch
git branch -d <branchName> : not delete if it has unmerged changes
git branch -D <branchName> : deletes even if it has unmerged changes

5.How to commit 
The "commit" command is used to save your changes to the local repository.
Git does not add changes to a commit automatically. You need to indicate which file and changes need to be saved before running the Git commit command.
The commit command does not save changes in remote servers, only in the local repository of Git.
syntax:
git commit -m '<topic> -m '<description>' : commit files staged with a message

6.How to change commit messages
git commit --amend -m "New message" : specify the commit message
git amend

Note: Be aware that amending the most recent commit replaces it entirely and the previous commit is removedfrom the branch's history. This should be kept in mind when working with public repositories and on branches withother collaborators.

This means that if the earlier commit had already been pushed, after amending it you will have to git push --force.

Commit message
git commit -m "Commit summary" -m "More detailed description follows here" : can pass in multiple -m arguments
Creating an empty commit
git commit -m "This is a blank commit" --allow-empty : able to easily create commits without having to edit/touch a dummy file.
The --allow-empty commit will bypass the check.

Committing on behalf of someone else
git commit-m "msg" --author "John Smith <johnsmith@example.com>" : can give them credit with the --author option.

7.What is git stash 
Sometimes you want to switch the branches, but you are working on an incomplete part of your current project. You don't want to make a commit of half-done work. Git stashing allows you to do so. 
The git stash command enables you to switch branches without committing the current branch
Generally, the stash's meaning is "store something safely in a hidden place." 
The sense in Git is also the same for stash; Git temporarily saves your data safely without committing.
syntax:
git stash : stashes all tracked files.

git stash --include-untracked/-u : include all untracked files

git stash save "message" : message with your stash to make it identifiable

git stash -keep-index/-k : leave the staging area in current state after stash

List saved stashes
git stash list : all stashes in the stack in reverse chronological order
Show Stash
git stash show : show the changes saved in the last stash
git stash show stash@{n} : specific stash
git stash show -p stash@{n} : content of the specific stash  

8.How to get back stashed content
To retrieve changes out of the stash and apply them to the current branch you’re on, you have two options:

git stash apply STASH-NAME applies the changes and leaves a copy in the stash
syntax:
git stash apply : apply last stash without removing it
git stash pop STASH-NAME applies the changes and removes the files from the stash
syntax:
git stash pop : apply last stash and remove it from the stack

9. What is origin
"origin" is the name of the remote repository where you want to publish you commits. By convention, the default remote repository is called "origin",
 but you can work with several remotes (with different names) as the same time.
 if you require more information about origin go just go with this Sometimes
 https://stackoverflow.com/questions/9529497/what-is-origin-in-git

 10.How to merge
 git merge <another_branch> : make sure you are in the branch that is getting merged into.
git merge --abort : after starting a merge, you might want to stop the merge and return everything to its pre-merge state
git merge <branch_name> --no-ff -m"<commit message>" : merge with a commit as default behaviour in fast-forward only updates the branch pointer without creating a merge commit.

11.How to resolve conflict


