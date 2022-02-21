---
title: "Slides"
date: 2021-11-09T15:12:13-06:00
draft: false
type: "slides"
weight: 1
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Bash: File System 

---

### Review

`pwd`: print working (current) directory

`ls`: list contents of current directory

These two commands will help you get your bearings as you move away from your home directory.

---

## Navigating the File System

Changing the working (current) directory is a common and useful action while in a Bash shell.

You can change the current directory with the `cd` shell builtin.

It takes an optional argument in the form of the directory to overwrite the current working directory.

___

### root

___

### userspace

---

### `cd` examples

- `cd /home/student/Documents`: absolute path
- `cd Documents`: relative path
- `cd .Documents`: relative path
- `cd ~`: `~` is a shortcut for `$HOME`
- `cd`: default argument is `$HOME`
- `cd ..`: change to parent directory

---

## Creating Directories

- `mkdir [new-dir-name]`: make directory
- relative
- absolute

---

## Creating Empty Files

- `touch [filename]`: create a new file
- `nano [filename]`: open filename in nano editor, upon writing file it will be created at location.

___

### `touch` actually updates timestamps

`touch` can be used to create new empty files, but it's main purpose is to update an existing file's timestamp.

You can try this out by creating a new file with `touch example-file` checking the last file modified date with `ls -l` and then waiting a few minutes and then running `touch example-file` again.

---

## Displaying the Contents of a File

Reading the contents of a file is always handy. In a terminal you can either take the entire contents and dump it into STDOUT with `cat`.

Or you can load pieces of the file into RAM at a time with `less`.

___

### `cat` example

___

### `less` example

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