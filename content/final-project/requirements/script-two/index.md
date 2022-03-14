---
title: "Poll SCM & Redeployment Script"
date: 2022-03-10T15:47:05-06:00
draft: false
weight: 2
originalAuthor: ""
originalAuthorGitHub: ""
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: "2022-03-10"
---

## Steps

- change to project repo
- pull project repo
- if changes are detected:
  - build artifacts
  - move artifacts to unit file location
  - restart service
  - email that changes were detected and project was successfully re-deployed
- if no changes are detected:
  - write to a log file with:
    - timestamp
    - the local project path was checked
    - the remote repo that was checked