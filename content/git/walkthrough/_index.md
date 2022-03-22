---
title: "Walkthrough"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 2
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Basic git workflow review

### new remote existing local

- create local repo
- create remote repo
- link remote repo to local repo
- stage, and commit local changes
- push from local to remote

## Fork & Clone

### new local existing remote

- git fork *optional only necessary if you are forking from another user or organization*
- git clone
- explore local files
- make local changes
- stage, commit and push

## Branching

- Why you should do this

{{< mermaid >}}
gitGraph:
options
{
  "nodeSpacing: 75,
  "nodeRadius": 10
}
end
  commit
  branch newbranch
  checkout newbranch
  commit
  commit
  checkout master
  commit
  commit
  merge newbranch
{{< /mermaid >}}

### `git branch`

- example repo
  - broken app with a bug
  - new branch to fix bug
- example repo2
  - app that is being expanded
  - new branch for new feature
- after coding pushed up and 

## Merge Strategies

### `git merge`

### `git rebase`