---
title: "Bash command: which"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 140
---

## `which` command

Most of the commands we have learned about in this class come standard as a part of the Ubuntu distribution we have been using. We will eventually learn about adding new commands and tools to our existing distribution. It is important to know the specific location of a command on your computer, something we can locate easily by using the `which` command.

The `which` command will give you the absolute path of the file that is being used to execute the instructions.

Let's find out where the `ls` command's binary lives.

Enter `which ls`.

![which ls](pictures/which-ls.png?classes=border)

According to the `which` command `ls` resides in `/usr/bin/ls`.

{{% notice note %}}
In Linux when you see something named `bin` it is almost always short for the word `binary`. A `binary` file is a file that **is not readable** to humans. Many `binary` files are executable programs. In fact, looking into the `/usr/bin` and `/bin` directories you may see the names of many executable programs that we have already used in this class!
{{% /notice %}}

### `which which`?

What about the `which` command? It is also an executable command so it should also have a location on our machine. How can we figure out where the `which` command resides?

![which which](pictures/which-which.png?classes=border)

It looks like the which command is also an executable binary located in `/usr/bin`.