---
title: "Creating Branches"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 100
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-17"
---

### Creating a new Branch

While inside of a git project directory you can create a new branch with the `git branch` command.

Navigate your terminal to the `py-demo-web-logs` project you cloned in the previous walkthrough. 

![git-branch-command](pictures/git-branch-command.png?classes=border)

Run the command `git branch`. This will show you the current branch you are working on in addition to any other local branches you have.

{{% notice green "Bonus" "rocket" %}}
If you would like to view all local branches in addition to any remote branches you can add the -a tag at the end of your command: `git branch -a`. Try it out!
![git-branch-a](pictures/git-branch-a.png?classes=border)
You will notice that there is a remote branch `bug-fix-solution` that has been created previously on this project.
{{% /notice %}}

The main.py program within this project currently contains a bug. You are going to create a new branch to fix the bug and stage that change for commit.

![git-new-branch](pictures/git-new-branch.png?classes=border)

Run the command `git branch bug-fix`. Check that the branch has been created using the `git branch` command.