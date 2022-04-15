---
title: "Normal Mode Command: Writing and Quitting"
date: 2022-04-07
draft: false
weight: 105
---

## Writing and Quitting

{{% notice note %}}
When entering commands like `:w` and `:q` into vim through normal mode you are technically in `Command Line Mode`. The only way to access `Command Line Mode` is through `Normal` mode which is what allows you to enter commands via the `Command Line`.
{{% /notice %}}

`vim` commands can be sent while in normal mode. This article will cover the `write` and `quit` commands.

## Write Command

To write a file type `:w`:

![vim :w picture](pictures/vim-w.png?classes=border)

{{% notice note %}}
While in command mode any typing will be displayed at the bottom of the terminal window. The above picture shows `:w`.
{{% /notice %}}

After typing `:w` simply hit enter to submit the command to `vim`:

![vim :w enter picture](pictures/vim-w-enter.png?classes=border)

The text at the bottom of the terminal window changed after submitting the `write` command.

It reads:

```bash
"temp-file.txt" [New] 0L, 0C written
```

This is a notification from `vim` saying the file was successfully written with so many lines and characters, in this case zero as no content has been added yet.

## Quit Command

To exit a file enter the `:q` command:

![vim :q picture](pictures/vim-q.png?classes=border)

After executing the command your terminal window will return back to the `bash` shell:

![vim :q enter picture](pictures/vim-q-enter.png?classes=border)

### Written File Validation

Check that the file was written by looking for the file name after executing the `ls` command:

![ls output](pictures/ls.png?classes=border)

## Combining Commands

{{% notice green "Bonus" "rocket" %}}
In `vim` commands can be combined.

The `write` and `quit` commands can be combined by typing and entering `:wq`.
{{% /notice %}}