---
title: "Working with Branches"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 3
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-17"
---

{{% notice note %}}
We will be using the repository you cloned in the previous walkthrough for the instructions below.
{{% /notice %}}

## Branching

Branches allow users to work on projects under version control in a safe and controllable way. Rather than changing folders and files on your `master` branch where you have a working project, branching allows you to add new features and bug fixes on a branch to then later merge them with your master branch. This ensures that you do not break or add unitended bugs directly to your master or main branch of development.

In the steps below you will do the following:
- Review best branching practices
- Create a new branch
- Fix an existing bug
- Stage changes
- Push changes to remote repository

### Good Branching Practices

When creating a new branch you always want to make sure your master branch is updated to the most recent version. One reason for this is to avoid any unecessary merge conflicts when you begin to merge any working branches into the master branch. That process will look something like the following:

![git-checkout-master](pictures/git-new-branch.png?classes=border)

- `git checkout master` (if not already on the master branch)
- `git pull`: Update master branch to most recent working version
- `git branch [new-branch-name]`: Create a new branch
- `git checkout [new-branch-name]`: Checkout or switch to newly created branch

{{% notice note %}}
When you "checkout" from master you are effectively creating a new branch with identical files and directories to the master branch. If you were to checkout from a different branch you would be working with code from that specific branch (which most likely wont have been merged with master yet). The command `git checkout -b new-branch-name` is also a shortened way of running the following commands: `git branch [new-branch]` >> `git checkout [new-branch]`
{{% /notice %}}

### Creating a new Branch

While inside of a git project directory you can create a new branch with the `git branch` command.

Navigate your terminal to the `py-demo-web-logs` project you cloned in the previous walkthrough. 

![git-branch-command](pictures/git-branch-command.png?classes=border)

Run the command `git branch`. This will show you the current branch you are working on in addition to any other local branches you have.

{{% notice green "Bonus" "rocket" %}}
If you would like to view all local branches in addition to any remote branches you can add the -a tag at the end of your command: `git branch -a`. Try it out!
![git-branch-a](pictures/git-branch-a.png?classes=border)
You will notice that there is a remote branch `big-fix-solution` that has been created previously on this project.
{{% /notice %}}

The main.py program within this project currently contains a bug. You are going to create a new branch to fix the bug and stage that change for commit.

![git-new-branch](pictures/git-new-branch.png?classes=border)

Run the command `git branch bug-fix`. Check that the branch has been created using the `git branch` command.

### Changing Branches

Now that you have a new branch to work on you can switch or "checkout" to that branch with the `git checkout` command.

![git-checkout](pictures/git-checkout.png?classes=border)

Run the command `git checkout bug-fix`. Once more check your current branch status with the `git branch` command.

Now that you are on your newly created branch you can fix the existing bug and stage the changes for commit.

Within your `py-demo-web-logs` directory you can run the main.py program to view the output:

![big-fix](pictures/bug-fix.png?classes=border)

You will notice that the current output shows the directory `/home/student` as the `ip` and it shows `127.0.1.1` as the `home-dir`. Those two values should be swapped. 

Open up the main.py file with `nano` or `vim` and change the print statement to look like the following: 

![big-fixed](pictures/bug-fixed.png?classes=border)

`print("{}: {}@{} ip: {} home-dir: {}".format(ts, user, hostname, local_ip, home_dir))`

{{% notice warning %}}
Make sure to write your changes before exiting!
{{% /notice %}}

Now if you run the `main.py` program again you should see that the error has been fixed!

![python3-main](pictures/python3-main.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
If you would like to check that the changes you made are correct you can run the command `git checkout master` and then run the command `git checkout bug-fix-solution` to compare your file.
{{% /notice %}}

### Staging

This would be a great place to stage your changes for a commit. Run the `git status` command to view the changes made.

![git-status](pictures/git-status.png?classes=border)

{{% notice note %}}
It is best practice to always create a new branch when adding content to a project.
{{% /notice %}}


### Recap

- example repo
  - broken app with a bug
  - new branch to fix bug
- example repo2
  - app that is being expanded
  - new branch for new feature
- after coding pushed up and 

