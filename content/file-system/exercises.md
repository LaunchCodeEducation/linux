---
title: "Exercises"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 3
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Exercises

### Create a Hidden folder called `notes` and a note file

- create a hidden **notes** directory in you home directory
- create a `file-system-navigation.notes` file in your new hidden notes directory
- edit the `file-system-navigation.notes` file with a brief description of what each of the following commands do:
  - `pwd`
  - `ls`
  - `cd`
  - absolute path vs relative path
  - `.`, `..` and `~` shortcuts
  - `mkdir`
  - `touch`
  - `mv` 

#### Questions

- What is the command to change working directories?
{{% expand "ANSWER" %}} 
`cd`
{{% /expand %}}
- What is an **absolute path**?
{{% expand "ANSWER" %}} 
An **absolute path** is the unique path for a specific file/directory. It always starts at root (`/`).
{{% /expand %}}
- What is a **relative path**?
{{% expand "ANSWER" %}} 
The path to a file/directory **relative** to the current working directory. This path always starts fromt he current working directory sometimes denoted as a `.` character.
{{% /expand %}}
- What is the `nano` program?
{{% expand "ANSWER" %}} 
`nano` is a command line text editor. It allows you to edit the text content of files directly from a terminal.
{{% /expand %}}
- How do you save a file in `nano`?
{{% expand "ANSWER" %}} 
One way to save a file in `nano` is to press `Ctrl` + `O` to **write out** the file.
{{% /expand %}}
- How do you exit a file in `nano`?
{{% expand "ANSWER" %}} 
You exit a file in `nano` by pressing `Ctrl` + `X` to **exit** the file. If changes have been made to the file `nano` will ask you if you want to write changes before exiting, or to discard changes before exiting.
{{% /expand %}}

### Create a new Bash Alias

- add a new bash alias called `allhomecontents` which shows all files (including hidden files) to your `~/.bashrc` profile
  - source the new file
  - run the new alias

#### Questions

- What is a Bash Alias?
{{% expand "ANSWER" %}} 
A Bash Alias is a command shortcut. It allows you to create a new command name that will run whatever command or collection of commands you want.
{{% /expand %}}
- When you invoke the `allhomecontents` alias what command is being run?
{{% expand "ANSWER" %}} 
`ls`
{{% /expand %}}
- For the previous answer did you include any options to be run with that command?
{{% expand "ANSWER" %}}
**Yes**. The `-a` option so all files, including hidden files, would be displayed. 
{{% /expand %}}

### Find the `hosts` files

- find **all** files containing the word `hosts` in the `/etc` directory
  - hint: you may need elevate permissions
  - hint: you may need to use wildcards (`*`)
  - bonus: only return files *checkout the man pages and look for the -type option*
- printout the terminal the contents of the `/etc/hosts`, which should be one of the files/directories you found in the last step
  - what do you think this file means?
  - hint: what is the relationship between `127.0.0.1` and the domain name `localhost`?

#### Questions

- What command, arguments, and options did you use to find all files containing the word `hosts` in the `/etc` directory?
{{% expand "ANSWER" %}}
`sudo find /etc --name *hosts*` 
{{% /expand %}}
- Why are the wildcards (`*`) necessary in the previous answer?
{{% expand "ANSWER" %}} 
Without the wildcards find searches for file names matching exactly `hosts` of which it finds a couple, but it doesn't find **all** files that contain the word `hosts`.
{{% /expand %}}

### Find the `passwd` file

- find the `passwd` file in the `/etc/` directory
  - find your username in this file
    - what does it say the home directory for that user is?

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

### Double Bonus

You can also complete the rest of the steps from the [Bash: Introduction - Demo]({{< relref "/bash-introduction/demo" >}}).

{{% notice note %}}
You are not expected to know about manually changing the `$PATH` shell variable, Symlinks, or how to use the `ln` command, but you can do your own research to learn about these concepts and command. Being able to look up and use various commands is a very important skill to develop within the tech industry!
{{% /notice %}}

#### General Steps

- add the `/home/student/bin` directory to the `$PATH` variable
- create a symlink named `when` that points at the `whattimeisit` bash script
- invoke both `when` and `whattimeisit` to show how they both work

##### Double Bonus: Question

- What happens if you close your terminal and try to run `when` and `whattimeisit`?
{{% expand "ANSWER" %}} 
The `when` and `whattimeisit` commands **no longer work**! Check the path of this new Bash session with `echo $PATH`. You will notice the `/home/student/bin` is no longer on the Path variable.

When we manually added the `/home/student/bin` directory to our Path variable, we were only adding it for the current Bash session. There are many ways you can add this directory to the `$PATH` permanently. However, the best solution would be to add the line specifically to your `~/.bashrc` user profile. That way this specific directory of programs is only added for the **student** user.

You could simply add `export PATH="$PATH":/home/student/bin` to the bottom of your `~/.bashrc` file. Now every time a new Bash shell is opened by the **student** user the `/home/student/bin` is added to the global path that is initially set for all users.

Try it out by closing and opening a new terminal and then `echo $PATH`.
{{% /expand %}}