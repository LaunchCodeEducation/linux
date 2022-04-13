---
title: "Pipe Operator"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 115
weight: 110
---

## Convert `STDOUT` into `STDIN` of Following Command

The Bash pipe operator `|` provides the abililty to take the `STDOUT` from the first command and use it as the `STDIN` for the next command.

The pipe operator is a **powerful** tool in Bash that allows us to create specific and sometimes complex commands.

The pipe operator syntax will look similar to: `[bash-command-one] | [bash-command-two]`.

Whatever contents added to `STDOUT` from `[bash-command-one]` will be used as the `STDIN` for `[bash-command-two]`.

## Pipe `STDOUT` from `ls -a` to `less`

```bash
ls -a | less
```

Upon executing the preceding command the `STDOUT` from `ls -a` will be used as the `STDIN` for the `less` command. This will open up the `less` view window in the terminal.

Output:

![ls -a | less output](pictures/ls-a-pipe-less.png?classes=border)

The picture displays a `less` window. The contents can be navigated using the `less` tools, and can be ultimately exited with a press of the `q` key.

{{% notice note %}}
The output you see may be slightly different than the output from the picture. Many of the hidden files and directories in the picture will eventually find their way onto your machine as your continue through this course.
{{% /notice %}}

## Pipe `history` to `less`

Viewing the `history` of your bash terminal is useful, but can be overwhelming:

```bash
history
```

Output:

![history output](pictures/history.png?classes=border)

The `STDOUT` of the `history` command defaulted to the terminal window. It would be much easier to view the contents in a `less` window. This can be achieved by piping `STDOUT` of `history` to the `STDIN` of `less`:

```bash
history | less
```

Output:

![history | less output](pictures/history-less.png?classes=border)
    
{{% notice note %}}
Your history will be different than the above picture. You can exit the `less` window by pressing the `q` key.
{{% /notice %}}

## Pipe `history` to `grep`

`grep` is a searching tool that we will learn about in a future article, but is a great example of how the `bash` pipe operator can be used.

In this case the `STDOUT` of `history` needs to be filtered to only include `ls` commands. This can be achieved by executing `history` and piping the `STDOUT` to the `grep` command with an argument searching for only `ls` commands:

```bash
history | grep 'ls'
```

Output:

![history | grep 'ls' output](pictures/history-grep-ls.png?classes=border)

## Pipelines

In `bash` you can chain together multiple commands with the pipe operator to create specific and sometimes complex commands.

Suppose we wanted to open the `STDOUT` from `history | grep 'ls'` in `less` we can add another pipe:

```bash
history | grep 'ls' | less
```

Output:

![history | grep 'ls' | less output](pictures/history-grep-ls-less.png?classes=border)

The `STDOUT` contents of `history | grep 'ls'` have now been passed as the `STDIN` to the `less` command.

You can chain as many pipes together as you need creating complex, but simple to understand, pipelines.