---
title: "Walkthrough"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 2
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Walkthrough

**Bash** is *the* GNU Project's shell. A **shell** is an interface between a user and the kernel. Bash is a **text-based** shell. By learning aspects of the Bash shell you are learning a *powerful mechanism* for interfacing with a computer.

### Terminal Emulator

To use this text-based Bash shell on our Ubuntu machines we will need to open a **terminal emulator** application. The terminal emulator is the graphical software that provides many features including: 
- a window
- a window exit button
- minimize and maximize window buttons

The terminal emulator is also configured to:
- handle key-press events
- handle click events
- receive Bash commands 
- display Bash Standard Output (STDOUT)

The **terminal emulator** we will be using in this class is simply called **terminal**. You can find it by clicking the *Activities* button in the top left corner of your Ubuntu screen.

![Ubuntu Activities Search](pictures/ubuntu-activities-search.png)

Then search for the program `terminal`.

![Ubuntu Activities Search: terminal](pictures/ubuntu-activities-search-terminal.png)

Either hit enter, or click the `terminal` application and a new `terminal emulator` will be launched!

![Ubuntu Terminal Emulator](pictures/ubuntu-terminal-emulator.png)

### Bash Command Basics

This Bash shell is expecting text based commands. However, we must follow the rules for inputting the commands.

All Bash commands follow this basic pattern: `command-name --option(s) argument(s)`.

Most commands have at least one argument, however they can have no arguments, provide default arguments, or sometimes allow for multiple arguments.

Bash command options are similar with regards to Bash command arguments. You won't always need an option, however they provide you with options for changing how the command will be executed, or how the output will be displayed. You may use no options, one options, or many options.

### `pwd` command

Let's try out our first command: `pwd`. `pwd` is one of the Bash commands that takes **no arguments**. 

Simply type `pwd` into your terminal and hit enter.

{{% notice note %}}
Make sure you only type `pwd` into your terminal before hitting enter. Since the Bash shell is expecting text it requires the text you enter to exactly match it's expectations.
{{% /notice %}}

![pwd output](pictures/pwd.png)

`pwd` stands for print working directory. You will notice the output of the command is simply the text `/home/student`. Which is the current working directory of our Bash shell session.

While in a Bash shell session you will be regularly changing directories. Being able to quickly determine your current working directory is *highly* beneficial.

### `clear` command

Our next command also takes no arguments. `clear` will clear the terminal emulator of all text.

Enter `clear` into your terminal.

![clear before execution](pictures/clear-before-execution.png)

Then submit the command with enter.

![clear output](pictures/clear.png)

All that text is gone! We now have a clean slate to continue working.

{{% notice note %}}
Most future images will `clear` the screen before running new commands.
{{% /notice %}}


### `ls` command

Our next command will list out the contents of either our current working directory or a specific directory: `ls`.

`ls` will use your current working directory as a default argument if you do not provide an argument. So to list out the contents of your current working directory you simply need to enter `ls` and nothing else before submitting the command. Give it a try!

![current working directory contents](pictures/ls.png)

Our home directory `/home/student` has quite a few things in it. All of the entires just happen to be directories:
- Desktop
- Documents
- Downloads
- Music
- Pictures
- Public
- snap
- Templates
- Videos

That's a pretty standard collection of user folders. These happen to be the default folders created when a new user is created in Ubuntu.

#### `ls` with argument

We can provide an argument to the `ls` command, which must be a valid directory, and our Bash shell will list all the contents in that argument!

Let's try looking at all the contents inside of the root directory `/`.

Enter `ls /`.

![root directory contents](pictures/ls-root.png)

The **root** directory is the container for all files/directories on this computer! It is the root of our Ubuntu distribution. The root directory contains the `/home` directories of all users, all the tools shared across the machine, and all of the files/directories necessary for the operating system to function.

Let's take a look in the `bin` directory inside of the root directory.

Enter `ls /bin`.

![/bin contents](pictures/ls-bin.png)

Woah. That's a lot of files! The `/bin` directory is a location of many of the **binaries** used on this operating system. If you scroll through the list you may see some familiar names like `zip` or `python3`. `zip` is used to create and open zipped folders. `python3` is the Python3 interpreter that can run python files.

If you continued to search through this list you will also find the three commands we have already learned (`pwd`, `clear`, `ls`). All three of these programs are simply binaries that the Bash shell is executing for us. Many of the programs we will use in this class are located in this directory!

{{% notice warning %}}
**Do not create, change or delete any files above your home directory** `/home/student/`, unless this book instructs you to. The files found directly above the user home directories are necessary for the operating system to work properly. Most Linux distributions will allow you direct access to these files.
{{% /notice %}}

### `ls` Empty Directory

Let's take a look at the contents inside our current user's `Documents` directory.

Enter `ls Documents`.

![/home/student/Documents](pictures/ls-documents.png)

Nothing came up. This isn't a bug, this is the output we would expect if there are no contents to be listed.

{{% notice bonus %}}
Try listing the contents of the remaining directories inside of `/home/student/`. Do any of them have contents?
{{% /notice %}}

### `ls` Options

