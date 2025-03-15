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



# App Versioning
1. Initial Setup (Version 0.1.0)
   - git init
   - git branch main
   - git checkout main
   - git commit --allow-empty -m "Initial Commit"
   - git push -u origin main
   - git tag v0.1.0
2. Feature Development
   - git checkout -b feature/<feature_name>
   - git add .
   - git commt -m "<commit_messaage>"
   - git push origin feature/<feature_name>
   - create a pull request in github from feature/<feature_name> to main
   - review and approval
   - git checkout main
   - git pull origin main
   - git tag v0.2.0
   - git push origin v0.2.0
3. Bug Fixes
   - git checkout -b hotfix/fix-login-bug
   - git add .
   - git commit -m "Fix login authentication error"
   - git push origin hotfix/fix-login-bug
   - Create a pull request from hotfix/fix-login-bug to main on GitHub.
   - After merging the PR, tag main with the patch version
   - git checkout main
   - git pull origin main
   - git tag v0.2.1
   - git push origin v0.2.1
4. Major Releases
   - git checkout -b release/1.0.0
   - perform thorogh testing on the release/1.0.0 branch
   - fix any critiicl bugs found during testing
   - this is the stage for final code
   - git checkout main
   - git merge --no-ff release/1.0.0
   - git push origin main
   - git tag v1.0.0
   - git push origin v1.0.0
5. Pre-releases
   - Use -alpha, -beta, or -rc suffixes to indicate pre-release stages.
   - alpha: Early development, unstable.
   - beta: Feature-complete, for wider testing.
   - rc (release candidate): Near-final, for final testing.
   - git tag v1.0.0-alpha.1 (First alpha release of version 1.0.0)
   - git tag v1.0.0-beta.3 (Third beta release of version 1.0.0)
   - git tag v1.0.0-rc.2 (Second release candidate of version 1.0.0)
   - Practical example: 
     - Imagine you're developing a major update to your app (version 2.0.0).
     - After implementing core features, you tag an alpha release for internal testing: git tag v2.0.0-alpha.1.
     - After fixing initial bugs and stabilizing, you tag a beta release for wider testing: git tag v2.0.0-beta.1
     - After a couple of beta releases, and after all known bugs are fixed, you create a release candidate: git tag v2.0.0-rc.1
