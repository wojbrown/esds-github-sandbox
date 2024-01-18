# esds-github-sandbox
Sandbox repository for the Python & Git Tutorial during the 2024 ESDS Annual Event

## Before the Workshop

Make sure you have the following steps completed before the workshop:

- Create a [GitHub](https://github.com/) account
- Share your GitHub username to with the instructors via email or Slack
- [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Install Miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html)

Additionally, participants might find it helpful to read the Project Pythia Foundations chapters on [Getting Started with GitHub](https://foundations.projectpythia.org/foundations/getting-started-github.html) and [Getting Started with Python](https://foundations.projectpythia.org/foundations/getting-started-python.html).

### Setup

Open a terminal window (also known as a command prompt). On Linux or macOS, search for 'terminal'. On Windows, use the terminal within Git Bash.

#### On Windows
Search for `git bash` and open a new terminal window.

If Git Bash is not already installed, it can be [downloaded for Windows here](https://git-scm.com/download/win).

By default, a terminal in Git Bash will open a command line at the base directory `/c/Users/<USERNAME>`.

## GitHub Overview:
**Repository (repo)**

Location where all code and related materials are stored on Github. _This_ is a public GitHub repo and lives at [github.com/ProjectPythia/esds-github-sandbox](https://github.com/ProjectPythia/esds-github-sandbox)

Breakdown of a typical repo:

- `README.md` - The landing page for the repo that contains information such as what the project is about, who it was created by, how to install it, and displays various status badges (_this_ is a README.md)
- `__init__.py` - This file is required for Python to treat a given repo as a Python package
- `LICENSE` - License information on how others can use this repo's contents
- `environment.yml` - A file specifying the required packages to be installed in an environment to run this package
- `.gitignore` - A file that specifies untracked files, typically pointing to a cached files or a website's 'build/' directory, essentially any file that is derivative of other code in the repo
- `.github/` - fA folder containing files related to GitHub! This could include contributing guides, a code of conduct, various Github Action scripts, a codeowners file, or issue/pull templates
- Code - The functions, scripts, modules, etc..
- Tests - Testing suite that compares expected and reproduced values output from various functions with various input

## Fork GitHub Repo

## Clone GitHub Repo

If the current working directory in your terminal is not the Desktop, move to desktop with the following commands:
```
cd
cd Desktop/
```
Clone the GitHub repo esds-github-sandbox
```
git clone https://github.com/ProjectPythia/esds-github-sandbox.git
```
Move into repo on the command line
```
cd esds-github-sandbox/
```
Can run git commands from this repo from this point

[For more information about how to navigate the command line](https://swcarpentry.github.io/shell-novice/key-points.html)

## Configure Git Name and Email (Optional)

It can be useful to set up `git config` options. When running commands that interact with a repo or require permissions, git will prompt you for your username, email, and password. By configuring git, the username and email can be saved locally that avoid being constantly prompted for this information

**Configure git name**

You can configure your name in git as your GitHub username. You can check your GitHub username by selecting your profile and checking the url (for example: https://github.com/github-username).

Set name on the terminal
```
git config --global user.name "<github-username>"
```
Verify name has been set correctly
```
git config --global user.name
```
Will print out `<github-username>` if set correctly

**Configure git email**

GitHub associates all commits to an account's email address, but GitHub has the option to keep the email private. Using GitHub's `noreply` email address when committing changes protects privacy and hides a developer's personal email, while still associating all changes in a commit to the correct author.

To find the `noreply` email that Github has generated for your specific account:

1. Open Profile > Settings
2. Select 'Emails'
3. Select 'Keep my email address private'
4. Select 'Block command line pushes that expose my email' (for extra protection)
5. Copy the `<username>@users.noreply.github.com` GitHub provides

Set the email address on the terminal
```
git config --global user.email "<username>@users.noreply.github.com"
```
Verify email address has been set correctly
```
git config --global user.email
```
Will print out `<username>@users.noreply.github.com` if set correctly

## Setup Conda Environment

Create a new conda environment from the file provided in the repo
```
conda env create -f environment.yml
```
Generates a new conda env named `esds_github_workshop` based on the variables within the `environment.yml` file. Activate the new env on the command line
```
conda activate esds_github_workshop
```
The terminal will include the env name when conda is activated like `(esds_github_workshop) user@user-os:~/Desktop/esds-github-sandbox$`

Start JupyterLab by running on the command line
```
jupyter lab
```
 This command will open a browser on the machine at `localhost:8888`
 ![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/eec37215-b157-4a86-9f9a-8c86d0f6dc27)

### Common Issues and Solutions:
If the browser opens, but JupyterLab displays an empty page try `http://127.0.0.1:8888/lab` instead of the default `http://localhost:8888/lab`. If this does not work, try switching browsers (Firefox, Chrome, Safari, etc...)

If the browser opens, but JupyterLab prompts you for a password/token
![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/d512ce1a-96e4-463a-86ec-90564b4050e4)

The token that JupyterLab is expecting can be found in the terminal where `jupyter lab` command is running as `http://localhost:8888/lab?token=<TOKEN/PASSWORD>` or `http://127.0.0.1:8888/lab?token=<TOKEN/PASSWORD>`

An example of the Jupyter output:

```
[I 2024-01-17 11:40:47.517 ServerApp] Jupyter Server 2.10.0 is running at:
[I 2024-01-17 11:40:47.517 ServerApp] http://localhost:8888/lab?token=b735c83f6f7a7d31a60cb773fc9bf3b392b14227396e26c3
[I 2024-01-17 11:40:47.517 ServerApp]     http://127.0.0.1:8888/lab?token=b735c83f6f7a7d31a60cb773fc9bf3b392b14227396e26c3
[I 2024-01-17 11:40:47.517 ServerApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 2024-01-17 11:40:47.547 ServerApp]

    To access the server, open this file in a browser:
        file:///home/user/.local/share/jupyter/runtime/jpserver-6001-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/lab?token=b735c83f6f7a7d31a60cb773fc9bf3b392b14227396e26c3
        http://127.0.0.1:8888/lab?token=b735c83f6f7a7d31a60cb773fc9bf3b392b14227396e26c3
```

[For more information about JupyterLab](https://jupyterlab.readthedocs.io/en/latest/)

## Git and GitHub
### Git vs. GitHub

GitHub is a website ([github.com](https://github.com/)) that hosts git repositories. GitHub allows for code to be shared and makes collaboration easy. By default, GitHub repos are public and even people without GitHub logins can view all the data, code, and documentation in a repo (although GitHub also has private repo options).

Git is a system with a series of commands that operate a version control system that allows for programmers to track changes in code and collaborate on code in groups.

Git allows for multiple developers to develop on the same repo at the same time and cleanly manage conflicts. This works by each developer having their own local copy of a repo that they work on and then git commands are used when it is time to combine with the 'main' repo (on Github)

Git works with three main areas: 

1. a local working directory
2. a staging area
3. a remote 'main' repo

The local working directory lives on a user's computer when `git clone` is run. This is where a user can make changes to a repo locally. The staging area is the middle ground between the local repo and the 'main' repo where a user can decide which changes they have made will be committed to the 'main' repo. The 'main' repo is the remote repo that lives on GitHub

### Git Workflow
**Fork Repo**

A fork is a new repository that is cloned from the original repository. The forked repo is a clone of the original that lives on your own GitHub account. You can fork any public repo on GitHub to your own account for experimentation and any changes on forked repo can be submitted for review to the original repo via a Pull Request. Forking a repo is also a way to use an existing project as a starting point for your own ideas (if you do this, make sure you've checked the original repo's license)

![fork](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/3e35c9dc-1932-499a-a94d-24fc1a42d05c)

[For more information about Forks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)

**Branches**

Each repo starts with a default branch 'main'. But developers can add new branches to isolate development work without impacting other branches in a repo. This is also useful when working on multiple different features at the same time without the changes to one feature impacting the other. All changes can be made on a branch in isolation and then merged back into the 'main' branch

[For more information about Branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)

**Commits**

Git and GitHub take advantage of [version control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) to keep a record of changes to a repo and each individual file. Each change that a user makes to a repo is made with a 'commit' and associated commit message. Each commit contains information about which files are changed and can be compared against previous versions visually to compare differences

[For more information about Commits](https://github.com/git-guides/git-commit)

**Pull Requests**

A Pull Request allows for changes made to a repo by a user that does not have permissions to change a repo to be submitted for review. If accepted, the original repo can "Pull" the requested changes and merge them into the original repo. This is the most common way to contribute to public repos. All open Pull Requests are visible at the top of a GitHub repo

[For more information about Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

### Generating GitHub Access Tokens

To use git commands on the command line via the terminal requires remote access to a GitHub account with personal access tokens or SSH keys. To generate a personal access token:

1. Open github.com
2. On the top right of the website, select your personal profile
3. Select Settings
4. On the left toolbar on the bottom, select Developer Settings
5. Select Personal access tokens
6. Select Tokens (classic)
7. Select Generate new token
8. Select Generate new token (classic)
9. Give the token a name under 'Note' (for example: laptop-github)
10. Under Expiration, select '7 days' (you can make new tokens at anytime)
11. Under Select Scope, check top 'repo'
12. Select Generate token
13. Copy down the token locally since it will only be given once and save in a secure location (this is effectively a password)

[For more information about personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

### git commands via command line
git operates with a series of commands that are the same on all platforms (Windows/macOS/Linux) when running on the command line

`git status`: displays all local changes in the local working directory and staging area

Any changes that a user makes to their local copy of a repo can be viewed with git status. In addition, git status can also give a user information about if changes have been made to the 'main' repo since the user can downloaded their repo

If a new Python file named `example_script.py` is added to the user's local copy of the repo, running `git status` will show the new file. The new file only exists on the local repo until the changes are committed to the 'main' repo. If a file is in red then it is listed as untracked and not in the staging area to be committed in the 'main' repo.

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

By running `git add <filename>`, a local change or new file will be moved into the staging area where it can be committed into the 'main' repo. Running `git add *` will add all files in the working directory into the staging area, but specifying individual files can be useful if a user does not want to commit all changes to the 'main' repo

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

Running `git commit` will move the changes from the working area and into the repo space that will be pushed to 'main' repo when `git push` is called. The changes will not show up in the 'main' repo until `git push` is called however. Often `git commit` and `git push` are called together since this moves the changes from the staging area and into the 'main' repo all at once. However, this is separated into two steps to avoid causing conflicts on the 'main' repo if a change to a file occurs on the local directory but the local directory is out of date (which can be avoided with `git pull` to get changes before committing)

Just running `git commit` without `git push` will move the changes fully out of the local working directory into the staging area which running `git status` will warn the user about
```
user@user-os:~/Desktop/esds-github-sandbox$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```
`git push`: push commits in staging area into the 'main' repo

Running `git push` will publish changes to the 'main' repo and prompt the user for their GitHub username and password. Rather than using the GitHub password that a user logs into their account with, GitHub requires a user's password to be a token for security reasons. For more information about generating an access token review [Generating GitHub Access Tokens](#Generating-GitHub-Access-Tokens)

```
git push
```
`git pull`: fetch changes committed to the 'main' repo

While working on the local working directory it is possible that changes have been made to the 'main' repo. This can happen when other users push changes to the 'main' repo since the local copy of a repo has been updated. Running `git pull` will fetch those changes and apply them to the local repo. If there is a chance that if the user is making changes to the same file that changes have been published to the 'main' repo then merge conflicts can occur

[For more information about Git and GitHub](https://gitbookdown.dallasdatascience.com/)
[For more information about Git](https://rogerdudler.github.io/git-guide/)

If you are interested in using an application instead of the command line to operate git commands, you can download [Github Desktop](https://desktop.github.com/) for Windows/macOS

There are even more commands that can handy to learn for specific cases, [more information here]([https://github.com/git-tips/tips](https://github.com/0nn0/git-basics-cheatsheet))

### Conflicts
It is possible for a conflict to occur if two people are modifying the same lines in the same file at the same time. A conflict occurs when Git cannot automatically determine which change should take priority. A conflict marks the file and prevents a proper merge from occurring. Git will prompt the developers to fix changes to conflict before attempting to merge again

A conflict will most likely occur when a merge is attempted. This can occur when a merge starts and a conflict is found in the staging area or during a merge when a conflict is found in the remote Github repo. When `git commit` is run, Git will check to see if there are any pending changes in the working directory that are in conflict with the `git commit`. If a conflict is found, the commit will be temporarily halted until the conflict is resolved

When a conflict is found, Git will automatically attempt to merge the conflicts into a single file with a label for which changes are from the HEAD and which changes are from the local branch
```
<<<<<<< HEAD
changes from the HEAD that caused conflict
=======
changes that were added later
>>>>>>> new_branch_to_merge_later
```
Git added the merge conflict notes `<<<<<<< HEAD` and `>>>>>>> new_branch_to_merge_later` changes separated by `=======` divider. To resolve merge conflicts, edit the conflicted file and remove the merge conflict notes that Git added

Add changes some merge conflict and commit
```
git add <changed_file>
git commit -m "resolve merge conflicts"
```

Some good ways to avoid conflicts:
- Ensure that your repo is up to date before commits (`git pull`)
- Commit often with small changes
- Use isolated branches

## Practice: Create GitHub Issues
GitHub Issues track issues, bugs, and feature requests to a repo. They can be created by anyone with a Github account, even if they do not have permissions to edit the repo

[Try it out! Create an Issue for this repo](https://github.com/ProjectPythia/esds-github-sandbox/issues)

Open 'Issues' and select 'New Issues'

By default, an Issue will allow you to fill out a Title and Description to give relevant information about the Issue you are submitting
![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/ea3dffc4-d24f-46ba-a8ab-059bd7c6c5bb)

However, this repo uses Issue Templates, so when creating a new Issue you will be prompted to select a type of Issue
![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/f23f8027-0255-40e5-9e82-710dc41be039)

Instead of a blank Title and Description, when you create a Bug Report you will be prompted to fill out specific information that the template contains

![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/3820388e-279d-4d24-a4f5-0a9be5cb07de)

The issue templates in this repo are:
- `Bug Report`: Report a bug (unexpected behavior, editing mistake, etc...)
- `Content`: Report an issue with the existing content or make a request to change it
- `Infrastructure`: Report an issue with the existing Infrastructure
- `Update Resource Gallery`: Submit an update to the resource gallery

[For more information about Issue Templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository)

## Practice: Address GitHub Issues
Within Issues, open [Pre-work #3](https://github.com/ProjectPythia/esds-github-sandbox/issues)

Add a comment to the Issue with your username when you have completed the steps for Pre-Work

## Practice: Fix GitHub Issues
Create a new Issue with the title "Github Issue Practice ESDS"

Next, assign the issue to all members in your team

Within an issue, you can assign an Issue to someone by selecting 'Assignees' and searching for a username
![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/ea63d5b3-004b-48da-9d80-4e73f9e22c4f)

You can view all your open Issues at [github.com/issues](https://github.com/issues)

## Practice: Pull Request
A Pull Request allows for a developer that does not otherwise have permissions suggest changes to be merged into a branch/repo

To make a pull request, first fork this repo:

![fork](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/3e35c9dc-1932-499a-a94d-24fc1a42d05c)

Github will pop up a prompt to "Create a new fork". Accept the default options and select `Create Fork`

The forked repo will appear on your personal profile as a cloned version of the repo that you will have permissions to edit

![new-repo](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/7a8c327c-4367-480b-a99e-423382c0ce5e)

On your new forked repo, open the README.md file and edit. You can edit files directly on Github by selecting the edit button at the top of the file

![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/3f1b3f11-623b-4c19-96b2-3ea6e2480989)

Edit the file by add a new line or comment or correct a misspelling and select the green `Commit changes` option

![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/5308ae4d-b6fb-43b6-95d6-5f0ffb70b124)

The prompt replaces the command line `git commit -m "Update README.md"`

Select `Create a new branch for this commit and start a pull request`

![image](https://github.com/ProjectPythia/esds-github-sandbox/assets/22159116/a52d0189-1ed8-4687-b8ec-abfeb709e5e8)

Github will display the changes between the main branch and the new patch branch. Select `Create pull request`

Fill out `Open a pull request` with a relevant Title and a summary of description of the changes that you have added

You can view all your open Pull Requests at [github.com/pulls](https://github.com/pulls)

## Additional Practice: 

### Learn How to Use Branches
Branches are an important part of being able to work on a repo with multiple developers. You can learn how to manage branches with this [visual tutorial](https://learngitbranching.js.org/?locale=en_US)

### Learn Markdown
README.md uses Markdown to edit: [learn how to use Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

### Find Good First Issues
If you want to tackle some more Issues and contribute to open source projects, you can find some issues that repos have labeled as good first issues here:
[goodfirstissue.dev/](https://goodfirstissue.dev/)

### Fill out Your GitHub Profile Page
[Make a Custom GitHub Profile Page](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/about-your-profile)

Making a personal GitHub profile page for others to see when they select your profile ([some examples](https://github.com/abhisheknaiidu/awesome-github-profile-readme))

### Make a New Repo
[Make your own repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories) and [give your team access to it!](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/managing-teams-and-people-with-access-to-your-repository)
