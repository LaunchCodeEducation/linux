---
title: "Git Merge"
date: 2022-07-03T15:20:12-06:00
draft: false
weight: 105
---

## Traditional Git Merge

{{% notice note %}}
You will be using [py-demo-web-logs-continued](https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-continued) as the github repository for this walkthrough.
{{% /notice %}}

Using the `git merge` command is the traditional way to merge development branches into your master branch of development. 

The main benefits of `git merge` is that you will keep the original history of the `master` branch in tact. The downside is that you will be working directly on the master branch and any mistakes or unwanted changes will cause problems.

- Fork the repository:`https://github.com/[your-github-username]/py-demo-web-logs-continued` to you your personal github account if you have not done so already.

- Clone the forked repository:`https://github.com/[your-github-username]/py-demo-web-logs-continued` onto your personal machine.

{{% notice note %}}
In the example below we are cloning the github repo into the `home/student/Desktop` directory.
{{% /notice %}}

![git-clone](pictures/git-clone.png?classes=border)

Run the command: `git clone https://github.com/[your-github-username]/py-demo-web-logs-continued` in the directory you cloned your repository.

## `git merge`

The `git merge` joins two or more development histories together. When you perform a merge you are **merging the target branch into the currently checked out branch**. 

The command to merge the target-branch into the currently checked out branch would be: 

`git merge [target-branch]`.

## Merge `new-feature` Branch into `master`

Open up the `py-demo-web-logs-continued` project directory inside of your terminal. 

Check the existing branches:

![git-branch-a](pictures/git-branch-a.png?classes=border)

Run the command `git branch -a`

You are going to merge the `new-feature` branch and the `new-function` branch into master.

### Actual Merge

Lets start with by merging `new-feature` branch into the `master branch`:

{{% notice warning %}}
Make sure the currently checked out branch is `master` before running the next command.
{{% /notice %}}

![git-merge-origin-new-feature](pictures/git-merge-origin-new-feature.png?classes=border)

While on the `master` branch run the command: `git merge origin/new-feature`

{{% notice green "Bonus" "rocket" %}}
Notice that the above example uses the remote name `origin` when merging. The remote branches had not yet existed on the local machine when I ran this command. If you already had checked out these remote branches you could have left off the remote name `origin` and simply run: `git merge new-feature`.
{{% /notice %}}

The merge was successful! Remember to update your remote master branch:

![git-push-master-new-feature](pictures/git-push-master-new-feature.png?classes=border)

Run the command `git push origin master`.

## Merge `new-function` Branch

Now that you have merged the `new-feature` branch into master its time to merge the `new-function` branch. Since both of these branches made edits to the same files you are going to have a **merge conflict**.

![git-merge-origin-new-function](pictures/git-merge-origin-new-function.png?classes=border)

Run the command `git merge origin/new-function`.

{{% notice note %}}
Remember that if you already have the `new-function` branch existing locally you can leave off the remote name origin and run the command `git merge new-function`!
{{% /notice %}}

Now would be a great time for you to run a `git status` command to see what is going on:

![git-status-git-merge](pictures/git-status-git-merge.png?classes=border)

### What Changes to Keep?

Paul and John both made changes to the `main.py` file. We need to decide which ones to keep and which to throw away. 

The changes that we want to keep in this walkthrough include the following:
- function created from John's solution
- name of file used in Paul's solution (`web.log`)

### Resolve conflicts in `main.py`

Open up the `main.py` file with `vim` (or `nano` or the file editor of your choice) so that you can make the necessary changes and fix the conflicts inside of the file:

![vim-main-py](pictures/vim-main-py.png?classes=border)

Make the below changes:

![edited-vim-changes](pictures/edited-vim-changes.png?classes=border)

After making the required changes to the file it should look similar to the above image. Write the changes and exit vim.

{{% notice warning %}}
Make sure to write the changes to the file before exiting vim!
{{% /notice %}}

Now that the conflicts have been resolved inside of the `main.py` file you need to resolve the conflicts inside of the `.gitignore` file.

### Resolve Conflicts in `.gitignore`

Open the `.gitignore` file with vim.

![vim-gitignore-new-function](pictures/vim-gitignore-new-function.png?classes=border)

Knowing that `web.log` is the name of the file preferred you can remove everything else from the `.gitignore` file so that there are no conflicts.

![fixed-gitignore](pictures/fixed-gitignore.png?classes=border)

Write the file and exit vim so that you are back inside of the `py-web-logs-continued` directory.

### Staging, Committing and Pushing Conflict Resolution

Now that all conflicts have been resolved you will need to add the changes to staging so that you can continue the merge.

Add the files to staging and commit changes:

![git-commit-merge](pictures/git-commit-merge.png?classes=border)

Run the following commands:
- `git add .`: Add changes to staging
- `git status`: Check status
- `git commit -m "your commit message`: Commit changes to complete merge
- `git push origin master`: Push changes to remote repo

{{% notice green "Bonus" "rocket" %}}
Both the `new-feature` branch and the `new-function` branch can now be deleted safely!
{{% /notice %}}

## Recap:
- Traditional `git merge` command: Merge development branches into master branch using the `git merge` command
  - Merged the `new-feature` branch into `master` without conflict
  - Merged `new-function` branch into `master` while resolving conflicts
Staging:
  - Pushed updated files into remote master branch



