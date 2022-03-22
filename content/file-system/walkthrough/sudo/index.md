---
title: "Sudo"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 9
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
---

## The `sudo` command

The `sudo` command stands for **SU**bstitute **U**ser **D**o. It allows you to run any Bash command as a substitute user.

The `sudo` command is most *commonly used* to run a command as the **root** user that has full permissions to everything on the machine.

{{% notice note %}}
When using the `sudo` command to execute a command as a different user, your user must be in the `sudoers` file. **You will be prompted to enter your password to authenticate the user and execute a command as another user**. Ubuntu by default adds all new general users to the `sudoers` file. There is a `sudoer` bash command for managing the `sudoers` file. The `sudoer` file exists in the `/etc` directory.
{{% /notice %}}

Let's take a look at how to use the powerful `sudo` command.

### The `whoami` command

The `whoami` command simply displays the current user.

Go ahead and execute the `whoami` command:

![whoami](pictures/whoami.png?classes=border)

This makes a lot of sense. We are the `student` user.

#### The `whoami` command as the daemon user

Run the same command this time as the `daemon` user.

Execute `sudo -u daemon whoami`:

![sudo -u daemon whoami](pictures/daemon-whoami.png?classes=border)

You will be prompted to enter your password, which if you followed the configuration guide in this course should be **admin**. As you type **nothing will be displayed** on the terminal, this is a security feature so someone that can see your terminal will not know what your password is. After typing your password hit enter. Assuming your password was correct you should see the following:

![sudo -u daemon whoami results](pictures/daemon-whoami-results.png?classes=border)

As we can see we ran the `whoami` command as the `daemon` user and so the display reads `daemon`.

#### The `whoami` command as the root user

Execute `sudo whoami`:

![sudo whoami](pictures/root-whoami.png?classes=border)

The default for the `sudo` command is to execute the command as the `root` user.

## Using `sudo`

Running a command as the `root` user is sometimes necessary. You may need to read, or edit a file that your current user doesn't have read or write access to. However, the `root` user always has read, write, and execute access to all files. Making `sudo [command]` a very useful tool to have in your pocket.

As an example let's say we needed to read the contents of the mysterious `/etc/shadow` file.

![cat /etc/shadow](pictures/cat-etc-shadow.png?classes=border)

Our `student` user doesn't have read access to this file. So we can run the same command as `root`.

`sudo cat /etc/shadow`

![sudo cat /etc/shadow](pictures/sudo-cat-etc-shadow.png?classes=border)

Running the command as the `root` user gave me read access to the file. General user's do not have read access to this file because the file lists **all** users and their hashed password.

You can see clearly that the `student` user's hashed password is: `$6$YQsJ8yJfzXt5L...`. 

{{% notice green "Bonus" "rocket" %}}
A hashed password can be cracked using a rainbow table, which goes way outside the scope of this class. However, knowing that a hashed password can be cracked illustrates why general users **do not have access to read the `/etc/shadow` file**.
{{% /notice %}}