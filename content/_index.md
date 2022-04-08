---
title: "Home"
date: 2021-10-01T09:28:27-05:00
draft: false
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Linux

Welcome. This course explores Linux.

We won't cover Linux exhaustively because it is a massive tool. 

Linux can be used in many ways to solve many problems, but we will specifically be learning Linux to serve as the **deployment environment** for web applications.

### Segments / Chapters

{{% children %}}

#### Configurations

- [Configurations Home]({{< relref "./configurations" >}})
  - [VirtualBox Download & Installation]({{< relref "./configurations/virtualbox" >}})
  - [Ubuntu Image in VirtualBox]({{< relref "./configurations/ubuntu" >}})

### Schedule

#### Day One

- Morning
  - [Introduction]({{< relref "./introduction" >}})
  - [Bash: Introduction]({{< relref "./bash-introduction" >}})
- Afternoon
  - [Bash: File System]({{< relref "./file-system" >}})

#### Day Two

- Morning
  - [Package Manager]({{< relref "./package-manager" >}})
  - [Userspace Applications]({{< relref "./userspace-applications" >}})
- Afternoon
  - [Git]({{< relref "./git" >}})

#### Day Three

- Afternoon
  - [Cron]({{< relref "./cron" >}})

#### Day Four

- Morning
  - [General Web Server Concepts & Key Terminology]({{< relref "./web-server" >}})
  - [General Web Server Slides]({{< relref "./web-server/slides" >}})
  - [Caddy]({{< relref "./web-server/caddy" >}}) (installation through static website)
  - [NGINX]({{< relref "./web-server/nginx" >}}) (installation through static website)
- Afternoon
  - [Caddy]({{< relref "./web-server/caddy" >}}) (Reverse Proxy)
  - [NGINX]({{< relref "./web-server/nginx" >}}) (Reverse Proxy)
  - [Web Server Exercises]({{< relref "./web-server/exercises" >}})

#### Day Five

- Morning
  - [systemd]({{< relref "./systemd" >}})
- Afternoon
  - [Final Project]({{< relref "./final-project" >}})
