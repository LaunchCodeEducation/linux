---
title: "Exercises"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Exercises

The more practice you get with the tools in this class, the more comfortable, and faster with them you will become.

We haven't learned how to use many tools yet, but we can still practice what we have learned. We want you to walk away from this chapter with a basic understanding of the terms presented and to be comfortable with Bash command structure, and the commands presented in the Walkthrough.

### Practice

- write down the absolute path for each of the following commands:
  - `bash`
  - `which`
  - `echo`
  - `ls`
  - `users`
  - `cat`
  - `less`
  - `man`
  - `kill`
- use the **man pages** to read the DESCRIPTION of each of the previous commands

## Questions & Answers

### How many directories does your `$PATH` variable currently contain?

{{% expand "CLICK FOR ANSWER" %}} 
**9**
- `/usr/local/sbin`
- `/usr/local/bin`
- `/usr/sbin`
- `/usr/bin`
- `/sbin`
- `/bin`
- `/usr/games`
- `/usr/local/games`
- `/snap/bin`
{{% /expand %}}

### What command was `less` based on? Check out the `less` *man page* for the answer!

{{% expand "CLICK FOR ANSWER" %}} `more`{{% /expand %}}

### Is the answer from the previous question a command you can use?

{{% expand "CLICK FOR ANSWER" %}} **Yes** try `less /etc/passwd` and `more /etc/passwd`{{% /expand %}}

### Does the command from the previous answer have a **man page**?

{{% expand "CLICK FOR ANSWER" %}} **YES** try `man more`{{% /expand %}}

### How can you exit or terminate your currently running emulator?

{{% expand "CLICK FOR ANSWER" %}} `kill -9 $BASHPID`{{% /expand %}}

### Is there any way you can terminate the terminal emulator using the terminal emulator window?

{{% expand "CLICK FOR ANSWER" %}} **YES** click the red x button in the terminal emulator window.{{% /expand %}}

### There is a command built directly into Bash for exiting a Bash Shell. Can you guess it?

{{% expand "CLICK FOR ANSWER" %}} 
`exit`. Using the built-in `exit` command is the preferred way to terminate a Bash Shell!
{{% /expand %}}
