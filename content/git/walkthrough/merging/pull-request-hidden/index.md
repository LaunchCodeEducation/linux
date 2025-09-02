---
title: "PR brief walkthrough"
date: 2022-07-03T15:20:12-06:00
draft: false
weight: 150
hidden: true
---

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