`ls` has many options for you to choose from, however the two most common options are:
- `--long`: show the permissions, size and date last modified among other meta-data
- `--all`: show all files and directories including hidden

#### `-l`

Enter `ls -l` to see the long form output for the current directory.

![ls -l current directory](pictures/ls-l-working-directory.png)

Most of the information isn't relevant to us yet, but it's still important to know how to access it.

#### `-a`

Enter `ls -a` to see all the files and folders including any that may be hidden for the current directory.

![ls -a current directory](pictures/ls-a-working-directory.png)

Here we can see a few hidden files, and directories. All of the hidden files and folders start with a period `.`. 

{{% notice note %}}
Your `ls -a` output may look slightly different from the provided image. Many hidden files and folders are created in the home directory to keep track of shell histories, shell profiles, and various configurations. As you continue to use this operating system your home directory will fill up with some of these files and directories. 
{{% /notice %}}

### `echo`

The next command `echo` simply prints out a message to the Bash shell's Standard Output (STDOUT). An echo statement is very similar to the `print()` method in Python3, or the `console.log()` method in JavaScript, or the `System.out.println()` method in Java.

To use the `echo command` we simply need to invoke the command with one argument that results in a string.

Enter `echo "Hello world"`.

![echo "hello world"](pictures/echo-hello-world.png)

{{% notice note %}}
`echo` commands are especially useful inside of Bash scripts. In any given Bash script many things be happening and outputting some message to the individual that invokes the script is a very useful feature.
{{% /notice %}}

The `echo` command can be used to easily view the contents of a Shell Variable. Your home directory, path, and many other variables are attached directly to your Bash Shell in the form of variables. You can use `echo $VARIABLE` to easily view the contents of the variable.

### Bash Shell Variables

#### `echo $BASH`

![](pictures/echo-bash-variable.png)

The `$BASH` shell variable contains the absolute path to the shell this session is using. 

#### `echo $HOME`

![](pictures/echo-home-variable.png)

The `$HOME` shell variable contains the absolute path to the home directory of the user that initiated the Bash shell.

#### `echo $PATH`

![](pictures/echo-path-variable.png)

The `$PATH` shell variable contains a collection of all of the tools currently accessible to this current Bash Shell session.

Any files and subdirectories found within the listed directories are available to be invoked by name.

{{% notice tip %}}
If you have ever tried to run a program before and received a message about the command not being found in the path, this is what it was referring to. When installing new programming languages, build tools, or really any software that needs to be used from a shell the location of the tool *must* be added to the path variable. Lots of software installations take care of adding the tool to your path by either editing the PATH variable or by simply adding the binary of the software directly to one of the directories listed in your path.
{{% /notice %}}
#### `echo $BASHPID`

![](pictures/echo-bashpid-variable.png)

The `$BASHPID` shell variable contains the process ID of the current Bash Shell. This number will likely be different for everyone. In fact if you open your current terminal and open a new one and then check the `$BASHPID` shell variable you should notice that it is different.

Every running program has at least one process running and therefore a process ID. Many programs will create multiple processes and each of their children processes will have unique IDs, however the program's initial main process is the parent of all other associated process IDs.

{{% notice note %}}
We will not be learning about processes in this class. Taking the time to learn about processes will make you a better Linux user, but goes deeper than we need to know in this class.
{{% /notice %}}

#### `kill` command

The `kill` command sends signals to a specific process. These signals give you a way to affect the process. 

One of the most common signals we may want to send to a running process is to end the process. This would immediately stop the process and free up any CPU, RAM, or hard disk operations the process is currently utilizing.

Sending signals to a process is a powerful tool for using Linux. You will not be expected to know the `kill` command in this class.

However, if you want to try the command out, you can send a signal to your `$BASHPID` to kill the process.

Take note of your `$BASHPID`.

Then enter `kill -9 your-bash-pid`, but enter the number of your `$BASHPID`.

![Kill Bash Shell](pictures/kill-bash-shell.png)

Upon entering this command you should see your terminal close immediately!

Once you entered the command the Bash Shell sent a `SIGKILL` (`-9`) signal to the process associated with your `$BASHPID`. The `SIGKILL` signal notifies the operating system the process, and any child processes, needs to be terminated immediately and must be completed. Your operating system acts on the command and the Bash Shell associated with your `$BASHPID` is closed.

There are various other signals that can be sent to processes, but they go beyond the scope of this class.

{{% notice warning %}}
Linux will perform whatever commands you instruct it to. You could conceivably start sending `SIGKILL` signals to random process IDs and Linux will terminate them. Everything running on your operating system has a process ID and you could terminate a process responsible for the Graphical User Interface of your operating system, or some software managing your hardware, which would require you to restart your machine to fix the issue.
{{% /notice %}}

{{% notice bonus %}}
If you want to send a `SIGKILL` signal to your `$BASHPID` without first looking up the value of the Shell Variable you can do that with a Bash Variable Substitution. You can simply reference the variable directly in a Bash Command!
![Bash Variable Substitution](pictures/bash-variable-subtitution.png)
{{% /notice %}}

### `which` command

### Getting Help

#### `man` command

#### `--help` option
