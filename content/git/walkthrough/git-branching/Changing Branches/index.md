---
title: "Changing Branches"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 105
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-30"
---

{{% notice note %}}
This walkthrough will be using the `https://github.com/LaunchCodeTechnicalTraining/py-demo-web-logs` repository you cloned in the basic-git-workflow article.
{{% /notice %}}

## Changing Branches

Now that you have a new branch to work on you can switch or "checkout" to that branch with the `git checkout` command.

![git-checkout](pictures/git-checkout.png?classes=border)

Run the command `git checkout bug-fix`. Once more check your current branch status with the `git branch` command.

Now that you are on your newly created branch you can fix the existing bug and stage the changes for commit.

Within your `py-demo-web-logs` directory you can run the main.py program to view the output:

![big-fix](pictures/bug-fix.png?classes=border)

You will notice that the current output shows the directory `/home/student` as the `ip` and it shows `127.0.1.1` as the `home-dir`. Those two values should be swapped. 

Open up the main.py file with `nano` or `vim` and change the print statement to look like the following: 

![big-fixed](pictures/bug-fixed.png?classes=border)

`print("{}: {}@{} ip: {} home-dir: {}".format(ts, user, hostname, local_ip, home_dir))`

{{% notice warning %}}
Make sure to write your changes before exiting!
{{% /notice %}}

Now if you run the `main.py` program again you should see that the error has been fixed!

![python3-main](pictures/python3-main.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
If you would like to check that the changes you made are correct you can run the command `git checkout master` and then run the command `git checkout bug-fix-solution` to view the file it contains and compare it to the change you made on the `bug-fix` branch. 
{{% /notice %}}