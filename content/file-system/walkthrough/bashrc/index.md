---
title: "Bashrc"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 8
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
---

## The `~/.bashrc` File

In your `/home/student` directory you should find a hidden file called `.bashrc`.

![ls -a](pictures/ls-a-bashrc.png?classes=border)

The contents of the `~/.bashrc` file are executed as a new user invoked Bash shell is initialized.

Let's take a look at the contents of the existing `.bashrc` file with `cat`.

![cat ~/.bashrc](pictures/cat-bashrc.png?classes=border)

There is a lot going on in this file that we don't need to worry about right now. However, if you scroll up you will find a section that looks like this:

```bash
# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
```

There are a few Bash aliases already programmed into our Bash shell. We should be able to execute them since the `.bashrc` file was run when our Bash shell session was being initialized.

Let's try them out.

### Execute `ll`

![ll](pictures/ll.png?classes=border)

### Execute `la`

![la](pictures/la.png?classes=border)

### Execute `l`

![l](pictures/l.png?classes=border)

Without defining any of the aliases they were still loaded into our Bash shell session because they exist in `~/.bashrc` file which was run upon initializing our current Bash shell session!

## Uses of `~/.bashrc`

Any personal changes you would want to make to your Bash shell sessions would go in this file. Those changes may include:

- Creating new Shell variables
- Editing any existing Shell variables (like adding your own personal `/home/student/bin` to only your `$PATH` variable)
- Adding any personal use Bash `aliases`
- Changing the color scheme of your terminal

Really anything you would want to happen as your Bash shell session initializes would go into your personal `~/.bashrc` file.