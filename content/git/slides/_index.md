---
title: "Slides"
date: 2021-11-09T15:20:12-06:00
draft: false
hidden: false
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Git

---

## Git Review

Version Control Software created by Linux Torvalds

Similar to the Linux Kernel (also created by Torvalds) it is open source software
___

## Basic Workflow

Adding changes to staging

Committing changes to local git repo

Pushing changes from local repo to remote

___

### Creating a Local Repo

git init (within project directory) will initialize a git repository in your current directory

This allows you to begin controlling "versions" of your project

---

## Branches

Branches allow you to diverge from your master or main branch of development

You are able to create a new branch in multiple ways:

git branch new-branch-name

git checkout -b new-branch-name

---

## Merging

This course will cover two different types of merging strategies

Traditional merge with git merge

merging with git rebase

___

### Traditional Merge

Using the traditional merge strategy allows you to keep the original history of commits in-tact

It also means that you will be working directly on your main or master branch of development

___

### Git Rebase

git rebase will reapply commits from your current branch on top of the target branch

You are working with a feature branch and conflits are handled prior to merging directly into your main or master branch of development

A rebase does alter the history of the feature branch

{{< /slides >}}