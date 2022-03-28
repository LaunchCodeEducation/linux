---
title: "Cloning a Repository"
date: 2022-16-03T15:20:12-06:00
draft: false
weight: 110
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-28"
---

## Cloning a Repository with Git Clone

Cloning a repo will work for any repository on github. An original project, a forked project, or a project you have created previously that you would like to access on a new machine. The command used to accomplish this task is `git clone`. 

The main purpose of cloning a repository is to access remote files *locally* so that you can review or make changes to those files.

There are a few ways to clone a repository. The simplest way is to grab the github project url and run the `git clone` command as follows:

![git-clone](pictures/git-clone.png?classes=border)

run the command `git clone https://github.com/LaunchCodeTechnicalTraining/linux.git` in the terminal while also inside the directory where you want the project to live.

<!-- TODO: Decide what repo we want them to clone. I believe it makes the most sense for this to be a forked repo for them to make changes. We have not gone over branching yet so they will most likely be working and pushing to master -->

This will create a new directory (inside of your current working directory) named *linux*, initializes a .git directory, and grabs all of the most recent data associated with the repository. This clone will be the most recent working version of the project.

{{% notice bonus %}}
You can also clone the repository with an additional option on the end of the command if you would like to rename the root directory. You can do so by simply adding the new directory name at the end of the command: `git clone https://github.com/LaunchCodeTechnicalTraining/linux.git <newdirectoryname>`
{{% /notice %}}

## Explore Cloned Local Files

Now that you have cloned a repository onto your machine you can access the files locally. Explore what files are inside of the directory and feel free to make some changes. This will allow us to make changes locally and push them to to a remote repository.

Once changes are made we can add them to staging with `git add`.

![git-add-changes](pictures/git-add-changes.png?classes=border)

Check that the files have been adding to staging using the `git status` command.

![git-status-changes](pictures/git-status-changes.png?classes=border)

Commit the changes using `git commit`.

![git-commit-changes](pictures/git-commit-changes.png?classes=border)

Push them to the remote repo using `git push`

![git-push-changes](pictures/git-push-changes.png?classes=border)

### Recap:

This walkthrough was a refresher on the following:
- Forking a remote repository
- Cloning a Repository
  - `git clone https://github.com/git-repo-url`
- Staging, Committing, and Pushing local changes to remote repository
  - `git add`, `git commit`, `git push`