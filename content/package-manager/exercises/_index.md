---
title: "Exercises"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 115
---

## Exercises

Install the packages in the following articles:

{{% children %}}

{{% notice note %}}
The Visual Studio Code (`VSC`) installation is optional.
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