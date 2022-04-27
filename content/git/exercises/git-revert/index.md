---
title: "Bonus: Git Revert"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 105
---

This is a bonus exercise. We didn't cover `git revert`, however it's a powerful tool.

## Git `revert`

> git-revert - Revert some existing commits

Git `revert` will allow us to undo a commit.

Say for example you accidentally deleted some important directories in your local repository, you then committed the changes, and pushed them to your remote repository.

Now both your local and remote repositories are missing the files in the directories you deleted!

If only we could go back in time and undo the commit that deleted the directories.

We can with `git revert`.

## Example Repo

Look at the history of the [example repo](https://github.com/LaunchCodeTechnicalTraining/revert-example) to see this illustrated.

Commits 2 and 3 introduced two new directories with very important stuff.

Commit 4 removed the directories accidentally.

Let's walk through the steps to revert commit 4.

## Fork Example Repo

First fork the remote repo controlled by LaunchCodeTechnicalTraining to your own personal account.

{{% expand "CLICK FOR ANSWER" %}}
![alt-text](pictures/fork-hover.png?classes=border)

![alt-text](pictures/create-fork.png?classes=border)

![alt-text](pictures/forked-repo.png?classes=border)
{{% /expand %}}

## Clone Example Repo

Clone your remote repository.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
git clone [your-remote-repo]
```

My remote repo was `https://github.com/pdmxdd/revert-example`. Yours should be similar, but have your username in place of `pdmxdd`.
{{% /expand %}}

## Revert Commit 4

### View Commit Log

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd revert-example
git log
```
![alt-text](pictures/git-log.png?classes=border)

The offending commit id is: `e92bf70cc84ed20b5e9583865753f5cc06c34b87`.
{{% /expand %}}

### Revert Commit

Now using the commit id revert the commit. This will create a new commit that reverts the commit in question.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd revert-example
git revert e92bf70cc84ed20b5e9583865753f5cc06c34b87
```
Save the default commit message that comes up and exit.
{{% /expand %}}

### Check Log for New Commit

The revert should have created a brand new commit that reverts the previous commit. The log should reflect this.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd revert-example
git log
```
![alt-text](pictures/git-log-after-revert.png?classes=border)
{{% /expand %}}

### Check Project Directory for Missing Directories

Check the contents of the `revert-example` directory to see that the new directories exist again.

{{% expand "CLICK FOR ANSWER" %}}
```bash
cd ~
cd revert-example
ls
```
{{% /expand %}}

## Push

Although we have reverted the commits on our local repo. We need to push them to update our remote repo.

{{% expand "CLICK FOR ANSWER" %}}
```bash
git push origin master
```
{{% /expand %}}