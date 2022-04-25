---
title: "Changing File Ownership"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 110
---

## Name

> `chown` - change file owner and group 

## Usage

The `chown` command allows you to change the ownership on any given file which will directly affect what users are able to `read`, `write`, and `execute` the target file.

```bash
chown [OPTION] [OWNER][:[GROUP]] [file-name]
```

## Examples

Create a new file called `chown-example`.

```bash
touch chown-example
```

Check the current owner of the newly created file:

```bash
ls -l
```

Output:

![touch chown-example && ls -l output](pictures/chown-ownership.png?classes=border)

The current user `student` in the `student` group is the owner of the file `chown-example`.

### Change File Owner

Change the ownership of the file `chown-example` to the root user.

```bash
sudo chown root chown-example
```

Output:

![sudo chown root chown-example output && ls -l](pictures/root-chown.png?classes=border)

The new owner of the file `chown-example` has been changed to the root user. However the `chown-example` file still falls within the `student` group.

### Change File Group

To change the group of a file chown requires an additional argument:

```bash
sudo chown :root chown-example
```

Output:

![sudo chown :root chown-example && ls -l output](pictures/chown-group.png?classes=border)

You are able to add a `:` to the `chown` argument to change the group of a file.

{{% notice green "Bonus" "rocket" %}}
The `chown` command also allows you to change the user and group ownership with one command.
![student-group-chown](pictures/student-group-chown.png?classes=border)
```bash
sudo chown student:student chown-example
```
The first argument of the chown command (prior to the `:`) designates the file owner. The second argument designates the desired group.
{{% /notice %}}

## Recap:
- `chown` command
  - allows you to change user and group ownership of a file
  - `chown [OPTIONS] file-name`
  - `chown new-user file-name`: changes user ownership
  - `chown :new-group file-name`: changes group ownership
  - `chown new-user:new-group file-name`: changes both user and group ownership with one command