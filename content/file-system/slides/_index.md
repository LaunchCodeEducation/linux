---
title: "Slides"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 1
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-10 # UPDATE ANY TIME CHANGES ARE MADE
---

{{< slides >}}

## Bash: Filesystem 

---

## The Linux Filesystem (FS)

The file system is a part of the Linux kernel.

In Linux **everything is a file**. That is to say directories, files, links, and a few other Linux tools are all files and are a part of the file system.

Knowing the basics of the Linux FS hierarchy, Bash shell FS navigation commands, and how to perform actions on files is a fundamental aspect of using Linux.

---

## Filesystem Hierarchy

The Linux FS begins with the **root (`/`) directory**. This is the top level directory that contains all other directories and files that are a part of the operating system.

If you understand the general purpose of top level directories inside of the root directory, you will have a good idea where various files live.

---

## Required root Directories

According to the [Linux Documentation Project](https://tldp.org/) the Linux FS is required to have the following directories inside of the root directory.

- `/bin`, `/boot`, `/dev`
- `/etc`, `/lib`, `/media`
- `/mnt`, `/opt`, `/sbin`
- `/srv`, `/tmp`, `/usr`

In this class you are expected to know the purpose and use of the files in `/bin`, `/etc`, `/usr` and the often utilized `/home` directories.

---

## `/bin` Essential command binaries

Contains useful commands that are used by both the system administrator and non-privileged users.

Contains shells like `bash`. Contains commonly used shell commands like `cp`, `mv`, `rm`, `cat`, `ls`.

The tools found in `/bin` are separate from many of the other user tools as they are crucial for servicing the operating system if other areas become corrupted.

---

## `/etc` Host-specific system configuration

The container for **all** system related configuration files. These files are used to control the operation of all programs.

Example files `hostname` (name of computer), `timezone` (timezone of computer), `environment` (the contents that control the `$PATH` shell variable).

---

## `/usr` User binaries, documentation, libraries, header files, etc

The container for programs and files that are shared across all users of the computer.

Many of the applications we will learn about in this class are found in `/usr`.

Examples include `nano`, `python3`, `man`, and `which`.

---

## `/home` multi-user data and applications

Linux distributions are allowed to add additional directories to the root directory. Ubuntu, and some other Linux distros add `/home`.

`/home` is the location of all individual user data and applications.

Some Linux distributions create the `/home` directory within the `/usr` directory.

---

## Other Root Level Directories

Check the slides below for the top level description of the remaining TLDP top level directories.

We will not be covering the details of these directories, however you can learn more at the [Linux Filesystem Hierarchy from TLDP](https://tldp.org/LDP/Linux-Filesystem-Hierarchy/Linux-Filesystem-Hierarchy.pdf).

___

## `/boot`

Static files of the bootloader
___

## `/dev`

Device files
___

## `/lib`

Essential shared libraries and kernel modules
___

## `/media`

Mount point for removable media
___

## `/mnt`

Mount point for mounting a filesystem temporarily.

*Flash drive, or external hard drive, among others*
___

## `/opt`

Add-on application software packages

___

## `/sbin`

Essential system binaries

___

## `/srv`

Data for services provided by this system
___

## `/tmp`

Temporary files

---

## Bash File System Command Review

`pwd`: print working (current) directory

`ls`: list contents of current directory

These two commands will help you get your bearings as you move away from your home directory.

---


## Navigating the File System

Changing the working (current) directory is a common and useful action while in a Bash shell.

You can change the current directory with the `cd` shell builtin command.

It takes an optional argument in the form of the directory which is used to update the current working path.


---

### `cd` examples

- `cd /home/student/Documents`: absolute path
- `cd Documents`: relative path
- `cd .Documents`: relative path
- `cd ~`: the "`~`" key is a shortcut for `$HOME`
- `cd`: default argument is `$HOME`
- `cd ..`: change to parent directory

---

## Creating Directories

`mkdir [new-dir-name]`: make directory

`mkdir` works with both relative and absolute paths.

___

### `mkdir` examples

- `mkdir ~/new-dir`: creates a new directory in the home directory

- `mkdir new-dir`: creates a new directory in the current working directory

- `mkdir /home/student/Documents/new-dir`: creates a new directory using the absolute path provided

---

## Creating Empty Files

- `touch [filename]`: create a new empty file
- `nano [filename]`: open filename in nano editor. 

Upon writing the file it will be created at your current directory location.
<!-- TODO: Clarity: As a user i created a new file using touch and "filename" as the name of the file. I then opened the file using nano "filename". The note about writing the file will create it at the location is a bit confusing for me. I suggest we potentially give specific filenames on this portion of the walkthrough to avoid any confusion ie: touch example-file, nano example-nano -->
___

### `touch` actually updates timestamps

`touch` can be used to create new empty files, but it's main purpose is to update an existing file's timestamp.

You can try this out by creating a new file with `touch example-file` checking the last file modified date with `ls -l` and then waiting a few minutes and then running `touch example-file` again.

---

## Displaying the Contents of a File

Reading the contents of a file is always handy. In a terminal you can either take the entire contents and dump it into STDOUT with `cat`.

Or you can load the file into RAM pieces at a time with `less`.

___

### `cat` example

`cat /etc/hostname`: display the contents of `/etc/hostname` in the terminal window.

___

### `less` example

`less /etc/hostname`: open the contents of `/etc/hostname` in chunks in an interactive terminal window.

---

## Searching for Files

`find [location] -name file-name`

---

## Moving Files and Directories

`mv file new-location/`: will move file to `new-location/file`.

___

### Using `mv` to rename files/directories

You can use the `mv` command to rename files and directories in place, or change their name when moving to a new location.

- `mv file file2`: will rename `file` to `file2`
- `mv file Documents/file2`: will move and rename `file` to `Documents/file2`

---

## Deleting Files

`rm [file-name]`: relative or absolute

- `rm temp-file`
- `rm Documents/file2`
- `rm /home/student/Documents/file2`

---

## Deleting Directories

`rm` will also delete directories, but it must first delete any contents inside of the directory.

You can trigger this behavior with the `-r` option.

`rm -r Documents`: delete the Documents directory and all files/directories in the Documents directory.

You can stop it from asking about every document by adding the `--force` option. This can cause some nasty effects if used on the wrong directory.

---

## Editing the contents of a File using Nano

`nano` is a terminal text editing program.

`nano filename`: will open the existing filename or create a new file and open it for content.

___

### Saving file from Nano

- `ctrl`+`o`: write file

___

### Exiting Nano

- `ctrl` + `x`: exit file, will prompt for save if changes are detected

---

## Creating aliases

`alias whereami=pwd`

show `whoami` make a `whereami` alias

---

## `~/.bashrc`

file run for every new shell session initiated by user.

This where you can add things to permanently add them to your shell.

You can also add any shell customizations here.

___

### Adding whereami alias to `~/.bashrc`

`nano ~/.bashrc`

scroll to bottom of file

add:

```bash
# My aliases:
alias whereami=pwd
```

`source ~/.bashrc`

---

## `sudo`

Execute a command as another user.

Super (root) user is the default argument.

{{< /slides >}}

<!--
- navigating file-system
  - root
  - userspace
  - `cd`
    - `cd` no args
    - `cd ..`
- creating directories and files
  - `mkdir`
  - `touch`
  - hidden files and directories
- displaying contents of a file
  - `cat`
- searching for files
  - `find [location] [filename]`
  - bash wildcard (`*`)
- moving files & folders
  - `mv`
  - locations
  - renaming
- deleting files
  - `rm`
- deleting directories
  - `rm -r`
- editing the contents of a file with terminal based editors (nano) (show vim)
  - `nano`
  - `nano` save file: `ctrl` + `o`
  - `nano` exit file: `ctrl` + `x`
- creating new user-defined aliases
  - `alias` builtin
- `~/.bashrc`: code run when a new shell session initializes
  - adding `alias` to your `~/.bashrc`
  - reload a `~/.bashrc` with `source`
    - `.bash_profile`: code run when a login shell is created (so not run for each new shell session)
- `sudo`
  -->