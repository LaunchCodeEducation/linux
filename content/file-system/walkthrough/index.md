---
title: "Walkthrough"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Navigation Commands

### Review: Where am I?

To get your bearings and view your current working directory you can use the familiar `pwd` command.

![pwd](pictures/pwd.png)

{{% notice note %}}
The `pwd` command simply prints out the contents of the `$PWD` shell variable. Don't forget you can see the contents of any shell variables with the `echo` command!
{{% /notice %}}

### Review: What are the contents of this location?

To view the contents of the current working directory you can use the familiar `ls` command without any arguments.

![ls no arguments](pictures/ls-no-args.png)

### Change Current Working Directory

To change the current working directory you can use the `cd` *builtin* command. 

`cd` allows for one optional argument the new path to use as the current working directory. If no argument is provided it will set the current working directory to the `$HOME` shell variable.

`cd` works with both *absolute* and *relative* paths.

#### `cd` relative path

Starting from the home directory we could move into the `Documents/` directory with the following command:

`cd Documents`

![cd Documents](pictures/cd-documents.png)

Take note from the image that our terminal emulator always tells us the current working directory. You should see `~/Documents$` directly before the character where you can enter text commands. You can also see on the previous line before the `cd` command had been executed the text directly before our input area is only `~$`. 

#### `cd` absolute path

Our current working directory is `/home/student/Documents`. We can return to the home directory by using an absolute path:

`cd /home/student/`

![cd /home/student](pictures/cd-home-student.png)

And we're back to `$HOME`!

The main benefit in using an *absolute* path as the argument for the `cd` command is it will work from any location. The absolute path is an unique identifier for a directory.

#### Shell Shortcuts

Another useful tool for changing directories is to learn some of the Bash shell shortcuts.

- `~`: a shortcut for the `$HOME` variable
- `.`: a shortcut for the current working directory (`$PWD` variable)
- `..`: a shortcut for the parent of the current working directory

##### Shortcut Home

From a terminal change into the root directory:

`cd /`

![cd-root](pictures/cd-root.png)

From the root directory change into the home directory by using the home shortcut:

`cd ~`

![cd ~](pictures/cd-tilde.png)

{{% notice note %}}
The default argument for the `cd` command is the home directory. An even more efficient shortcut for changing into the home directory would be simply `cd` with no arguments. Try it out on your own, by changing into the root directory, and then entering `cd` without any arguments.
{{% /notice %}}

##### Shortcut to Parent

From your home directory let's change into the parent directory using the `..` shortcut:

`cd ..`

![cd ..](pictures/cd-dot-dot.png)

Using the parent directory shortcut we were able to move up one directory.

{{% notice bonus %}}
You can extend the parent and current directory shortcuts. Assuming you are in `/home/student/Documents` you can change into `/home/student/Desktop` with the command: `cd ../Desktop`.
![cd ../Desktop](pictures/cd-dot-dot-desktop.png)
Additionally, the parent and current directory shortcuts can be used with most bash commands.
{{% /notice %}}

## Creation Commands

CRUD stands for Create, Read, Update, Delete and it's the actions you can take on a record, object, file, directory, etc.

Let's learn how to **C**reate files and directories.

### Create Directory

### Create File

### Creating Hidden Files/Directories

## Reading Contents

Let's learn how to **R**ead files and directories.

You already know how to list the contents of a directory: `ls`.

You can list the contents of a file in a few different ways:

### Concatenate and display on STDOUT

`cat`

### Display and Parse Interactively

`less`

### Display contents in Text Editor

Open files in your text editor of choice, either in terminal (nano, vim, emacs) or in a GUI application (VisualStudioCode, IntelliJ, PyCharm, Atom).

## Deleting Files and Directories

Let's learn how to **D**elete files and directories.

`rm` command

### Delete Recursively

`rm -r`

#### Delete Recursively with Force!

`rm -rf`

{{% notice warning %}}
Linux will do what you tell it. If you tell it to delete a directory recursively with force it will not ask again. As long as you have permissions to edit a file it will be completely destroyed. Many horror stories exist around people accidently running `rm -rf` against their entire home directory and losing **all of their files**. Even worse targeting the root directory in which individuals have effectively **deleted their OS**...
{{% /notice %}}

## Update Files and Directories

You can either update the contents of a file/directory or the metadata (name, last modified, permissions) of a file/directory.

### Updating Metadata

#### Moving Files and Directories

Updating the absolute path of the given file.

`mv`

#### Moving to Rename Files and Directories

`mv`

#### Changing Additional Metadata

{{% notice bonus %}}
You can change a file's permissions with the `chmod` command. It will allow you to set a user (or groups) permissions to read, write and execute a specific file. In the Bash: Introduction - Demo the instructor added the execute permission to all users and groups. You can also change the owner of a file with the `chown` command.
{{% /notice %}}

### Updating File Contents

Open file using terminal text editor.

- `nano filename`
  - `vim filename`
  - `emacs filename`

{{% notice bonus %}}
`echo "newline" >> filename`
{{% /notice %}}


Open the file in your favorite text editor or IDE. Visual Studio Code, IntelliJ, Pycharm, Atom, etc.

### Using `nano`

#### Open File

#### Write File

#### Exit File

## Finding Files

## Bash Alias

## `.bashrc`

## `sudo`

<!-- 

- navigation commands
  - `pwd`
  - `ls`: read contents of directory
  - `cd` relative path
  - `cd` absolute path
  - shortcuts
    - `.` current directory
    - `..` parent directory
    - `~` current user's home directory
- creating commands
  - directory
    - `mkdir new-dir`
  - file
    - `touch new-file`
- hidden folders/files
  - `mdkir .hidden-folder`
    - `ls`
    - `ls -a` or `ls -A`
  - `touch .hidden-file`
    - `ls`
    - `ls -a` or `ls -A`
- reading contents of file
  - `cat some-file`: read contents of file
- finding files
  - `find location -name filename`
  - `find location -name '*.file'`
  - `find location -name '*README.md'`
  - `find location -regex '.*/*+README.md'`
- moving / editing filename
  - `mv`
    - move file to a new location
      - `mv ./examplefile ~/new-location/`
    - rename file in current location
      - `mv ./examplefile new-file-name`
    - move file to a new location and rename file
      - `mv ./examplefile ~/new-location/new-file-name`
    - move folder to a new location
      - `mv ./example-directory/ ~/new-location`
    - rename directory in current location
      - `mv ./example-directory/ new-directory-name`
    - move folder to a new location and rename file
      - `mv ./example-directory/ ~/new-location/new-directory-name`
- deleting files
  - `rm`
- deleting directories
  - `rmdir`: only deletes **empty** directories
    - `rm target-directory/*`: delete all files inside a directory
    - `rmdir target-directory`: delete now empty directory 
  - `rm -r target-directory`: delete directory **recursively**. An irreversible action that will delete whatever it is pointed at will check in with the user before removing any *write-protected* files.
  - `rm -rf target-directory`: delete directory **recursively** with **force**. An irreversible action that will delete whatever it is pointed at without checking in with the user before removing any *write-protected* files.
- editing contents of a file
  - `nano some-file`
  - Nano basics
    - directional pad navigation
    - great for making edits to existing files
    - `ctrl+o`: save file
    - `ctrl+x`: exit file
  - Vim/Emacs note
- alias
  - customizing our personal shells with custom commands
    - homecontents: `ls ~`
  - `.bashrc`
    - adding an alias `homecontents` to `.bashrc`
- `sudo`
  - students will need sudo to cat out some files, and look into some directories so they just need to know what the command means substitute user do and the default argument is the root user (who has the highest level of permissions)
  -->