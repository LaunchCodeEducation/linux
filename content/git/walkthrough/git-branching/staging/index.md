---
title: "Staging Changes"
date: 2022-07-03T15:20:12-06:00
draft: false
weight: 115
---

## Staging, Committing & Pushing

Now that you have made changes on a new branch this would be a great place to stage, commit and push the changes. You can then open a new pull request so the changes introduced in the `bug-fix` branch can be incorporated into the `master` branch.

![git-status](pictures/git-status.png?classes=border)

- `git status`: Check that there have been changes made
- `git add .` or `git add [file-name]`: Add the changes to staging
- `git commit -m "commit message"`: Commit the changes
- `git push origin bug-fix`: Push updated local branch to remote repo
- Submit a pull request and merge the `bug-fix` branch into the `master` branch.