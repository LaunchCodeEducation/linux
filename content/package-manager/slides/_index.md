---
title: "Slides"
date: 2021-11-09T15:13:39-06:00
draft: false
hidden: false
# type: "slides"
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Package Manager

A key aspect of a Linux distribution is the **Package Manager**.

A distribution's package manager is the preferred tool for managing software on the computer.

---

## Package

A **Package** is software and additional metadata.

The additional metadata includes: *dependencies*, *version*, *origin*, *essential* to operating system, *conflicts*, *source*, and more.

The package contains the executable software and additional data for managing the software.

___

### Under the Hood

A package is a collection of compressed files that can easily be made into executable files. Many packages are configured to work directly with a package manager. However, it is possible to manually build packages to access the executable software.

For Debian based (like Ubuntu) distributions you will regularly find `.deb` packages.

For RedHat based (like CentOS) distributions you will regularly find `.rpm` packages.

Manual packages are commonly bundled together as a `.tar` file.

---

## Package Repository

All packages that are managed directly by a package manager have an associated **repository**. This is the web location in which the package files can be downloaded.

Part of the Package Manager's responsibilities is in maintaining these package repository lists.

For the major linux distributions there are thousands of repositories. Many of which are maintained by the linux distribution themselves.

___

### Package Repositories in Ubuntu

Checkout the list of Packages managed by Ubuntu for [Ubuntu 22.04 (jammy)](https://packages.ubuntu.com/jammy/)

This is the list of official Ubuntu Packages. You can add new package repositories from parties outside of Ubuntu, which would give you access to even more packages.

---

## Common Package Managers

The majority of Debian based distributions use `APT` (Advanced Package Tool).

The majority of RedHat based distributions use `RPM` (RPM Package Manager).

These are the predominate underlying package managers in the Linux world. However, they are low level tools used directly by the operating system. End users interface with these tools with various text-based or graphical clients.

---

## Package Manager Clients

For `APT` we have the CLI's named `apt` and `apt-get` / `apt-cache`.

For `RPM` there are the CLI's named `rpm` and `yum`.

Most linux distributions that come with a graphical windows system also provide a graphical client to access the underlying package manager (`Ubuntu Software` in Ubuntu 22.04).

We will only be using the CLI options from our Bash shell's.

{{< /slides >}}