---
title: "Merging"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 110
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-17"
---

## Merge Strategies

In this walkthrough you will find two different merge strategies: `git merge` and `git rebase`. 

Both strategies have their own pros and cons.

The main benefit of `git merge` is that you keep the original history of the `master` branch in tact. However, conflicts are handled during the merge into the `master` branch.

The main benefit of the `git rebase` is that conflicts are handled in the feature branch and conflicts will not need to be managed when merging with the `master` branch. However, performing a `rebase` alters the history of the feature branch.

- `get merge` requires you to merge a branch directly into master. 
- `git rebase` allows you to rebase your development branch on top of master.

## Content Links

{{% children %}}

{{% notice note %}}
The walkthrough articles in this section will be using the [py-demo-web-logs-continued](https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs-continued) GitHub repository.
{{% /notice %}}