---
title: "Slides"
date: 2022-04-14T16:13:40-05:00
draft: false
# type: "slides"
weight: 1
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## File Permissions

---

## Linux File Permissions

All files have permissions for different types of classifications

The classifications are Owners, Groups, and Others
___

### Available Permissions

Read, Write, Execute, None

Read: User, Group, and Other can Read the file
Write: User, Group, and Other can Write to the file
Execute: User, Group, and Other can execute the file
None: None of the above permissions

___

## Possible Permission Combinations

Read only
Write Only
Execute only
Read and Write
Read and Execute
Write and Execute
Read, Write, and Execute
None
___

### View Permissions

You can use the -l option with the ls command for a long listing format of files within a given directory

You can expand even further and provide the -a option in addition to -l for all files (including hidden)

---

## Changing File Permissions

The chmod command allows you to change file permissions for a file or directory

chmod [OPTION] [file-name]

Read is represented by the numeric value 4

Write is represented by the numeric value 2

Execute is represented by the numeric value 1

None is represented by the numberic value 0

___

### chmod Command Example

chmod 444 example-file-name

The above command would provide the Owner, Group, and all Other users with access to the "example-file-name" file with Read only permissions
___

### Providing Multiple Permissions

You are able to use the numeric values in addition to one another to provide multiple permissions for any given Owner, Group, and Other users

Read + Execute = 5

Read + Write = 6

Read + Write + Execute = 7

---

## Changing File Ownership

The chown command allows you to change file ownership for a file or directory

chown [OPTION] [OWNER][:[GROUP]] [file-name]

___

### Change User Ownership

chown new-user example-file

The above command would change the ownership of the example-file from its current owner to "new-user"

___

### Change Group Ownership

chown :new-group example-file

The above command would change the ownership of the example-file from its current group to "new-group"

___

### Change User and Group Ownership

chown new-user:new-group example-file

The above command would change the ownership of the example-file from its current owner to "new-user" and group to "new-group"

{{< /slides >}}