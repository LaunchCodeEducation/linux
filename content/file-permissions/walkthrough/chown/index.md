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

## Examples

Create a new file called `chown-example`.

Check the current ownership of the newly created file:

![chown-ownership](pictures/chown-ownership.png?classes=border)

```bash
ls -l
```

The current user `student` in the `student` group is the owner of the file `chown-example`.

### Change User Ownership

Change the ownership of the file `chown-example` to the root user.

![root-chown](pictures/root-chown.png?classes=border)

```bash
sudo chown root chown-example
```

The new ownership of the file `chown-example` has been changed to the root user. However the `chown-example` file still falls within the `student` group.

### Change Group Ownership

To change the group of a file chown requires an additional option:

![chown-group](pictures/chown-group.png?classes=border)

```bash
sudo chown :root chown-example
```

You are able to add a `:` to the `chown` options to specify a change in group.

{{% notice green "Bonus" "rocket" %}}
the `chown` command also allows you to change the user and group ownership with one command.
![student-group-chown](pictures/student-group-chown.png?classes=border)
```bash
sudo chown student:student chown-example
```
The first argument of the chown command (prior to the `:`) designates what user you would like to change ownership to. The second argument designates the desired group to change ownership to.
{{% /notice %}}

## Recap:
- `chown` command
  - allows you to change user and group ownership of a file
  - `chown [OPTIONS] target-file`
  - `chown new-user target-file`: changes user ownership
  - `chown :new-group`: changes group ownership
  - `chown new-user:new-group`: changes both user and group ownership with one command