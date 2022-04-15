---
title: "Review & Changing Directories"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 100
---

### Review: Where am I?

To get your bearings and view your current working directory you can use the familiar `pwd` command.

![pwd](pictures/pwd.png?classes=border)

{{% notice note %}}
The `pwd` command simply prints out the contents of the `$PWD` shell variable. Don't forget you can see the contents of any shell variables with the `echo` command!
{{% /notice %}}

### Review: What are the contents of this location?

To view the contents of the current working directory you can use the familiar `ls` command without any arguments.

![ls no arguments](pictures/ls-no-args.png?classes=border)

### Change Current Working Directory

To change the current working directory you can use the `cd` *builtin* command. 

`cd` allows for one optional argument. If no argument is provided it will set the current working directory to the `$HOME` shell variable.

`cd` works with both *absolute* and *relative* paths.

#### `cd` relative path

Starting from the home directory we could move into the `Documents/` directory with the following command:

`cd Documents`

![cd Documents](pictures/cd-documents.png?classes=border)

Take note from the image that our terminal emulator always tells us the current working directory. You should see `~/Documents$` directly before the character where you can enter text commands. You can also see on the previous line before the `cd` command had been executed the text directly before our input area is only `~$`. 

#### `cd` absolute path

Our current working directory is `/home/student/Documents`. We can return to the home directory by using an absolute path:

`cd /home/student/`

![cd /home/student](pictures/cd-home-student.png?classes=border)

And we're back to `$HOME`!

The main benefit in using an *absolute* path as the argument for the `cd` command is it will work from any location. The absolute path is an unique identifier for a directory.

#### Shell Shortcuts

Another useful tool for changing directories is to learn some of the Bash shell shortcuts.

- `~`: a shortcut for the `$HOME` variable
- `.`: a shortcut for the current working directory (`$PWD` variable)
- `..`: a shortcut for the parent of the current working directory

##### Shortcut Home

From a terminal change into the root directory:

`cd /`

![cd-root](pictures/cd-root.png?classes=border)

From the root directory change into the home directory by using the home shortcut:

`cd ~`

![cd ~](pictures/cd-tilde.png?classes=border)

{{% notice note %}}
The default argument for the `cd` command is the home directory. An even more efficient shortcut for changing into the home directory would be simply `cd` with no arguments. Try it out on your own, by changing into the root directory, and then entering `cd` without any arguments.
{{% /notice %}}

##### Shortcut to Parent

From your home directory let's change into the parent directory using the `..` shortcut:

`cd ..`

![cd ..](pictures/cd-dot-dot.png?classes=border)

Using the parent directory shortcut we were able to move up one directory.

{{% notice green "Bonus" "rocket" %}}
You can extend the parent and current directory shortcuts. Assuming you are in `/home/student/Documents` you can change into `/home/student/Desktop` with the command: `cd ../Desktop`.
![cd ../Desktop](pictures/cd-dot-dot-desktop.png?classes=border)
Additionally, the parent and current directory shortcuts can be used with most bash commands.
{{% /notice %}}