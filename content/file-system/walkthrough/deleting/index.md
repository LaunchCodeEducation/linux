---
title: "Deleting Files & Directories"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 115
---

## Deleting Files and Directories

Let's learn how to **D**elete files and directories.

### The `rm` command

You can remove files and directories with the remove (`rm`) command.

You simply provide the remove target as the argument for the `rm` command.

Let's create a new temporary file and then delete it with `rm`.

##### `touch temporary.file`

![touch temporary file](pictures/touch-temporary-file.png?classes=border)

After executing the `ls` command you can see that a new file named `temporary.file` was created from the `touch` command.

##### `rm temporary.file`

Let's get rid of that file with the `rm` command.

![rm temporary file](pictures/rm-temporary-file.png?classes=border)

And the file is gone!

{{% notice green "Bonus" "rocket" %}}
In an earlier walkthrough we created a file named `temp.file`. Feel free to remove that file as we won't be using it again!
![rm temp file](pictures/rm-temp-file.png?classes=border)
{{% /notice %}}

#### Delete Recursively

The `rm` command works on both files and directories. However the `rm` command can **only** delete an empty directory. Usually when we choose to delete a directory we want to delete all of the contents in the directory as well.

Luckily, there is a *recursive* option that will remove all of the items inside of directory before deleting the directory itself, it's the `-r` option. Let's try it out.

##### Create a directory: `mkdir temp-dir`

![mkdir temp-dir](pictures/mkdir-temp-dir.png?classes=border)

##### Add file to new directory: `touch temp-dir/temp.file`

![touch temp-file](pictures/touch-temp-file.png?classes=border)

##### Delete directory without recursive option: `rm temp-dir`

![rm temp-dir](pictures/rm-temp-dir.png?classes=border)

##### Delete directory recursively: `rm -r temp-dir/` 

![rm temp-dir recursively](pictures/rm-temp-dir-recursively.png?classes=border)

Since our user `student` has full permissions of the `temp-dir/temp.file` our Bash shell deleted the file without asking. In instances where the file is write-protected the Bash shell will ask for confirmation before deleting any files while using the `-r` option.

{{% notice green "Bonus" "rocket" %}}
The following image shows a read-only file. Notice the beginning of the second line: `-r--r--r--` indicating the file owner, group, and everyone else only has **read** access to the file. Write access and Execute access would be represented by the letter `w` and `x` respectively.
![ls -l temp-dir](pictures/ls-l-temp-dir.png?classes=border)
When we go to delete the directory recursively, the Bash shell will ask for permission before deleting this write protected file.
![rm -r temp-dir write protected](pictures/rm-r-temp-dir-write-protected.png?classes=border)
We will not cover modifying file permissions in this lesson. But you can read about the `chmod` command to get a sense of how the `temp.file` came to have only read access for all users.
{{% /notice %}}

{{% notice green "Bonus" "rocket" %}}
In an early section of this course we created a `temp` directory in our home directory. Feel free to delete it using your newfound `rm -r` skills!
{{% /notice %}}

#### Delete Recursively with Force!

In some instances there may be **many** write-protected files in a directory. It would be tedious to manually hit enter for each write protected file that needs to be deleted. There is another option called force `-f` that will delete the file(s) without checking the write protected status of the individual pieces.

We recommend throughout this course that you manually go through the process of approving the deletion of write protected files, except when instructed not to.

{{% notice warning %}}
Linux will do what you tell it. If you tell it to delete a directory recursively with force it will not ask again. Many horror stories exist around people accidentally running `rm -rf` against their entire home directory and losing **all of their files**. Even worse targeting the root directory which would effectively **delete the entire OS**...
{{% /notice %}}