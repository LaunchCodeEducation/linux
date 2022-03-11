---
title: "Poll SCM & Redeployment Script"
date: 2022-03-10T15:47:05-06:00
draft: false
weight: 1
originalAuthor: ""
originalAuthorGitHub: ""
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: "2022-03-10"
---

## Example

Pictures of the output of using the script in all states:

- success: changes detected & successfully redeployed
- failure: changes detected & NOT successfully redeployed
- success: no changes detected log updated

## Validation

After running the script the pictures of proof of validation including:

- script exists
  - `ls /path/to/script`
- script logs
  - `cat /path/to/log/location`
- change made to project
  - picture of browser reflecting change after change made to project master branch