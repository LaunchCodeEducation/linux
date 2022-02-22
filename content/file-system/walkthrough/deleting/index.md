---
title: "Deleting Files & Directories"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 4
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

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