---
title: "Git Merge"
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

{{% notice note %}}
This walkthrough will be using the `https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-continued` github repository.
{{% /notice %}}

## Merge Strategies

In this walkthrough you will find two different merge strategies. `git merge` and `git rebase`. The main benefits of `git merge` is that you will keep the original history of the `master` branch in tact. `git rebase` will alter the history but you are able to perform the rebase on a alternate branch. 
- `get merge` requires you to merge a branch directly into master. 
- `git rebase` allows you to rebase your development branch on top of master.

### `git merge`

Lets begin with the `git merge` command and strategy to combine two branches.

- Fork the `https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-continued` repository to you your personal github account.

- Clone the forked `https://github.com/[your-github-username]/py-demo-web-logs-continued` repository onto your personal machine.

{{% notice note %}}
In the example below we are cloning the github repo into the `home/student/Desktop` directory.
{{% /notice %}}

![git-clone](pictures/git-clone.png?classes=border)

run the command `git clone https://github.com/[your-github-username]/py-demo-web-logs-continued` in your preferred directory.

### View existing branches

This repository has three existing branches:
- `master`
- `new-feature`
- `new-function`

![git-branch-a](pictures/git-branch-a.png?classes=border)

Run the command `git-branch-a` to view all existing local and remote branches.

### Test Existing Code

The `master` branch main.py file currently prints information to Stdout. You can check this behavior by running the main.py file within your directory.

![python3-main-master](pictures/python3-main-master.png?classes=border)

Run the command `python3 main.py` within your `py-demo-logs-continued` directory.

### new-feature branch

Paul has come up with a solution to write the information inside of main.py to a file when run instead of only printing to Stdout. Checkout to the `new-feature` branch to test the behavior.

![git-checkout-new-feature](pictures/git-checkout-new-feature.png?classes=border)

- run the command `git checkout new-feature`
- run the command `python3 main.py`
- run the `ls` command to check that a file was written to your directory
- run the `cat` command to print the contents of web.log to Stdout
- lastly, remove the file as we no longer need it

<!-- Lets start by merging the `new-feature` branch into the `master` branch. Create a pull request on your personal github repository from the `new-feature` branch.

![pull-request](pictures/pull-request.png?classes=border)

![git-merge-new-feature](pictures/git-merge-new-feature.png?classes=border) -->