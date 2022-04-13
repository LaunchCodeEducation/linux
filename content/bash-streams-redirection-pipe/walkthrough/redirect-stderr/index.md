---
title: "Bonus: Redirect STDERR"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 110
---

## Standard Error

Output stream used to display error messages. 

## Example

- broken bash command with a redirect into `error.log` file

## Redirect `STDERR`

By default any error messages in `STDERR` are sent to the terminal window of the CLI shell.

```bash
cat non-existent-file.txt
```

Output:

```bash
cat: non-existent-file.txt: No such file or directory
```

## Redirect `STDERR` Write

`STDERR` can be redirected and written, or appended to a file similar to `STDOUT`, by using the write file `2>` and append file `2>>` redirection operators. 

```bash
cat non-existent-file.txt 2> cat-error.log
```

Output:

![cat non-existent-file.txt 2> cat-error.log && ls && cat cat-error.log output](pictures/cat-error-log.png?classes=border)

## Redirect `STDERR` Append

```bash
cat different-file.txt 2>> cat-error.log
```

Output:

![cat different-file.txt 2>> cat-error.log && cat cat-error.log](pictures/cat-error-log-appended.png?classes=border)

{{% notice note %}}
You are not expected to know how to redirect `STDERR` in this course.
{{% /notice %}}
