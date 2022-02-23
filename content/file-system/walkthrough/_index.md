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

## Bash File System Commands

{{% children %}}

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