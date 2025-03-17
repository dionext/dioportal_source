---
title: "Git"
description: "Using GIT for devops tasks"
keywords: "Git, pull, push, Github, Gitlab"
lang: "en"
permalink: "devops-git"
aliases:
  - "devops-git"
---

# Git

Git is a free, open-source, distributed version control system. It makes it easier to write code using distributed teams of developers. What makes it different from previous version control systems is its ability to perform common operations (branching, committing, etc.) on your local machine, without having to modify the main repository or even having write permissions to it.

## Git Commands

git init

Initial Git setup

Specify the user name - git config --global user.name "John". Specifies the name of the user from whom commits will come.

Specify email - git config --global user.email "mail@gmail.com". Instead of mail@gmail.com you need to enter your email. Please note that it must match the one for which the account is registered in Github.

View settings - git config --list. The parameters can also be viewed in the configuration file, but this method is faster. git config -l --show-origin  
The --global option allows you to set the desired settings once, which Git will use for all repositories on your computer.

Correct display of Native letters For those who use Windows with names for folders and files in Native, you need to run the command: git config --global core.quotepath off

git add

git status

Revert changes not added to the index - git restore \[file name\]. Will delete changes in one file. To remove changes to all files, use git restore :/.  
Revert changes added to the index - git reset --hard. Returns changes from the index and discards them completely.

git fetch

The git fetch command contacts a remote repository and fetches any changes from it that you don't already have and stores them locally.

git pull

git pull origin master

The git pull command works as a combination of the git fetch and git merge commands, i.e. Git first pulls changes from the specified remote repository and then tries to merge them into the current branch.

git push The git push command is used to establish a connection with a remote repository, calculate local changes that are not in it, and actually transfer them to the above-mentioned repository. This command needs write permission to the repository, so it uses authentication.

Create a repository - git init. Initializes an empty repository.

### Working with Remotes

Remote repositories are versions of your project that are hosted on the Internet or network somewhere. You can have several of them, each of which generally is either read-only or read/write for you. [https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes)

Remote commands [https://git-scm.com/docs/git-remote](https://git-scm.com/docs/git-remote)

The git remote command is used to manage the list of remote repositories. It allows you to save long repository URLs as understandable short strings, such as "origin", so that you don't have to fill your head with all sorts of nonsense and type it every time to contact the server. You can use multiple remote repositories for work and git remote will help you add, change and delete them.

git remote -v

git remote remove \<name\> Remove the remote named \<name\>. All remote-tracking branches and configuration settings for the remote are removed.

git remote add origin git@github.com:dionext/lib-ms-spring-starter.git

Clone a remote repository - git clone \[link to remote repository\]. The project will appear in the directory where you were at the time of cloning.  
Link remote and local repositories - git remote add origin \[link to remote repository\].

View commit history - git log. Lists all commits. This command has different options, the most used one is  
\--oneline. It shows the hash in a shortened format, the branch in which the commit was made, and the text of the commit. To use this option (like any other), you need to add it after the command: git log--oneline.

## Github vs Gitlab

[https://about.gitlab.com/competition/github/](https://about.gitlab.com/competition/github/)

Note: You can't arrange repositories into folders on Github. [https://stackoverflow.com/questions/11852982/can-i-arrange-repositories-into-folders-on-github](https://stackoverflow.com/questions/11852982/can-i-arrange-repositories-into-folders-on-github)

## Github

[https://github.com/pricing](https://github.com/pricing)

### Github Actions

[https://docs.github.com/en/actions](https://docs.github.com/en/actions)

### Github Pages

[https://pages.github.com/](https://pages.github.com/)

## Gitlab

### Own Gitlab Server

[https://docs.gitlab.com/omnibus/docker/](https://docs.gitlab.com/omnibus/docker/)

[https://www.sanglyb.ru/ustanovka-sobstvennogo-git-servera-na-ubuntu-server-1604](https://www.sanglyb.ru/ustanovka-sobstvennogo-git-servera-na-ubuntu-server-1604)

Note: Gitlab consumes a lot of system resources

Installation system requirements [https://docs.gitlab.com/ce/install/requirements.html](https://docs.gitlab.com/ce/install/requirements.html)

* 4 cores is the recommended minimum number of cores and supports up to 500 users
* 4 GB RAM is the required minimum memory size and supports up to 500 users

Our experience: version 13 does not works on 2CPU/4GB, version 11 works

## Git Clients (UI)

[https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/) A free Git client for Windows and Mac Sourcetree simplifies how you interact with your Git repositories so you can focus on coding. Visualize and manage your repositories through Sourcetree's simple Git GUI.

[https://git-fork.com/](https://git-fork.com/) $59.99, free evaluation

## References

So You Think You Know Git - FOSDEM 2024 [https://www.youtube.com/watch?v=aolI\_Rz0ZqY](https://www.youtube.com/watch?v=aolI_Rz0ZqY)
