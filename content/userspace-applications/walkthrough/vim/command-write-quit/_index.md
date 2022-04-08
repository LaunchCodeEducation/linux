---
title: "Normal Mode Command: Writing and Quitting"
date: 2022-04-07
draft: false
weight: 105
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-07 # UPDATE ANY TIME CHANGES ARE MADE
---

## Writing and Quitting

From `vim` commands can be sent while in normal mode. This article will cover the write and quit commands.

## Write Command

To write a file type `:w`:

![vim :w picture](pictures/vim-w.png?classes=border)

{{% notice note %}}
While in command mode any typing will be displayed at the bottom of the terminal window. The above picture shows `:w`.
{{% /notice %}}

After typing `:w` simply hit enter to submit the command to `vim`:

![vim :w enter picture](pictures/vim-w-enter.png?classes=border)

The text at the bottom of the terminal window changed after submitting the write command it reads:

```bash
"temp-file.txt" [New] 0L, 0C written
```

This is a notification from `vim` the file was successfully written with so many lines and characters, in this case zero as no content has been added yet.

## Quit Command

To exit a file enter the `:q` command:

![vim :q picture](pictures/vim-q.png?classes=border)

After entering the terminal window will return back to the `bash` shell:

![vim :q enter picture](pictures/vim-q-enter.png?classes=border)

### Written File Validation

Check that the file was written by looking for the file name after executing the `ls` command:

![ls output](pictures/ls.png?classes=border)

## Combining Commands

In `vim` commands can be combined.

Write and quit can be combined by typing and entering `:wq`.