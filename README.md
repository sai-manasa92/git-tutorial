# git-tutorial
My first Git repo. I will be updating the readme file as I learn new stuff.

## Learnings in class:
1. Basic writing and formatting syntax: https://help.github.com/en/articles/basic-writing-and-formatting-syntax#task-lists
2. Setting 'Atom' as the default editor in git : git config --global core.editor "atom --wait"

## Important syntax:

### Basic git commands:
- git branch <branch_name> : creates a new branch.
- git checkout <branch_name> : changes the working directory to the particular branch.
- short cut for both of the above steps together: git checkout -b <branch_name> : Switched to a new branch <branch_name>

### Viewing all the commits:
- git log : to see the history of the commits
- press q to exit from git log
- git branch -d <branch_name> : to delete a branch locally
- git push origin —delete <branch_name> : to delete a branch remotely 


### Adding a file from local to remote:
- Creating a file locally using text editor in the folder.
- git add <file_name>
- git commit -m "Adding new file from terminal to repo"
- git push origin <branch_name>

### Stash (Add more notes on git stash: https://www.youtube.com/watch?v=d6vn5r4lWqE)
- git stash save "message" : saving the current status of the branch
- git diff
- git stash list : gives a list of all the stashes with indexes
- git stash apply <index> : applies the changes related to the index to a particular branch and the index still lives in the git stash list
- git stash pop : applies the top most index to a particular branch and clears it from the git stash list
- git stash drop <index> : drops off a particular stash with the index. Both from the file and the stash list.

### Squashing commits
After creating multiple updates and commits in the files, we might end up in a phase where we make many commits for a single file. To make the entire process much cleaner we can combine all the tiny commits into a single commit. This method is called Squashing.

#### Steps for squashing: (Refer: https://yangsu.github.io/pull-request-tutorial/)
- git rebase master
- git rebase -i HEAD~5 : 5 indicates the number of commits, i means interactive mode.
- leave the first commit with pick and replace all the other commits with 's' or 'squash' (that indicates you are squashing into the first commit)
- :wq (write and quit)
- opens up another editor allowing us to edit the commit message for the new combined commit.
- :wq (write and quit)
- git log : to check the change.
- git push origin <branch_name> -f : force pushing is essential for the changes to reflect on the remote branch during the pull request.

### Rewording a commit message
Two types of Rewording a commit message:
1. Rewording during the process of squashing. (discussed above)
2. Rewording general commits.

#### Changing the message from the very recent/ last commits
git commit --amend -m "new_message"

#### Changing the message from any other commits
- git log : to see the position of the commit
- git rebase -i HEAD~5 : 5 indicates the position of commit you want to change the message
- leave the first commit with pick and replace all the other commits with 'r' or 'reword' (that indicates you are rewording or renaming the particular commit)
- :wq (write and quit)
- opens up another editor allowing us to edit the commit message for the new combined commit.
- :wq (write and quit)
- git log : to check the change.

### Splitting a commits
When there are multiple changes in a single commit or the commit is very big that it can be saved a smaller and more meaningful works, we usually split the commit.

- git reset HEAD~ : we will unstage the changes after the reset
- git status
- git diff
- git add -
- then it would ask us whether we need to
  - Stage this hunk [y,n,q,a,d,s,e,?]? s
  - Stage this hunk [y,n,q,a,d,j,J,g,/,e,?]? y
  - Stage this hunk [y,n,q,a,d,K,g,/,e,?]? e
- Remove the changes that are recently added.
- Now save and close the files
- Commit the remaining changes with a new commit message git commit -m "message-1"
- Now do a git diff : To see what are the removed changes.
- Add them git add .
- Commit the changes with another commit message git commit -m "message-2"
- git log --online : to check the log message and confirm 2 different commit messages.
