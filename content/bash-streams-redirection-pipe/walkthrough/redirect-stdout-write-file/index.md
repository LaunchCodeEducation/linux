---
title: "Redirect STDOUT Write File"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 100
---

## `STDOUT` Redirection

By default `STDOUT` goes to the terminal window of the CLI.

`Bash` provides a collection of `STDOUT` redirection operators that give the user the ability to redirect `STDOUT` from the terminal window to a different location.

As a base example consider:

```bash
ls /home/student
```

The results of this command are placed in `STDOUT` and by default `STDOUT` is directed to the CLI terminal window like so:

![ls /home/student output](pictures/ls-stdout.png?classes=border)

This default behavior can be changed by using one of the `STDOUT` redirection operators.

## `STDOUT` Redirect Write to File

`STDOUT` can be redirected to a file with the `>` redirection operator.

The syntax for the `>` redirection operator would be `[bash command] > file.txt`.

Give it a try:

```bash
ls /home/student/ > home-contents.txt
```

Upon entering this command any `STDOUT` text will **not** display in the terminal window, but instead be written into the `home-contents.txt` file.

Output:

![ls /home/student/ > home-contents.txt output](pictures/ls-redirect-write.png?classes=border)

It comes as no surprise that no `STDOUT` message was printed to the terminal window. The contents of `STDOUT` should have been written to the file `home-contents.txt`.

Print the contents of the working directory and print the contents of the `home-contents.txt` file:

![ls && cat home-contents.txt output](pictures/cat-home-contents-txt.png?classes=border)

Using the `Bash` `STDOUT` redirection write operator a new file was created and it's contents are set to what was in `STDOUT`.

{{% notice warning %}}
The `Bash` `STDOUT` redirection write operator will **overwrite** any contents that exist in the file provided. For example the contents of `home-contents.txt` would be overwritten by rerunning the command, but changing the argument of the `ls` command:

```bash
ls /home/student/Desktop > home-contents.txt
```

Output:

![home-contents.txt overwritten output](pictures/home-contents-txt-overwritten.png?classes=border)

The contents of the file no longer contains the contents of the home directory, but instead of the Desktop directory inside of the home directory. Which in this case is empty!

{{% /notice %}}
