---
title: "Walkthrough"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
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