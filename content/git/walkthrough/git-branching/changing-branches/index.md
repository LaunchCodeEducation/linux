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

## Changing Branches

Now that you have a new branch to work with you can switch or `checkout` the branch by using the `git checkout` command.

![git-checkout](pictures/git-checkout.png?classes=border)

Run the command `git checkout bug-fix`.

Once more check your current branch status with the `git branch` command.

## Running the Python Program

Run the `main.py` program within `py-demo-web-logs` to view the output:

![big-fix](pictures/bug-fix.png?classes=border)

You will notice that the current output has the following issues:
- `ip`: /home/student
- `home-dir`: 127.0.1.1

These two values should be swapped.

## Fix the Bug

Open up the main.py file with `nano` or `vim` and change the print statement to look like the following: 

`print("{}: {}@{} ip: {} home-dir: {}".format(ts, user, hostname, local_ip, home_dir))`

![big-fixed](pictures/bug-fixed.png?classes=border)

Write the changes and exit back to the terminal.

{{% notice warning %}}
Make sure to write/save your changes before exiting!
{{% /notice %}}

Now if you run the `main.py` program again you should see that the error has been fixed!

![python3-main](pictures/python3-main.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
If you would like to check that the changes you made are correct you can run the command `git checkout master` and then run the command `git checkout bug-fix-solution` to view the file it contains and compare it to the change you made on the `bug-fix` branch. 
{{% /notice %}}

## Recap:
- Changing branches with the `git checkout` command
  - Making minor changes to existing files