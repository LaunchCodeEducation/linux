---
title: "Bonus: Redirect STDIN"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 115
---

## Redirect `STDIN`

So far you have given `bash` commands input in two ways:

1. as command arguments
1. via converting `STDOUT` from a preceding command into `STDIN` using the pipe operator

These are the two ways you should expect to work with `STDIN` in this course.

However, there are additional ways you can provide input to `bash` commands.

## `STDIN` Redirection from Here String

```bash
cat <<< "hello"
```

`cat` is concatenating the contents of the here string "hello".

{{% notice note %}}
This is identical to `echo "hello"`. This example shows how a here string can be passed to a command as `STDIN`.
{{% /notice %}}

## `STDIN` Redirection from File

```bash
cat < hello-from-bash.txt
```

{{% notice note %}}
The `hello-from-bash.txt` file was created in the Redirect STDOUT Append File article.
{{% /notice %}}

`cat` is concatenating the contents of the file `hello-from-bash.txt`

{{% notice note %}}
This is identical to `cat hello-from-bash.txt`. This is example shows how a file can be passed to a command as `STDIN`.
{{% /notice %}}

You will not be expected to know here strings, or `STDIN` redirection from files in this course.