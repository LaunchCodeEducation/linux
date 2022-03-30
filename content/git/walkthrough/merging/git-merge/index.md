---
title: "Git Merge"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 105
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

## Git Merge

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

Open up your terminal and navigate to the `py-web-logs-continued` directory and update your master branch with the new remote changes.

![git-pull-origin-master](pictures/git-pull-origin-master.png?classes=border)

Run the following commands:
 - `git checkout master`: Ensure you are on the master branch
 - `git pull origin master`: update local master branch with remote changes


