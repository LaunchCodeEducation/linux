---
title: "Slides"
date: 2021-11-09T15:13:39-06:00
draft: false
# type: "slides"
weight: 1
originalAuthor: "Paul Matthews"
originalAuthorGitHub: "pdmxdd"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub: ""
lastEditor: "" # update each time the file is edited
lastEditorGitHub: "" 
lastMod: 2022-03-09
---

<!--  TODO: remove this comment

- Package: software
  - `cat /etc/apt/sources.list`
  - `man sources.list`
  - `ls /etc/apt/sources.list.d`
- Package Repository: source of the software
  - https://packages.ubuntu.com/
  - `lsb_release -a`: focal: https://packages.ubuntu.com/focal/
    - `lsb_release -cs`: focal
  - `apt list`
  - `apt list --installed`
- Package Manager: tool for managing packages (installing, removing, upgrading, adding new repositories)
  - `.tar`
  - **Debian**
    - packages: DEB 
    - package managers: `apt` / `apt-get` & `apt-cache`
  - **Red Hat**
    - packages: RPM
    - package managers: `yum` / `dnf` / `rpm`
  - OpenSUSE: `zyyper`
  - Arch: `pacman`
  - tons of options
- APT
- CLI: `apt`
  - Older CLI tools: `apt-get` & `apt-cache`
- `apt list`
  - `apt list --installed`
- `apt show [package]`
  - `apt show bash`
  - `apt show firefox`

-->

{{< slides >}}

## Package Manager

A key aspect of a Linux distribution is the **Package Manager**.

A distribution's package manager is the preferred tool for managing software on the computer.

---

## Package

A **Package** is software and additional metadata.

The additional metadata includes: *dependencies*, *version*, *origin*, *essential* to operating system, *conflicts*, *source*, and more.

---

## Package Repository

---

## Common Package Managers

---

## Package Manager Clients

{{< /slides >}}