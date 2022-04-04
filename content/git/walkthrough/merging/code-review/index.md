---
title: "Review Existing Code"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 100
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-30"
---

## Setup

Project repository: [py-demo-web-logs-continued](https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-continued)

- Fork the project repository to you your personal github account.

- Clone your forked repository onto your personal machine.

## Code Review

{{% notice note %}}
In the example below we are cloning the github repo into the `home/student/Desktop` directory.
{{% /notice %}}

![git-clone](pictures/git-clone.png?classes=border)

Run the command `git clone https://github.com/[your-github-username]/py-demo-web-logs-continued` in your preferred directory.

## View existing branches

This repository has three existing branches:
- `master`
- `new-feature`
- `new-function`

![git-branch-a](pictures/git-branch-a.png?classes=border)

Run the command `git-branch-a` to view all existing local and remote branches.

## Test Existing Code

The `master` branch `main.py` file currently prints information to `STDOUT`. You can check this behavior by running the `main.py` file within your directory.

![python3-main-master](pictures/python3-main-master.png?classes=border)

Run the command `python3 main.py` within your `py-demo-logs-continued` directory.

## Branch: `new-feature`

Paul has come up with a solution to write the information inside of `main.py` to a file when run instead of only printing to `STDOUT`. 

![cat-main-new-feature](pictures/cat-main-new-feature.png?classes=border)

Checkout to the `new-feature` branch to test the behavior.

![git-checkout-new-feature](pictures/git-checkout-new-feature.png?classes=border)

- run the command `git checkout new-feature`
- run the command `python3 main.py`
- run the `ls` command to check that a file was written to your directory
- run the `cat` command to print the contents of web.log to Stdout
- lastly, remove the file as we no longer need it

## Branch `new-function`

John has also come up with a solution to write the information inside of `main.py` to a file but has created a function and called that function to handle the work. John also added in a newline character so that a newline is always triggered after the information has been displayed.

![cat-main-new-function](pictures/cat-main-new-function.png?classes=border)

Checkout to the `new-function` branch to test the behavior.

![git-checkout-new-function](pictures/git-checkout-new-function.png?classes=border)

- run the command `git checkout new-function`
- run the command `python3 main.py`
- run the `ls` command to check that a file was written to your directory
- run the `cat` command to print the contents of web.log to Stdout
- lastly, remove the file as we no longer need it

## Recap

- Reviewed existing code inside of `master`, `new-feature`, and `new-function` branches

Now that you are familiar with what code is inside of each branch you are going to need to merge all existing branches together.

Lets begin with the traditional `git merge` in the next walkthrough.