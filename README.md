# esds-github-sandbox
Sandbox repository for a GitHub workshop during the ESDS 2024 event (Jan. 18-19)

## Setup Instructions

Make sure you have the following steps completed before the workshop:

- [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- Create a [GitHub](https://github.com/) account
- Install Python [miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html)
- [Generate Github Access Token](#Generate-Github-Access-Token)

Additionally, participants might find it helpful to read the Project Pythia Foundations textbook [GitHub chapters](https://foundations.projectpythia.org/foundations/getting-started-github.html).

### Setup on Windows
Git Bash should be installed by default for Windows 11. In search bar, search for `git bash` and open git bash as a new terminal on Windows

If Git Bash is not available, it can be [downloaded for Windows here](https://git-scm.com/download/win)

By default, a terminal in Github Bash will open a command line on `/c/Users/<USERNAME>`

Move onto [Downloading Github Repo](#Download-Github-Repo)

### Setup Linux

Open terminal prompt

Move onto [Downloading Github Repo](#Download-Github-Repo)

### Setup macOS

Move onto [Downloading Github Repo](#Download-Github-Repo)

## Download Github Repo

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
Can run git commands from this repo from this point

## Setting Up Git Username and Email (Optional)

It can be useful to set up `git config` options. When running commands that interact with a repo or require permissions, git will prompt you for your username, email, and password. By configuring git, the username and email can be saved locally that avoid being constantly prompted for this information

**Configure git username**

The username is the name associated with Github (not the profile full name). You can check your name by selecting Profile and checking the url (for example: https://github.com/github-username)

Set username on the terminal
```
git config --global user.name "<github-username>"
```
Verify username has been set correctly
```
git config --global user.name
```
Will print out `<github-username>` if set correctly

**Configure git email**

Github associates alll commits to an account's email address, but Github has the option keep the email private. Using Github's `noreply` pseudo email address when committing changes protects privacy and hides a developer's personal email, while still associating all changes in a commit to the correct author

To find the `noreply` email that Github has generated for your specific account:

1. Open Profile > esttings
2. Select Emails
3. Select 'Keep my email address private'
4. Select 'Block command line pushes that expose my email' (for extra protection)
5. Copy the `<username>@users.noreply.github.com` Github provides

Set the email address on the terminal
```
git config --global user.email "<username>@users.noreply.github.com"
```
Verify email address has been set correctly
```
git config --global user.email
```
Will print out `<username>@users.noreply.github.com` if set correctly

## Git and Github
### Git vs. Github

Github is a website ([github.com](https://github.com/)) that hosts git repositories. Github allows for code to be shared and makes collaboration easy. By default, Github repos are public and even people without Github logins can view all the data, code, and documentation in a repo (although Github also have private repo options).

Git is a system with a series of commands that operate a version control system that allows for programmers to track changes in code and collaborate on code in groups

Git allows for a multiple developers to develop on the same repo at the same time and cleanly manage conflicts. This works by each developer having their own local copy of a repo that they work on and then git commands are used when it is time to combine with the 'master' repo (on Github)

Git works with three main areas: 

1. a local working directory
2. a staging area
3. a remote 'master' repo

The local working directory lives on a user's computer when `git clone` is run. This is where a user can make changes to a repo locally. The staging area is middle ground between the local repo and the 'master' repo where a user can decide which changes they have made will be commited to the 'master' repo. The 'master' repo is the remote repo that lives on Github

## Github Overview:
**Repository (repo)**

Location where all data, code, and documentation are stored on Github. _This_ is a public Github repo and lives at [github.com/ProjectPythia/esds-github-sandbox](https://github.com/ProjectPythia/esds-github-sandbox)

**Branches**

Each repo starts with a default branch 'main'. But developers can add new branches to isolate development work without impacting other branches in a repo. This is also useful when working on multiple different features at the same time without the changes to one feature impacting the other. All changes can be made on a branch in isolation and then merged back into the 'main' brnach.

[For more information about Branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)

**Issues**

Issues are the way that a repo can receive and track bugs, tasks, and feature requests. If you find an issue with a repo that you are working with or have a question about functionality, you can submit an Issue to the repo for the developers to review and response to. Anyone with a Github account can submit an Issue to a repo. All open Issues are visible at the top of a Github repo

[For more information about Issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

**Fork Repo**

A fork is a new repository that is cloned from the original repository. The forked repo is a clone of the original that lives on your own Github account. You can fork any public repo on Github to your own account for experimentation and ay changes on forked repo can be submitted for review to the original repo via a Pull Request. Forking a repo is also a way to use an existing project as a starting point for your own ideas (if you do this, make sure you've checked the original repo's license)

[For more information about Forks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)

**Pull Requests**

A Pull Request allows for changes made to a repo by a user that does not have permissions to change a repo to be submitted for review. If accepted, the original repo can "Pull" the requested changes and merge them into the original repo. This is the most common way to contribute to public repos. All open Pull Requests are visible at the top of a Github repo

[For more information about Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

### Generate Github Access Token

To use git commands on the command line via the terminal require remote access to a Github account with personal access tokens. To generate a personal access token:

1. Open Github.com
2. On the top right of the website, select your personal profile
3. Select Settings
4. On the left toolbar on the bottom, select Developer Settings
5. Select Personal access tokens
6. Select Tokens (classic)
7. Select Generate new token
8. Select Generate new token (classic)
9. Give the token a name under 'Note' (for example: laptop-github)
10. Under Expiration, select 'No expiration' (you can remove tokens at anytime)
11. Under Select Scope, check top 'repo'
12. Select Generate token
13. Copy down the token locally since it will only be given once

[For more information about personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

### git commands via command line
git operates with a series of commands that are the same on all platforms (Windows/macOS/Linux) when running on the command line

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

`git add`: moves a change on a local repo into the staging area

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
`git commit`: saves changes from the local repo with an associated commit message

A message is included when `git commit` is run to provide information about what changes were made. The message is written after `-m` in quotes

```
user@user-os:~/Desktop/esds-github-sandbox$ git commit -m "new python script added"
```

Running `git commit` will move the changes from the working area and into the repo space that will be pushed to 'master' repo when `git push` is called. The changes will not show up in the 'master' repo until `git push` is called however. Often `git commit` and `git push` are called together since this moves the changes from the staging area and into the 'master' repo all at once. However, this is seperated into two steps to avoid causing conflicts on the 'master' repo if a change to a file occurs on the local directory but the local directory is out of date (which can be avoided with `git pull` to get changes before committing)

Just running `git commit` without `git push` will move the changes fully out of the local working directory into the staging area which running `git status` will warn the user about
```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```
`git push`: push commits in staging area into the 'master' repo

Running `git push` will publish changes to the 'master' repo and prompt the user for their Github username and password. Rather than using the Github password that a user logs into their account with, Github requires a user's password to be a token for security reasons. For more information about generating an access token review [Generate Github Access Token](#Generate-Github-Access-Token)

```
git push
```
`git pull`: fetch changes committed to the 'master' repo

While working on the local working directory it is possible that changes have been made to the 'master' repo. This can happen when other users push changes the 'master' repo since the local copy of a repo has been updated. Running `git pull` will fetch those changes and apply them to the local repo. If there is a chance that if the user is making changes to the same file that changes have been published to the 'master' repo then merge conflicts can occur

[For more information about Git and Github](https://gitbookdown.dallasdatascience.com/)
[For more information about Git](https://rogerdudler.github.io/git-guide/)

If you are interested in using an application instead of the command line to operate git commands, you can download [Github Desktop](https://desktop.github.com/) for Windows/macOS

### Conflicts
It is possible for a conflict to occur if two people are modifying the same lines in the same file at the same time. A conflict occurs when Git cannot automatically determine which change should take priority. A conflict marks the file and prevents a proper merge from occuring. Git will prompt the developers to fix changes to conflict before attempting to merge again

A conflict will most likely occur when a merge is attempted. This can occur when a merge starts and a conflict is found in the staging area or during a merge when a conflict is found in the remote Github repo. When `git commit` is run, Git will check to see if there are any pending changes in the working directory that are in conflict with the `git commit`. If a conflict is found, the commit will be temporarily halted until the conflict is resolved

When a conflict is found, Git will automatically attempt to merge the conflicts into a single file with a label for which changes are from the HEAD and which changes are from the local branch
```
<<<<<<< HEAD
changes from the HEAD that caused conflict
=======
changes that were added later
>>>>>>> new_branch_to_merge_later
```
Git added the merge conflict notes `<<<<<<< HEAD` and `>>>>>>> new_branch_to_merge_later` changes seperated by `=======` divider. To resolve merge conflicts, edit the conflicted file and remove the merge conflict notes that Git added

Some good ways to avoid conflicts:
- Ensure that your repo is up to date before commits (`git pull`)
- Commit often with small changes
- Use isolated branches

### Markdown

## Practice: Create Github Issues
[Try it out!](https://github.com/ProjectPythia/esds-github-sandbox/issues)
## Practice: Address Github Issues
## Practice: Fix Github Issues
## Practice: Pull Request

## Future Work: 

Get involved! Good First Issues

https://goodfirstissue.dev/

[Make a Custom Github Profile Page](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/about-your-profile)

Making a personal Github profile page for others to see when they select your profile ([some good examples](https://github.com/abhisheknaiidu/awesome-github-profile-readme))
