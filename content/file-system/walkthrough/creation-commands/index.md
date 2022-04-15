---
title: "Creation Commands"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 105
---

## Creation Commands

In your learning journey you have very likely heard the acronym **CRUD**. Which stands for:

- **C**reate
- **R**ead
- **U**pdate
- **D**elete

This is the collection of actions you can perform on any given record, object, or in the case of Linux: files/directories.

In the following sections we will be learning about, and practicing, some commands that can be used to perform **CRUD** actions on files and directories from our Bash shell.

### Create Directory

You can create a new directory with the `mkdir` command. Let's use it to create a new directory named `temp` in our home directory. With your current working directory as your home directory enter:

`mkdir temp`

![mkdir temp](pictures/mkdir-temp.png?classes=border)

When `mkdir` runs successfully there is no standard output (`STDOUT`) displayed to the user. To see the new directory you can run the `ls` command to see the contents that were created in the current working directory.

{{% notice note %}}
You can use absolute or relative paths with the `mkdir` command.
{{% /notice %}}

### Create File

You can create a new *empty* file with the `touch` command. In our home directory let's create a new file called `temp.file`.

`touch temp.file`

![touch temp.file](pictures/touch-temp-file.png?classes=border)

Again, a successful `touch` command will provide no message to standard output (`STDOUT`). To see the new `temp.file` you will need to run the `ls` command as shown in the picture.

### Creating Hidden Files/Directories

A hidden file or directory is denoted by the name starting with a period (`.`). We can create hidden files and directories using the exact command above, but adding the period (`.`) to the file name.

#### Hidden Directory

From your home directory create a new hidden-directory:

`mkdir .hidden-directory`

![mkdir .hidden-directory](pictures/mkdir-hidden-directory.png?classes=border)

To see this new hidden directory we will need to run the `ls` command with the the `-a` option so **all** files are displayed.

![ls -a](pictures/ls-hidden-directory.png?classes=border)

You may have to look for it, but you should find the new `.hidden-directory` that resulted from the execution of the `mkdir` command.

#### Hidden File

Let's change into the new `.hidden-directory`.

![cd .hidden-directory](pictures/cd-hidden-directory.png?classes=border)

Now create a new hidden file named `.hidden.file`.

`touch .hidden.file`

![touch .hidden.file](pictures/touch-hidden-file.png?classes=border)

To see the hidden file you will again need to run:

`ls -a`

![ls -a](pictures/ls-hidden-file.png?classes=border)