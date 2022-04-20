---
title: "Changing File Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 105
---

## Name

> `chmod` command - change permissions of file or directory

## Usage

The chmod command allows you to change the permissions on any given file so that you can update the `read`, `write`, and `execute` status.

```bash
chmod [OPTIONS] file-name
```

## Chmod Numerical Expressions

When changing permissions of a file with the `chmod` command it would help to understand the numerical expressions for each type.
- `Read` (r) is represented by the number `4`.
- `Write` (w) is represented by the number `2`.
- `Execute` (x) is represented by the number `1`.

You can combine or add these numbers together to represent a combination of the permissions. If you wanted to provide a file with `Read` and `Write` permissions you would assign a `6` to the specific user or group.

See the table below for more explanation:

| Chmod | Description |
| :---: | :--- |
| 7 | 4(r) + 2(w) + 1(x) = 7 `rwx`: read, write and execute |
| 6 | 4(r) + 2(w) = 6 `rw` -: read and write |
| 5 | 4(r) + 1(x) = 5 `r-x`: read and execute |
| 4 | 4(r) `r` - -: read only |
| 3 | 2(w) + 1(x) = 3 `-wx`: write and execute |
| 2 | 2(w) `-w-`: write only|
| 1 | 1(x) `- -x`: execute only |
| 0 | 0 `- - -` : none |


## Example

Navitate to your desktop and create a new file called `chmod-example`

Check the permissions of the newly created file:

![check-permissions](pictures/check-permissions.png?classes=border)

```bash
ls -l
```

You will notice the file currently has the following permissions:
- `Read` and `Write` for the `student` user
- `Read` and `Write` for the `student` group
- `Read` only for all others

Pick your favorite editor and add the following code to the file:

```bash
#!/bin/bash

echo "Hello chmod example!"
```

Execute the file to view the output:

![bash-chmod-example](pictures/bash-chmod-example.png?classes=border)

```bash
bash chmod-example
```

## Changing Permissions

Now that you have created a new file and viewed the existing permissions it is time to use `chmod` command to change them.

Change the permissions of the `chmod-example` file so that all users only have read permissions:

![chmod-444](pictures/chmod-444.png?classes=border)

```bash
chmod 444 chmod-example
```

The above command can be broken down as follows:

chmod `4` - read only for student user `4` - read only for student group)`4` - read only for all other users