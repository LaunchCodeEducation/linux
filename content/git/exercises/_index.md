---
title: "Exercises"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 115
---

## Exercises

{{% children %}}

## Questions & Answers

### What is `git`?

{{% expand "CLICK FOR ANSWER" %}}
Distributed version control software.
{{% /expand %}}

### What is a local git repository?

{{% expand "CLICK FOR ANSWER" %}}
A git repository that lives on your **local computer**. 

Development happens in local git repositories.
{{% /expand %}}

### What is a remote git repository?

{{% expand "CLICK FOR ANSWER" %}}
A git repository that lives on a team accessible **remote server**.

Code sharing and collaboration happens in remote git repositories.

Many remote git repos are hosted by Git hosting organizations like GitHub, Gitlab, or Bitbucket.
{{% /expand %}}

### When changes (commits) are made to a local repo how can the remote repo be updated?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git push
```
{{% /expand %}}

### When changes (commits) are made to a remote repo how can the local repo be updated?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git pull
```
{{% /expand %}}

### What is the command to create a new local git repository from an existing directory?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git init
```
This command will create a local git repository in the directory where it is invoked, resulting in a new hidden folder called `.git`.
{{% /expand %}}

### How can a new remote repository be created?

{{% expand "CLICK FOR ANSWER" %}}
It **varies** by Git Remote repo manager (GitHub, Gitlab, BitBucket), but usually consists of **working through a Web based GUI to name and create a new remote repo**.
{{% /expand %}}

### What is the command to add a remote repo to a local repo?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git remote add [remote-name] [remote-URI]
```
{{% /expand %}}

### What are the steps of the basic git workflow?

{{% expand "CLICK FOR ANSWER" %}}
1. stage
1. commit
1. push

```bash
git add files-to-be-committed
git commit -m "commit message title" -m "commit message body"
git push
```
{{% /expand %}}

### What is forking a remote repository?

{{% expand "CLICK FOR ANSWER" %}}
Creating a copy of a remote repository you don't control to a remote repository you do control. The forked relationship allows you make changes to your remote repo and suggest them as changes to the remote repo you don't control.
{{% /expand %}}

### How do you fork a remote repository?

{{% expand "CLICK FOR ANSWER" %}}
It **varies** by Git remote repo manager, but usually there is a **fork** button and web GUI to guide the process.
{{% /expand %}}

### What is cloning a remote repository?

{{% expand "CLICK FOR ANSWER" %}}
Cloning a remote repo **creates a brand new directory and local git repo** onto your local computer from the existing remote repo.

In addition to copying all repo files (including the `.git` folder) it automatically **adds a new remote to the local repo** using the URI of the cloned location.
{{% /expand %}}

### How do you clone a remote repository?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git clone [remote-repo-URI]
```
A web address (URL) like `https://github.com/LaunchCodeTechnicalTraining/linux` is a valid remote repo URI that can be used with `git clone`.
{{% /expand %}}

### What is a branch?

{{% expand "CLICK FOR ANSWER" %}}
A branch is an independent line of development.

A new branch is a copy of an existing branch with the full set of files, and history. Changes can be made to files and new commits can be added without altering the files or history of the original branch.

This gives you the ability to add new work in a safe environment.
{{% /expand %}}

### What is the command to create a new branch?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git branch [new-branch-name]
```
{{% /expand %}}

### What is the command to change into an existing branch?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git checkout [existing-branch-name]
```
{{% /expand %}}


### What is the command to both create and change into a new branch?

{{% expand "CLICK FOR ANSWER" %}}
```bash
git checkout -b [new-branch-name]
```
{{% /expand %}}

### What is a merge?

{{% expand "CLICK FOR ANSWER" %}}
A merge is a combination of two branches. 

The files and histories need to be merged together so file changes and histories can be combined as the new history of the project.
{{% /expand %}}

### What is a merge conflict?

{{% expand "CLICK FOR ANSWER" %}}
A merge conflict is when two merging branches have conflicting information between the contents of a file. 

Both branches would have to change the same line of the same file in different ways to create a conflict.

Conflicts must be manually resolved before the merge can be considered complete.
{{% /expand %}}

### What are the two merge strategies introduced in this course?

{{% expand "CLICK FOR ANSWER" %}}
Traditional `merge` and `rebase`.
{{% /expand %}}