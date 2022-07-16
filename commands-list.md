# Commands

### Version

- `git --version`: show git version

### Git config

```bash
# set up your name and email address
git config --global user.name "Enrique Romero"
git config --global user.email "git@codercloud.io"


# change core.editor setting
git config --global core.editor "code --wait" #vscode

# open config using default editor
git config --global -e


# get global config
git config --global --list
```

### Initialize Repository (local)

```bash
# transform the current directory into a Git repository
git init

# add or set a remote repository
git remote add origin
git remote set-url origin

# copy an existing repository into a new local directory
git clone [url] # create a reference to the remote repository called origin

```

## Useful Commands List

- `git status`: display the state of the repository and staging area.
- `git add [filename]`: add a file to the staging area.
- `git add .`: add all changed files to the staging area.
- `git commit -m "[commit_message]"`: commit changes.
- `git branch`: list branches (asterisk denotes the active branch).
- `git branch -a`: list all branches (local and remote).
- `git branch [branch]`: create a branch.
- `git branch -d [branch]`: delete a branch.
- `git push origin --delete [branch]`: delete a remote branch.
- `git checkout -b [branch]`: create a new branch and switch to it.
- `git checkout [branch]`: switch to a branch.
- `git checkout -- [filename]`: discard changes to a file.
- `git merge [branch]`: merge a branch into the active branch.
- `git push origin [branch]`: push a branch to your remote repository.
- `git push`: push changes to remote repository (remembered branch).
- `git pull`: update local repository to the newest commit.
- `git pull origin [branch name]`: pull changes from remote repository.
- `git log`: view changes.
- `git log --summary`: view changes (detailed).
- `git revert [commit_id]`: revert commit