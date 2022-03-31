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
You will be using `https://github.com/[your-github-username]/py-demo-web-logs-continued` as the github repository for this walkthrough.
{{% /notice %}}

## Merging with Git Rebase

Lets start by merging the `new-feature` branch into the `master` branch. Navigate to the `py-demo-web-logs-continued` repository within your personal github account.

### Create a Pull Request

![pull-request](pictures/pull-request.png?classes=border)

Click the `3 branches` section.

Open a pull request for the `new-feature` branch.

![pull-request-new-feature](pictures/pull-request-new-feature.png?classes=border)

Click the `New pull request` for the `new-feature` branch.

{{% notice note %}}
You will notice that is says "There isn't anything to compare.". You need to change the base repository option to your personal github repo.
{{% /notice %}}

![pull-request-dropdown](pictures/pull-request-dropdown.png?classes=border)

Click `[your-github-username]/py-demo-web-logs-continued`

{{% notice note %}}
You will also need to select a different base reference. 
{{% /notice %}}

![base-reference](pictures/base-reference.png?classes=border)

Select `master` as the base branch reference.

Lastly we will be able to create a pull request:

![create-pull-request-button](pictures/create-pull-request-button.png?classes=border)

Click the `Create pull request` button.

### Merge pull request

Since the `new-feature` branch did not have any conflicts with the `master` branch we can merge it automatically.

![merge-pull-request](pictures/merge-pull-request.png?classes=border)

Click the `Merge pull request` button.

### Confirm the merge

![click-confirm-merge](pictures/click-confirm-merge.png?classes=border)

Click `Confirm merge`

### Delete Merged Branch

Now that the `new-feature` branch has been merged into the `master` branch it can be safely deleted. 

{{% notice green "Bonus" "rocket" %}}
Deleting the branch on the remote repository will only delete the remote branch. You will still have access to this branch locally.
{{% /notice %}}

![delete-branch](pictures/delete-branch.png?classes=border)

Click the `Delete branch` button.

### Merge the `new-function` Branch into Master

Now it is time to merge the `new-function` branch into master. Since you just merged the `new-feature` branch into master there will be merge conflicts because both branches were working on the **same file**

### Create Another Pull Request

Similar to the steps above, create another pull request for the `new-function` branch. The steps will be as follows:
- Navigate to your branches view
- Click the `New pull request` button for the `new-function` branch
- Change the base repository option to `[your-github-username]/py-demo-web-logs-continued`
- Change the base branch reference to `master`
- Click the `Create pull request` button.

### Merge Conflicts

You will notice that there is a warning saying "This branch has conflicts that must be resolved". It asks you to use the web editor or the command line to resolve the conflicts. This walkthrough is going to utilize the `command line` to resolve the conflicts.

![merge-conflicts](pictures/merge-conflicts.png?classes=border)

{{% notice note %}}
Github shows you what files have conflicts:
- `.gitignore`
- `main.py`
{{% /notice %}}

You will need to resolve these conflicts within your terminal so that you are able to merge the `new-function` branch into `master`.

Open up your terminal and navigate to the `py-web-logs-continued` directory and update your master branch with the new remote changes.

![git-pull-origin-master](pictures/git-pull-origin-master.png?classes=border)

Run the following commands:
 - `git checkout master`: Ensure you are on the master branch
 - `git pull origin master`: update local master branch with remote changes

 ### Fixing Conflicts with Git Rebase

 Checkout to the `new-function` branch and use the `git rebase` command to rebase `new-function` on top of master.

 ![git-rebase-master](pictures/git-rebase-master.png?classes=border)

 Run the following commands:
 - `git checkout new-function`
 - `git rebase master`

 You will receive a notification that there are merge conflicts in `main.py` and `.gitignore` and that the conflcits need to be resolved manually before continuing.

 Lets fix the conflicts using vim.

 ![vim-web-logs](pictures/vim-web-logs.png?classes=border)

- Open up the `main.py` file with vim:
    - `vim main.py`

There should be a few things that come to your immediate attention:
- Section marked as `Head`
- Separating lines `=======`
- Section marked as `master`

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

Now that all conflicts have been resolved you will need to add the changes to staging so that you can continue the rebase onto `master`.

![git-status-rebase](pictures/git-status-rebase.png?classes=border)

Run the following commands:
- `git status`: check changes made
- `git add .`: add changes to staging

If you run the command `git status` after adding the changes to staging you will notice that it says "all conflicts fixed: run "`git rebase --continue`".

{{% notice note %}}
It's always a good idea to run `git status` to make sure things are as they should be.
{{% /notice %}}

![git-status-fixed](pictures/git-status-fixed.png?classes=border)

Run the command `git status`.

### Git Rebase --Continue

Since you have added the changes to staging you can now continue the `git rebase`.

![git-rebase-continue](pictures/git-rebase-continue.png?classes=border)

run the command `git rebase --continue`

### Pushing Local Changes to Remote Branch

You have completed a `git rebase`. If you run the command `git status` you will receive a notice that your branch and `origin/new-function` have diverged. This is because you rebased your local `new-function` branch onto the local `master` branch. 

![git-status-diverged](pictures/git-status-diverged.png?classes=border)

If you attempt to run the command `git push origin new-function` without force the push will be denied since the branches have diverged.

![git-push-force](pictures/git-push-force.png?classes=border)

Run the command `git push -f origin new-function`.

Now that the local changes have pushed to the remote repository you should be able to merge the pull request created for the `new-function` branch.

Open up the pull request on your personal github account and merge the pull request!

![no-merge-conflicts](pictures/no-merge-conflicts.png?classes=border)

- Click the `Merge pull request` button.
- Click the `Confirm merge` button.
- Click the `Delete branch` button.

You have successfully completed a `git rebase`!

## Recap:
- Create a pull request
  - Merge pull request without conflicts
- Create pull request that has unresolved conflicts
  - 









