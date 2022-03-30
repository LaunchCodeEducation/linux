---
title: "Best Practices"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 120
hidden: true
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-30"
---

### Branching Practices

When creating a new branch you always want to make sure your master branch is updated to the most recent version. One reason for this is to avoid any unecessary merge conflicts when you begin to merge any working branches into the master branch. That process will look something like the following:

![git-checkout-master](pictures/git-new-branch.png?classes=border)

- `git checkout master` (if not already on the master branch)
- `git pull`: Update master branch to most recent working version
- `git branch [new-branch-name]`: Create a new branch
- `git checkout [new-branch-name]`: Checkout or switch to newly created branch

{{% notice note %}}
When you "checkout" from master you are effectively creating a new branch with identical files and directories to the master branch. If you were to checkout from a different branch you would be working with code from that specific branch (which most likely wont have been merged with master yet). The command `git checkout -b new-branch-name` is also a shortened way of running the following commands: `git branch [new-branch]` >> `git checkout [new-branch]`
{{% /notice %}}