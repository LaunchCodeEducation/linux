---
title: "Bonus"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 4
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
---

## Bonus Exercise

In the previous [Bash: Introduction - Demo]({{< relref "/bash-introduction/demo" >}}) article the instructor presented a demo consisting of:

- Creating a new `bin` directory in the current user's home directory
- Creating a new bash file called `whattimeisit`
- Adding the *shebang* (`#!/bin/bash`) instructing the OS to run the file using the `bash` interpreter on the first line
- Adding three separate `echo` commands to the bash file
- Saving and exiting the file
- executing the bash file using the `bash` command
- adding executable permissions to the file
- executing the bash file by invoking the name both using a relative path and an absolute path

These are all steps you can now perform with your new found Bash: File System Navigation and File/Directory CRUD skills!

## Double Bonus

You can also complete the rest of the steps from the [Bash: Introduction - Demo]({{< relref "/bash-introduction/demo" >}}).

{{% notice note %}}
You are not expected to know about manually changing the `$PATH` shell variable, Symlinks, or how to use the `ln` command, but you can do your own research to learn about these concepts and commands. Being able to look up and use various commands is a very important skill to develop within the tech industry!
{{% /notice %}}

### General Steps

- add the `/home/student/bin` directory to the `$PATH` variable
- create a symlink named `when` that points at the `whattimeisit` bash script
- invoke both `when` and `whattimeisit` to show how they work

#### Double Bonus: Question

- What happens if you close your terminal and try to run `when` and `whattimeisit`?
{{% expand "ANSWER" %}} 
The `when` and `whattimeisit` commands **no longer work**! Check the path of this new Bash session with `echo $PATH`. You will notice the `/home/student/bin` is no longer on the Path variable.

When we manually added the `/home/student/bin` directory to our Path variable, we were only adding it for the current Bash session. There are many ways you can add this directory to the `$PATH` permanently. However, the best solution would be to add the line specifically to your `~/.bashrc` user profile. That way this specific directory of programs is only added for the **student** user.

You could simply add `export PATH="$PATH":/home/student/bin` to the bottom of your `~/.bashrc` file. Now every time a new Bash shell is opened by the **student** user the `/home/student/bin` is added to the global path that is initially set for all users.

Try it out by closing and opening a new terminal and then `echo $PATH`.
{{% /expand %}}