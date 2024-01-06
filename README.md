# esds-github-sandbox
Sandbox repository for a GitHub workshop during the ESDS 2024 event (Jan. 18-19)

## Setup Instructions

Make sure you have the followin steps completed before the workshop:

- [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- Create a [GitHub](https://github.com/) account
- Install Python [miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html)

Additionally, participants might find it helpful to read the Project Pythia Foundations textbook [GitHub chapters](https://foundations.projectpythia.org/foundations/getting-started-github.html).

### Setup Windows
Git Bash
- Optional Download for Windows/macOS: [Github Desktop](https://desktop.github.com/)

Open Github Bash

By default, Github Bash will open a command line on `/c/Users/<USERNAME>`

If terminal is opened in a position that is not the Desktop, move to desktop with the command:
```
cd
cd Desktop/
```
Clone Github repo esds-github-sandbox
```
git clone https://github.com/ProjectPythia/esds-github-sandbox.git
```
Move into repo on the command line
```
cd esds-github-sandbox/
```
In the cloned repo, new Github Options will be avaliable
![tutorial-image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/f8ff6fb6-68a6-404d-b713-b040dc5b48ee)

`(main)` refers to the branch that the user is currently on, will cover this is more detail in the next sections

Can run github commands from this repo from this point, [jump down to the next section to continue](#Git-and-Github)

### Setup Linux

Open terminal prompt in Desktop

If terminal is opened in a position that is not the Desktop, move to desktop with the command:

```
cd
cd Desktop/
```
Clone Github repo esds-github-sandbox
```
git clone https://github.com/ProjectPythia/esds-github-sandbox.git
```
Move into repo on the command line
```
cd esds-github-sandbox/
```
### Setup macOS

- Optional Download for Windows/macOS: [Github Desktop](https://desktop.github.com/)


## Git and Github
**Git vs. Github**

Github is a website ([github.com](https://github.com/) that hosts git repositories. Git is a system with a series of commands that operate a version control system that allows for programmers to track changes in code and collaborate on code in groups

Git allows for a multiple developers to be developing on the same repo at the same time and clearly manage conflicts. This works by each developer having their own local copy of a repo that they work on and then git commands are used when it is time to combine with the 'master' repo (on Github)

Git works with three main areas: 1. a local working directory, 2. a staging area, 3. a remote 'master' repo. The local working directory lives on a user's computer when `git clone` is run. This is where a user can make changes to a repo locally. The staging area is middle ground between the local repo and the 'master' repo where a user can decide which changes they have made will be commited to the 'master' repo. The 'master' repo is the remote repo that lives on Github

**Github Token**

**git commands via command line**
git operates with a series of commands that are the same on all platforms (Windows/macOS/Linux)

`git status`: displays all local changes in the local working directory and staging area

Any changes that a user makes to their local copy of a repo can be viewed with git status. In addition, git status can also give a user information about if changes have been made to the 'master' repo since the user can downloaded their repo

If a new Python file named `example_script.py` is added to user's local copy of the repo, running `git status` will show the new file. The new file only exists on the local repo until the changes are committed to the 'master' repo. If a file is in red then it is listed as untracked and not in the staging area to be commited in the 'master' repo.

```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is up-to-date with 'origin/main'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	example_script.py

nothing added to commit but untracked files present (use "git add" to track)
```

`git add`: moves a change on a local repo in the staging area

By running `git add <filename>`, a local change or new file will be moved into the staging area where it can be committed in to the 'master' repo. Running `git add *` will add all files in the working directory into the staging area, but specifying individual files can be useful if a user does not want to commit all changes to the 'master' repo

```
git add example_script.py
```
Running `git status` now will show that the new file is now green and is in the staging area
```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   example_script.py
```
`git restore --staged`: the opposite of `git add`, to remove a tracked change if you want to not include it in a commit
```
git restore --staged example_script.py
```
Running `git status` after `git restore` will show that the file has been returned to red and is no longer in the staging area
```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is up-to-date with 'origin/main'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	example_script.py

nothing added to commit but untracked files present (use "git add" to track)
```
`git commit`: commits a change in the local repo to the 'master' repo

Running git commit will move the changes from the working area and into the repo space that will be pushed to 'master' repo when `git push` is called. The changes will not show up in the 'master' repo until `git push` is called however. Often `git commit` and `git push` are called together since this moves the changes from the staging area and into the 'master' repo all at once. However, this is seperated into two steps to avoid causing conflicts on the 'master' repo if a change to a file occurs on the local directory but the local directory is out of date (which can be avoided with `git pull` to get changes before committing)

Just running `git commit` without `git push` will move the changes fully out of the local working directory into the staging area which running `git status` will warn the user about
```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```
`git push`: push commits in staging area into the 'master' repo

Running `git push` will publish changes to the 'master' repo and prompt the user for their Github username and password. Rather than using the Github password that a user logs into their account with, Github requires a user's password to be a token for security reasons

```
git push
```
`git pull`: fetch changes committed to the 'master' repo

While working on the local working directory it is possible that changes have been made to the 'master' repo. This can happen when other users push changes the 'master' repo since the local copy of a repo has been updated. Running `git pull` will fetch those changes and apply them to the local repo. If there is a chance that if the user is making changes to the same file that changes have been published to the 'master' repo then merge conflicts can occur

Merge conflicts


## Github Overview:
Repository (repo):

Branch:

Commit:

Pull Request:

## Practice: Create Github Issues
## Practice: Address Github Issues
## Practice: Fix Github Issues
## Practice: Pull Request

## Future Work: Good First Issues
https://goodfirstissue.dev/
