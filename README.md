# git-tutorial
My first Git repo. I will be updating the readme file as I learn new stuff.

## Learnings in class:
1. What is git?
2. What is github?
3. Differences between git and github?
4. What is a repo?
5. master branch
6. Branching technique.
7. Creating a branch
8. Basic writing and formatting syntax: https://help.github.com/en/articles/basic-writing-and-formatting-syntax#task-lists

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

### Stash
- git stash save "message" : saving the current status of the branch
- git diff
- git stash list : gives a list of all the stashes with indexes
- git stash apply <index> : applies the changes related to the index to a particular branch and the index still lives in the git stash list
- git stash pop : applies the top most index to a particular branch and clears it from the git stash list
- git stash drop <index> : drops off a particular stash with the index. Both from the file and the stash list.

