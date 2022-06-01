---
title: "User File Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 100
---

## System Users and Permissions

All files within a Linux system define permissions for owner, group, and others.

The available permissions for any given owner, group, and other users is as follows:
- `Read`
- `Write`
- `Execute`
- `None`

An owner, group, or other users can have any combination of the above permissions. 

The following list shows all possible options:

- `Read only`
- `Write only`
- `Execute only`
- `Read and Write`
- `Read and Execute`
- `Write and Execute`
- `Read, Write, and Execute`
- `None`

## Viewing Permissions in Terminal

Open up a terminal and navigate to the home directory if necessary.

View all the contents of the home directory with:

```bash
ls -l
```

For each non hidden file found by `ls -l` the following is displayed: 

- file type
- file permissions
- number of contained folders
- file owner
- file group
- file size (in bytes)
- file last touched date
- file name

Output:

![ls -l of home directory output](pictures/ls-l-desktop.png?classes=border)

The line with the `Desktop` directory can be broken down as follows:

- file type: `d` for directory
- file permissions: `rwxr-xr-x`
- number of contained files: `4`
- file owner: `student`
- file group: `student`
- file size (in bytes): `4096` bytes (`4` kilobytes)
- file last touched date: `Apr 20 10:00`
- file name: `Desktop`

The file permissions section defines read, write and execute permissions for each of the file owner, file group, and all other users.

`rwxr-xr-x` is broken into three:

- `rwx`: the file owner has **r**ead, **w**rite and e**x**ecute permissions
- `r-x`: the file group has **r**ead and e**x**ecute permissions
- `r-x`: all other users have **r**ead and e**x**ecute permissions

Bringing it together:

- `drwxr-xr-x 4 student student`: 
  - Directory that allows the `student` user to `Read, Write, and Execute`, the `student` group to `Execute and Read`, and all others to `Execute` only.

The line with the `snap` directory is as follows:
- `drwx------ 4 student student`:
  - Directory that allows the `student` owner to `Read, Write, and Execute`, the `student` group has `None` permissions, and all other users have `None` permissions.

## Alternate Users

Now that you have a basic understanding of the user and file permissions structure lets take a look at a different directory with alternate users.

Using the `ls -l` command view the file permissions for all files within the root directory:

```bash
ls -l /
```

Output:

![ls -l / output](pictures/ls-l-root.png?classes=border)


Take note that all folders and files located within the root directory belong to the `root` user and `root` group.

### `/usr/` File Permission Breakdown

```bash
drwxr-xr-x  21 root root        4096 Apr 20 10:20 tmp
```

`drwxr-xr-x`:

- `d`: file is of the directory type
- `rwx`: root owner has read, write and execute privileges
- `r-x`: root group has read and execute privileges
- `r-x`: all other users have read and execute privileges

### `/lost+found/` File Permission Breakdown

```bash
drwx------  2 root root        16384 Mar 11 14:32 lost+found
```

`drwx------`:

- `d`: file is of the directory type
- `rwx`: the root owner has read, write and execute privileges
- `---`: the root group has **no** permissions
- `---`: all other users have **no** permissions

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