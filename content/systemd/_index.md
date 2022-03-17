---
title: "systemd"
date: 2022-03-02T09:54:08-06:00
draft: false
weight: 150
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Major Concepts & Key Terminology

- `systemd` is responsible for **initializing** and **managing** daemons and services 
  - initialize daemons and services at various machine states (most commonly power-on but also power-off, user login, user logout, machine crash, kernel panic, etc)
  - manage ongoing services & daemons
    - handle service & daemon dependencies
    - directly control services & daemons
- initialization system
  - `systemd`
  - `Init V`
- daemon: definition
- service: definition
- where system daemon and service files live (existing services and daemons)
  - from https://www.enricozini.org/blog/2017/debian/systemd-01-intro/ linked from [official debian systemd docs](https://wiki.debian.org/systemd/documentation)
  - `/lib/systemd/system/`: for units provided by packaged software
  - `/run/systemd/system/`: runtime-generated units
  - `/etc/systemd/system/`: for units provided by systemd administrators (always a part of the system unit cache)
- defining custom daemon or service with a unit file
- where personal unit files should live:
  - `/etc/systemd/user` (only a part of the unit cache when certain shell variables are true, like when the user is logged in)
  - `$HOME/.config/systemd/user` (only a part of the unit cache when certain shell variables are true, like when the user is logged in)
  - can technically live anywhere, they just have to be linked to correctly so systemd can find them on boot
- `systemctl`
  - `start`
  - `stop`
  - `enable`
  - `disable`
  - `status`
- `journalctl`

## Content Links

{{% children %}}
