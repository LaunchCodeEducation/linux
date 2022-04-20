---
title: "Changing File Ownership"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 110
---

## Name

> `chown` command - change the user and/or group ownership of any given file

## Usage

The `chown` command allows you to change the ownership on any given file which will directly affect what users are able to `read`, `write`, and `execute` the target file.

```bash
chown [OPTIONS] file-name
```

## Example

Create a new file called `chown-example`.

Check the current ownership of the newly created file:

![chown-ownership](pictures/chown-ownership.png?classes=border)

```bash
ls -l
```

The current user `student` in the `student` group is the owner of the file `chown-example`

Change the ownership of the file `chown-example` to the root user.

![root-chown](pictures/root-chown.png?classes=border)

```bash
sudo chown root chown-example
```

The new ownership of the file `chown-example` has been changed to the root user. However the `chown-example` file still falls within the `student` group.

