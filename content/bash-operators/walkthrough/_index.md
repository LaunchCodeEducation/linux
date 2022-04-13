---
title: "Walkthrough"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 2
---

## Walkthrough

Under normal circumstances every Linux distribution package has three streams opened when it starts. A stream for standard input, a stream for standard output, and a stream for errors & diagnostic information.

These streams are ubiquitously known as:
- `STDIN`: Standard Input
- `STDOUT`: Standard Output
- `STDERR`: Standard Error

{{% notice note %}}
By default the `STDOUT` & `STDERR` streams are displayed within the terminal window.
{{% /notice %}}

Understanding the three data streams is an important concept when working with Linux.

Almost every package expects input, performs operations on, or uses, the input, and will very likely provide output based on the actions that were performed. 

Additionally, when a package encounters unexpected behavior or exceptional conditions information about the failure is displayed to the error stream.

## `STDIN`

You have worked with `STDIN` already in this class without knowing it. 

Every Bash command argument is a form of `STDIN`.

### Arguments are `STDIN`

Consider the bash command `ls`:

```bash
ls /home/student
```

`ls` is the name of the command and **one argument is provided**. The argument `/home/student` is the string representation of the directory that the `ls` command should operate on.

A package argument is a form of `STDIN`.

{{% notice note %}}
`ls` requires an argument because the source code needs to know which directory's contents should be displayed to `STDOUT`. `ls` is configured to use the current working directory when an argument is not provided as the **default value** of the argument.
{{% /notice %}}

{{% notice green "Bonus" "rocket" %}}
Many bash commands and packages are configured in a way to accept multiple arguments. Try:
```bash
ls /home/student /home/student/Desktop
```
How does adding a second argument affect `STDOUT`?
{{% /notice %}}

## `STDOUT`

By default `STDOUT` is displayed to the terminal window.

### Terminal Display is `STDOUT`

Consider the bash command `ls`:

```bash
ls /home/student
```

Output:

![ls /home/student output](pictures/ls-stdout.png?classes=border)

The command `ls` was performed on the `/home/student` argument and the results were displayed to `STDOUT`. The string `Desktop Documents Downloads Music...` is a representation of the contents found inside of the provided directory.

## `STDERR`

By default `STDERR` is displayed to the terminal window.

### Terminal Display is `STDERR`

Consider running the `cat` command on a file that does not exist:

```bash
cat a-file-that-does-not-exist.txt
```

Output:

![cat a-file-that-does-not-exist.txt output](pictures/cat-nonexistant-file.png?classes=border)

The file `a-file-that-does-not-exist.txt` does not exist. When provided as an argument to the `cat` command `cat` is unable to locate the provided file and prints out an error message: `No such file or directory`.

This error message is not what we expected as the user of the `cat` command. We expected the contents of the file to be displayed in `STDOUT`, but since an error occurred when the `cat` command was running it instead streamed the message to `STDERR`, which by default is the terminal window of the CLI shell. 


## Recap

There are three data streams:

- `STDIN`: input provided to CLI commands
- `STDOUT`: standard output provided to the user as a result of CLI commands
- `STDERR`: standard error output provided to the user as an error result of a CLI command

The following articles explore `bash operators` that provide ways to work with the three data streams discussed in this article.

## Content

{{% children %}}