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

- `systemd` has 2 major responsibilities
  - initialize actions at specific states (machine power-on, machine power-off, user login, user logout, machine crash, kernel panic, etc)
  - manage ongoing services & daemons
- initialization system
  - `systemd`
- daemon
- service
- where system daemon and service files live (existing services and daemons)
- defining custom daemon or service with a unit file
- where personal daemon and service files live
- `systemctl`
  - `start`
  - `stop`
  - `enable`
  - `disable`
  - `status`
- `journalctl`

## Content Links

{{% children %}}
