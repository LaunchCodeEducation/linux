---
title: "New Project"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 100
---

For this exercise we want you to go through the process of:

1. creating a new local repo
1. creating a new remote repo
1. adding the remote repo to the local repo
1. adding files
1. going through the basic git workflow

## Creating a New Local Repo

From your home directory create a new directory called `hello-git`.

Initialize the `hello-git/` directory as a local `git` repository.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
mkdir hello-git
cd hello-git
git init
```
{{% /expand %}}

## Creating a New Remote Repo

Create a new remote repo on your personal GitHub account named `hello-git`.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
#### Create New Remote Repo Dropdown

![alt-text](pictures/github-new-repository-dropdown.png?classes=border)

#### Fill Out Form & Submit

![alt-text](pictures/fill-out-form.png?classes=border)

From here you must click `Create repository`.

{{% /expand %}}

## Adding Remote Repo to Local Repo

{{% expand "CLICK FOR ANSWER" %}}
#### Copy Remote Repo URI

![alt-text](pictures/copy-remote-uri.png?classes=border)

#### Add New Remote to Local Remote via Terminal

```bash
cd ~
cd hello-git
git remote add origin [copied-remote-URI]
```
{{% /expand %}}

## Adding Files to Local Directory

Add a file called `myname.txt` and add your name to the contents of the file.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd hello-git
echo "Paul Matthews" > myname.txt
```
{{% /expand %}}

## Basic Git Workflow

Add the file to staging, commit the staged changes, and push the commit to the remote repo.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd hello-git
git add myname.txt
git commit -m "added myname.txt" -m "Contents of file contains my name."
git push origin master
```

After you should be able to see the changes on your remote repo.

![alt-text](pictures/remote-synced.png?classes=border)
{{% /expand %}}