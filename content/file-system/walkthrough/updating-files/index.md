---
title: "Updating Files & Directories"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 5
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

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