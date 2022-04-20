---
title: "User Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 100
---

## System Users and Permissions

All files and directories within a Linux system have assigned users, group members, and permissions.

The available permissions for any given user is as follows:
- `Read`
- `Write`
- `Execute`

A user or group can have any combination of the above permissions.
- `Read only`
- `Write only`
- `Execute only`
- `Read and Write`
- `Read and Execute`
- `Write and Execute`
- `Read, Write, and Execute`
- `None`

Open up a terminal and view users and permissions for the directories inside of the `home` directory.

![ls-l-desktop](pictures/ls-l-desktop.png?classes=border)

```bash
ls -l ~
```

The line with the `Desktop` directory can be broken down as follows:
- `drwxr-xr-x 4 student student`: 
  - Directory that allows the `student` user to `Read, Write, and Execute`, the `student` group to `Execute and Read`, and all other to `Execute` only.
The line with the `snap` directory is as follows:
- `drwx------ 4 student student`:
  - Directory that allow sthe `student` user to `Read, Write, and Execute`, the `student` group has `None` permissions, and all others also have `None` permissions.

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

<!-- `ls -l` /path

`ls -l` /path/file

examples

- `drwxrwxrwx`
- `rwxrwxrwx`

d or - (directory or file)

1. `rwx`: permissions for owner
2. `rwx`: permission for other users in the owner's user group
3. `rwx`: permissions for all other user

`r`: read
`w`: write
`x`: execute

So a file with:

- `-rw-r-----`: a standard file: owner can read and write; user group can read; all other user's have NO permissions
- `drw-rw-r--`: a directory: owner can read/write; user group can read/write; all other user's can read
- `rwxr-x---x`: a standard file: owner can read/write/execute; user group can read/execute; all other user's can execute

`chown` command

`chmod` command:

bit notatation:

- 7 `4(r) + 2(w) + 1(x)` rwx: read, write and execute
- 6 `4(r) + 2(w)` 	rw-: read and write
- 5 `4(r) + 1(x)` r-x:	read and execute
- 4 `4(r)` r--: read only
- 3 `2(w) + 1(x)` 	-wx: write and execute
- 2 `2(w)` 	-w-: write only
- 1 `1(x)` 	--x: execute only
- 0 `0` ---: none 


numerical file permissions -->