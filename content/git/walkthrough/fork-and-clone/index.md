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

- git clone
- explore local files
- make local changes
- stage, commit and push