---
title: "Creating Branches"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 100
---

## Viewing Branches

While inside of a git project directory `git branch` command is very useful.

Navigate your terminal to the `py-demo-web-logs` project you cloned in the previous walkthrough. 

Run the command `git branch`.

![git-branch-command](pictures/git-branch-command.png?classes=border)

Running the `git branch` command **without an argument** will show you the current branch you are working on and any additional local branches in your local repository (this project only has one branch in the local repository).

{{% notice green "Bonus" "rocket" %}}
If you would like to view all branches in the local and all remote repositories you can add the `-a` tag at the end of the `branch` command: `git branch -a`. Try it out!
![git-branch-a](pictures/git-branch-a.png?classes=border)
Notice the remote branch `bug-fix-solution` exists on the remote repository named `origin`, but is not a part of the local repository.
{{% /notice %}}

## Creating a new Branch

The `main.py` file within this project currently contains a bug. You are going to create a new branch to fix the bug and stage that change for commit.

You will need to:

1. create a new branch
2. view the new branch

![git-new-branch](pictures/git-new-branch.png?classes=border)

Run the command `git branch bug-fix`. 

Check that the branch has been created using the `git branch` command. Notice the new branch was created, but the currently checked out branch is still the `master` branch as indicated by the asterisk and green text.

## Recap:

- View existing branches with `git branch`
  - View all branches (including remote) with `git branch -a`
- Creating a new branch with `git branch [new-branch-name]`