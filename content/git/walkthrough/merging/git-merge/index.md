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

You are going to merge the `new-feature` branch and the `new-function` branch into master.

## Merge `new-feature` Branch

Lets start with by merging `new-feature` branch into the `master branch`:

![git-merge-origin-new-feature](pictures/git-merge-origin-new-feature.png?classes=border)

While on the `master` branch run the command: `git merge origin/new-feature`

{{% notice green "Bonus" "rocket" %}}
Notice that the above example uses the remote name `origin` when merging. The remote branches had not yet existed on the local machine when I ran this command. If you already had checked out these remote branches you could have left off the remote name `origin` and simply ran the command `git merge new-feature`.
{{% /notice %}}

The merge was successful! Remember to update your remote master branch:

![git-push-master-new-feature](pictures/git-push-master-new-feature.png?classes=border)

run the command `git push origin master`

## Merge `new-function` Branch

Now that you have merged the `new-feature` branch into master its time to merge the `new-function` branch. Since both of these branches made edits to the same files you are going to run into conflicts.

![git-merge-origin-new-function](pictures/git-merge-origin-new-function.png?classes=border)

run the command `git merge origin/new-function`

{{% notice note %}}
Remember that if you already have the `new-function` branch existing locally you can leave off the remote name origin and run the command `git merge new-function`!
{{% /notice %}}

Now would be a great time for you to run a `git status` command to see what is going on:

![git-status-git-merge](pictures/git-status-git-merge.png?classes=border)


