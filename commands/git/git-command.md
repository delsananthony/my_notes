# Git config and commands

## Setup git
- git config --global user.name "<username>"
- git config --global user.email "<user@email.com>"
- ### List setup credentials
  - git config --list


## Initializing a git repository
- on the terminal in your target directory, run this command: git init

## Adding a remote repository
- git remote add origin <repository_url>


## Stage changes and commit
- git status => to list all the changes you created inside the repository
- git add <files> or git add <directory>/\* => to add changed file/s and/or files under a directory
- git commit -m "<commit_message>"


## Pull and push
- git pull => must always git pull, especially if working with a team. To make sure that the code you are working in your local machine
is as updated as possible. (--rebase => to pull changes from the remote repository and merge its history with to the local repository)
if a history conflict occurs, resolve the conflict first.
- git push => after a successful commit or resolving a merge conflict, you can now push. (note: for initial push will require you to attach upstream by utilizing -U or --upstream e.g. git push --upstream origin main)


## Suggested workflow for git
- create a new directory for new features: mkdir <feature_directory>, go inside the directory
- initialized the directory to create a local repository: git init
- attach a remote repository where you wanted to develop a feature for: git remote add <repository_url>
- create a local branch: git branch -M <feature_name> or git checkout -b <feature_name> or git switch -c <feature_name>
- if an existing remote repository: git clone -b <branch> --depth=1 <remote_repository_url>
- git status, git add, git commit, git pull and git push
- checkout to a directory where you want to merge your local branch, and delete the previous feature branch (e.g.:
  from feature1 branch: git checkout main
  in the main branch: git merge feature1
  delete feature1 branch: git branch -d feature1)