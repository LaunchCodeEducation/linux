---
title: "Bash Shell Variables"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 7
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Bash Shell Variables

The Bash shell has numerous variables that contain useful information. They are indicated by the following pattern: `$VARIABLE_NAME`.

We won't look at all of the Bash Shell Variables, but we would like you to know about four of them:

- `$BASH`
- `$HOME`
- `$PATH`
- `$BASHPID`

To view the contents of any Bash Shell variable you can simply use the variable as the argument with the `echo` command.

### `echo $BASH`

![echo $BASH](pictures/echo-bash-variable.png)

The `$BASH` shell variable contains the absolute path to the shell this session is using. 

### `echo $HOME`

![echo $HOME](pictures/echo-home-variable.png)

The `$HOME` shell variable contains the absolute path to the home directory of the user that initiated the Bash shell.

### `echo $PATH`

![echo $PATH](pictures/echo-path-variable.png)

The `$PATH` shell variable contains a collection of all of the tools currently accessible to this current Bash Shell session.

Any files and subdirectories found within the listed directories are available to be invoked by name.

{{% notice green "Bonus" "rocket" %}}
If you have ever tried to run a program before and received a message about the command not being found in the path, this is what it was referring to. When installing new programming languages, build tools, or really any software that needs to be used from a shell the location of the tool *must* be added to the path variable. Lots of software installations take care of adding the tool to your path by either editing the PATH variable or by simply adding the binary of the software directly to one of the directories listed in your path.
{{% /notice %}}

### `echo $BASHPID`

![echo $BASHPID](pictures/echo-bashpid-variable.png)

The `$BASHPID` shell variable contains the process ID of the current Bash Shell. This number will likely be different for everyone. In fact if you open your current terminal and open a new one and then check the `$BASHPID` shell variable you should notice that it is different.

Every running program has at least one process running and therefore a process ID. Many programs will create multiple processes and each of their children processes will have unique IDs, however the program's initial main process is the parent of all other associated process IDs.

{{% notice note %}}
We will not be learning about processes in this class. Taking the time to learn about processes will make you a better Linux user, but goes deeper than we need to know in this class.
{{% /notice %}}