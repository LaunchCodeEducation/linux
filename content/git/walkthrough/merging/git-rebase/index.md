---
title: "Git Rebase"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 110
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-30"
---

{{% notice note %}}
You will be using `https://github.com/[your-github-username]/py-demo-web-logs-rebase` as the github repository for this walkthrough.
{{% /notice %}}

## Merging with Git Rebase

Rebase is another way to merge branches. The `git rebase` command essentially takes committed changes to a branch and reiterates them on top of another branch.

## Repository Staged for Rebase

- Fork this repository: `https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-rebase` to your personal github account
- Clone the forked repo to your own machine: `git clone https://github.com/[your-github-username]/py-demo-web-logs-rebase`
- `cd` into the root folder of the project inside of your terminal

## Perform the Rebase

This project is currently staged for a `git rebase`. There has been a feature branch merged into the `master` branch already. In order to merge the remaining branch `new-function` into `master` we will need to resolve the merge conflicts within the `main.py` and `.gitignore` files.

iCheckout to the `new-function` branch and perform the `git rebase`:

![git-rebase-master-new-function](pictures/git-rebase-master-new-function.png?classes=border)

Run the following commands:
- `git checkout new-function`
- `gi You will receive a notification that there are merge conflicts in `main.py` and `.gitignore` and that the conflcits need to be resolved manually before continuingt rebase master`

## Merge Conflicts

You will notice some warnings that there are merge conflicts in the `main.py` and `.gitignore` files. 
- It asks you to resolve the conflicts manually and mark them as resolved with the `git add` or `git rm` command
- After the conflicts have been resolved you can then run `git rebase --continue`. 
- Lets resolve the conflicts so that you can continue the rebase.

## Resolve Conflicts
- Open up the `main.py` file with vim:

 ![vim-web-logs](pictures/vim-main-py.png?classes=border)

 run the command `vim main.py`

There should be a few things that come to your immediate attention:
- Section marked as `Head`
- Separating lines `=======`
- Section marked as `new feature`:

<!-- TODO: Write explanation of above sections -->

### What Changes to Keep?

Paul and John both made changes to the main.py file. We need to decide which ones we want to keep and which to throw away. 

The changes that we want to keep in this walkthrough include the following:
- function created from John's solution
- name of file used in Paul's solution (`web.log`)

![edited-vim-changes](pictures/edited-vim-changes.png?classes=border)

After making the required changes to the file it should look similar to the above image. Write the changes and exit vim.

{{% notice warning %}}
Make sure to write the changes to the file before exiting vim!
{{% /notice %}}

Now that the conflicts have been resolved inside of the `main.py` file you need to resolve the conflicts inside of the `.gitignore` file.

Open the `.gitignore` file with vim.

![vim-gitignore](pictures/vim-gitignore.png?classes=border)

Knowing that `web.log` is the name of the file preferred you can remove everything else from the `.gitignore` file so that there are no conflicts.

![fixed-gitignore](pictures/fixed-gitignore.png?classes=border)

Write the file and exit vim so that you are back inside of the `py-web-logs-continued` directory.

## Staging

Now that all conflicts have been resolved you will need to add the changes to staging so that you can continue the rebase onto `master`.

![git-status-rebase](pictures/git-status-rebase.png?classes=border)

Run the following commands:
- `git status`: check changes made
- `git add .`: add changes to staging

{{% notice green "Bonus" "rocket" %}}
If you run the command `git status` after adding the changes to staging you will notice that it says "all conflicts fixed: run "`git rebase --continue`".
![git-status-fixed](pictures/git-status-fixed.png?classes=border)
{{% /notice %}}

## `Git Rebase --Continue`

Since you have added the changes to staging you can now continue the `git rebase`.

![git-rebase-continue](pictures/git-rebase-continue.png?classes=border)

run the command `git rebase --continue`

## Pushing Local Changes to Remote Branch

You have completed a `git rebase`. If you run the command `git status` you will receive a notice that your branch and `origin/new-function` have diverged. This is because you rebased your local `new-function` branch onto the local `master` branch. 

![git-status-diverged](pictures/git-status-diverged.png?classes=border)

If you attempt to run the command `git push origin new-function` without force the push will be denied because the tip of your current branch is behind its remote counterpart.

<!-- TODO: notes on the above for further explanation -->

![git-push-force](pictures/git-push-force.png?classes=border)

Run the command `git push -f origin new-function`.

<!-- TODO: notes on the above line for further explanation -->

Now that the local changes have been pushed to the remote repository you should be able to merge the branch without conflict.

Open up the pull request from the `new-function` branch on your personal github account and merge the pull request!

{{% notice warning %}}
You may need to change the base repository and base branch reference!
{{% /notice %}}

- Click the `Create pull request` button.
- Click the `Merge pull request` button.
- Click the `Confirm merge` button.
- Click the `Delete branch` button.

You have successfully completed a `git rebase`!

## Recap:
- Checkout to branch needing to be merged
  - Rebase the branch onto master with `git rebase master`
  - Resolve merge conflicts
  - Add changes to staging
  - Continue rebase with `git rebase --continue`










