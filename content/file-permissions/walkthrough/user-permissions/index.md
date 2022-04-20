---
title: "User File Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 100
---

## System Users and Permissions

All files and directories within a Linux system have assigned users, groups, and permissions.

The available permissions for any given user, group, and others is as follows:
- `Read`
- `Write`
- `Execute`
- `None`

A user or group can have any combination of the above permissions:
- `Read only`
- `Write only`
- `Execute only`
- `Read and Write`
- `Read and Execute`
- `Write and Execute`
- `Read, Write, and Execute`
- `None`

Open up a terminal and view users and permissions for the directories inside of the `home` directory.

Each line reads as follows:

`Permissions | User | Group`

![ls-l-desktop](pictures/ls-l-desktop.png?classes=border)

```bash
ls -l ~
```

The line with the `Desktop` directory can be broken down as follows:
- `drwxr-xr-x 4 student student`: 
  - Directory that allows the `student` user to `Read, Write, and Execute`, the `student` group to `Execute and Read`, and all others to `Execute` only.

The line with the `snap` directory is as follows:
- `drwx------ 4 student student`:
  - Directory that allows the `student` user to `Read, Write, and Execute`, the `student` group has `None` permissions, and all others also have `None` permissions.

## Alternate Users

Now that you have a basic understanding of the user and file permissions structure lets take a look at a different directory with alternate users.

View the users and directories for all files within the root directory:

![ls-l-root](pictures/ls-l-root.png?classes=border)

```bash
ls -l /
```

You can see that all folders and files located within the root directory belong to the `root` user and `root` group.

{{% notice green "Bonus" "rocket" %}}
You may also notice that some of the lines begin with an `l`. The first character on the line will always provide what type of file it is. In this particular example the `l` signifies a symbolic link. The other types of files you may see are as follows:
- `-`: regular file
- `d`: directory
- `c`: character device file
- `b`: block device file
- `s`: socket file
- `l`: symbolic link

You are not expected to fully understand any of the special file types in this course.
{{% /notice %}}