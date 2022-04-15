---
title: "Exercises: Solution"
date: 2021-11-09T15:12:13-06:00
draft: true
weight: 120
---

## Exercise Solution

### Create a Hidden folder called `notes` and a note file

```bash
mkdir ~/.notes
nano ~/.notes/file-system-navigation.notes
```

Student will have to add text to the file, and then write and exit the file in nano.

### Create a new Bash Alias

```bash
nano ~/.bashrc
```

Students will then have to add:
```bash
alias allhomecontents="ls -a ~"
```

### Find the `hosts` files

```bash
sudo find /etc -name *hosts*
```

Without wildcards students will only find 2 files, instead 5 files.

### Print out the contents of the `/etc/hosts` file

```bash
cat /etc/hosts
```

### Find the `passwd` file

```bash
sudo find /etc -name *passwd*
```

### Find the `student` username in this file

```bash
cat /etc/passwd
```

```bash
cat /etc/passwd | grep student
```

The home dir for `student` is `/home/student` their default shell is `/bin/bash`.