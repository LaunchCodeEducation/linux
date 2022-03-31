---
title: "Git Merge"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 105
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-17"
---

{{% notice note %}}
You will be using `https://github.com/[your-github-username]/py-demo-web-logs-continued` as the github repository for this walkthrough.
{{% /notice %}}

## Traditional Git Merge

Using the `git merge` command is the traditional way to merge development branches into your master branch of development. The main benefits of `git merge` is that you will keep the original history of the `master` branch in tact. The downside is that you will be working directly on the master branch and any mistakes or unwanted changes will cause problems.

- Fork the repository:`https://github.com/[your-github-username]/py-demo-web-logs-continued` to you your personal github account if you have not done so already.

- Clone the forked repository:`https://github.com/[your-github-username]/py-demo-web-logs-continued` onto your personal machine.

{{% notice note %}}
In the example below we are cloning the github repo into the `home/student/Desktop` directory.
{{% /notice %}}

![git-clone](pictures/git-clone.png?classes=border)

run the command `git clone https://github.com/[your-github-username]/py-demo-web-logs-continued` in your preferred directory.

## `git merge` command

Open up the `py-demo-web-logs-continued` project directory inside of your terminal. 

Check the existing branches:

![git-branch-a](pictures/git-branch-a.png?classes=border)

Run the command `git branch -a`





