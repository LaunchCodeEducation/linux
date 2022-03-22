---
title: "Exercises"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 115
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "John Woolbright" # update any time edits are made after review
lastEditorGitHub: "jwoolbright23" # update any time edits are made after review
lastMod: 2022-03-15 # UPDATE ANY TIME CHANGES ARE MADE
---

## Exercises

Install each of the following packages:

### Vim: `vim` package

Let's start off easy. We installed this and then removed it during our walkthrough. 

Reinstall the package as we will be using it in a later lesson.

### cURL: `curl` package

We will be using the cURL tool in a later lesson. Go ahead and install it now.

### Visual Studio Code: `code` package

Visual Studio Code is a very popular text and code editor. It is graphical in nature, and does not offer a terminal version. However, due to it's popularity let's install it on our machines.

There isn't an official Ubuntu repository for Visual Studio Code, however the Microsoft documentation provides an excellent article for [installing VSC on Linux](https://code.visualstudio.com/docs/setup/linux) systems:

![code installation instructions](pictures/code-installation-instructions.png?classes=border)

The picture above shows the exact steps for adding the repository, with gpg key, and then installing the `code` package.

{{% notice green "Bonus" "rocket" %}}
If you visit the [actual article](https://code.visualstudio.com/docs/setup/linux) you will find there is another way to complete the steps in a more streamlined process.
{{% /notice %}}

## Questions & Answers

### What is a package?

{{% expand "CLICK FOR ANSWER" %}}
A **package** is software and related metadata.
{{% /expand %}}

### What is a package repository?

{{% expand "CLICK FOR ANSWER" %}}
A **package repository** is the web address where the package files can be downloaded.
{{% /expand %}}

### What is a package manager?

{{% expand "CLICK FOR ANSWER" %}}
A **package manager** is a tool that is used to manage packages. There are commonly CLI and GUI programs for interfacing with a Linux distributions underlying package management system.
{{% /expand %}}

### What is the package manager for Ubuntu that we learned in this course?

{{% expand "CLICK FOR ANSWER" %}}
We learned about the Advanced Packaging Tool known as `apt`.
{{% /expand %}}

### How can you learn more about the `apt` CLI?

{{% expand "CLICK FOR ANSWER" %}}
Three ways:
- `man apt`
- `apt --help`
- Searching the internet for assistance (reading the `apt` online documentation)
{{% /expand %}}

### How can you list all package repositories?

{{% expand "CLICK FOR ANSWER" %}}
`apt list`
{{% /expand %}}

### What is the source of the package repositories?

{{% expand "CLICK FOR ANSWER" %}}
`/etc/apt`
{{% /expand %}}

### How do you update the package repositories?

{{% expand "CLICK FOR ANSWER" %}}
`sudo apt update`
{{% /expand %}}

### How can you view all installed packages?

{{% expand "CLICK FOR ANSWER" %}}
`apt list --installed`
{{% /expand %}}

### How can you view the metadata for any specific package?

{{% expand "CLICK FOR ANSWER" %}}
`apt show [package-name]`
{{% /expand %}}

### Using `apt` how do you find packages?

{{% expand "CLICK FOR ANSWER" %}}
`apt search [package-name]`
{{% /expand %}}

### Using the internet how do you find packages?

{{% expand "CLICK FOR ANSWER" %}}
Use a search engine! A common phrase for finding valid articles: `[package-name] Ubuntu Installation`.
{{% /expand %}}

### How do you install packages with `apt`?

{{% expand "CLICK FOR ANSWER" %}}
`sudo apt install [package-name]`
{{% /expand %}}

### How do you remove packages with `apt`?

{{% expand "CLICK FOR ANSWER" %}}
`sudo apt remove [package-name]`
{{% /expand %}}

### How do you upgrade all installed packages?

{{% expand "CLICK FOR ANSWER" %}}
`sudo apt upgrade -y`
{{% /expand %}}

### What would including the `-y` option when using `apt` accomplish?

{{% expand "CLICK FOR ANSWER" %}}
It would auto confirm the `apt` action being performed including: updating, installing, removing, upgrading.
{{% /expand %}}