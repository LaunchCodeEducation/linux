---
title: "Staging Changes"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 115
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-30"
---

{{% notice note %}}
This walkthrough is a continuation of the `Changing Branches` walkthrough.
{{% /notice %}}

## Staging

Now that you have made changes on a new branch this would be a great place to stage your changes for a commit and submit a pull request.

![git-status](pictures/git-status.png?classes=border)

- `git status`: Check that there have been changes made
- `git add .` or `git add [file-name]`: Add the changes to staging
- `git commit -m "commit message"`: Commit the changes
- `git push origin bug-fix`: Push updated local branch to remote repo
- Submit a pull request and merge the `bug-fix` branch into the `master` branch.