---
title: "Review: Forking and Cloning Repositories"
date: 
draft: false
weight: 2
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: ""
---

## Fork & Clone

<!-- ### new local existing remote -->

## Forking a Repository

A fork is simply a copy of a pre-existing repository. The major benefit of working with a forked repo is that any changes you make wont directly affect the original repository you forked. You are free to make changes to files and directories and push those changes to your forked repo. This can be very useful for your own experimentation or ideas you have that you want to add to a pre-existing project.

{{% notice note %}}
You can still submit a pull request to the original project repository you forked from your newly forked repo. Once you have made changes (preferably on a new branch: not master) you can submit that pull request through your github repo homepage. This is one way to contribute to a project as as an outside user.
{{% /notice %}}

To fork a repository you must visit the desired github project url and click on the `fork` button.

![fork-repository-button](pictures/fork-repository-button.png?classes=border)

## Cloning a Repository with Git Clone

Cloning a repo will work for any repository on github. An original project, a forked project, or a project you have created previously that you would like to access on a new machine. The command used to accomplish this task is `git clone`. 

The main purpose of cloning a repository is to access remote files *locally* so that you can review or make changes to those files.

There are a few ways to clone a repository. The simplest way is to grab the github project url and run the `git clone` command as follows:

![git-clone](pictures/git-clone.png?classes=border)

run the command `git clone https://github.com/LaunchCodeTechnicalTraining/linux.git` in the terminal while also inside the directory where you want the project to live.

This will create a new directory (inside of your current working directory) named *linux*, initializes a .git directory, and grabs all of the most recent data associated with the repository. This clone will be the most recent working version of the project.

{{% notice bonus %}}
You can also clone the repository with an additional option on the end of the command if you would like to rename the directory. You can do so by simply adding the new directory name at the end of the command: `git clone https://github.com/LaunchCodeTechnicalTraining/linux.git <newdirectoryname>`
{{% /notice %}}


- explore local files
- make local changes
- stage, commit and push