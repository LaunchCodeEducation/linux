---
title: "Reading Packages"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 115
---

Being able to access the metadata of package can be useful. This article shows how to view all currently installed packages, and how to look at some of the metadata associated with any specific installed package.

## Viewing All Installed Packages

Enter: `apt list --installed`

![apt list --installed](pictures/apt-list-installed.png?classes=border)

There are so many installed packages that they cannot be displayed within one Bash shell session.

{{% notice note %}}
It's pretty rare you would need to see **all** of the installed packages on a machine. It is much more informative to look at the metadata for a specific package.
{{% /notice %}}

## Viewing a Specific Package

You can use the `apt show` command to view some of the metadata, and OS level configuration information about any specific package. The structure for this command is: `apt show [package]`. Go ahead and try it out on a couple of different packages

### Enter `apt show apt`

![apt show apt](pictures/apt-show-apt.png?classes=border)

### Enter `apt show bash`

![apt show bash](pictures/apt-show-bash.png?classes=border)

### Enter `apt show python3`

![apt show python3](pictures/apt-show-python3.png?classes=border)

## Package Metadata Breakdown

Each of the examples listed above show a ton of different metadata including:

- Package: The name of the package
- Version: The version of the currently installed package
- OS Priority: If this package is required for the current distribution to operate normally
- Origin: The party that controls the package
- Maintainer: The party that maintains the package
- Depends: All the packages this specific package needs to function properly
- Suggests: Additional related packages you may want to use in addition to this package
- Description: What the package is used for

{{% notice note %}}
All of this metadata simply describes the package. However to learn how to use the package you should look at the package homepage, the `man` reference page, or the ``--help`` option.
{{% /notice %}}