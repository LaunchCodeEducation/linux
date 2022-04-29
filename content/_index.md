---
title: "Home"
date: 2021-10-01T09:28:27-05:00
draft: false
---

## Linux


### What is this Course

#### Generally

#### Specifically

### Why take this Course

#### Generally

#### Specifically

### Where this Course leads
- Cloud Basics
- Operations
- Docker/Containers
- CI/CD


<!-- This course is designed to provide you with the 

What can I accomplish with concepts and skills learned?
- Learning how to give CLI text based instructions to a computer to perform specific tasks
- Deploy web apps
- Prepare for Cloud Computing

What do I need to know to take this course?

How will this help me perform a job in the future? -->

<!-- Welcome. This course explores Linux.

We won't cover Linux exhaustively because it is a massive tool. 

Linux can be used in many ways to solve many problems, but we will specifically be learning Linux to serve as the **deployment environment** for web applications. -->

## Segments / Chapters

{{% children %}}

## Pre-Course Requirements

The only dependancy for this class is that you have VirtualBox installed on your machine and you are able to run Ubuntu 20.04. The configurations walkthrough will take you through the steps for both Windows and MacOS installations.

### Configurations

- [Configurations Home]({{< relref "./configurations" >}})
  - [VirtualBox Download & Installation]({{< relref "./configurations/virtualbox" >}})
  - [Ubuntu Image in VirtualBox]({{< relref "./configurations/ubuntu" >}})

## Schedule

### Day One

- Morning
  - VirtualBox Installation Validation
  - [Linux: Introduction]({{< relref "./introduction" >}})
  - [Bash: Introduction]({{< relref "./bash-introduction" >}})
- Afternoon
  - [Bash: Streams, Redirection, & Pipes]({{< relref "./bash-streams-redirection-pipe" >}})
  - [Bash: File System]({{< relref "./file-system" >}})
  - [File Permissions]({{< relref "./file-permissions" >}})

### Day Two

- Morning
  - [Package Manager]({{< relref "./package-manager" >}})
  - [Git]({{< relref "./git" >}})
- Afternoon
  - [Userspace Applications]({{< relref "./userspace-applications" >}})
    - [Wget]({{< relref "./userspace-applications/walkthrough/wget" >}})
    - [Curl]({{< relref "./userspace-applications/walkthrough/curl" >}})

### Day Three

- Morning
  - [Userspace Applications: Continued]({{< relref "./userspace-applications" >}})
    - [Grep]({{< relref "./userspace-applications/walkthrough/grep" >}})
    - [Sed]({{< relref "./userspace-applications/walkthrough/sed" >}})
- Afternoon
    - [Userspace Applications: Continued]({{< relref "./userspace-applications" >}})
      - [Vim]({{< relref "./userspace-applications/walkthrough/vim" >}})
  - [Bash: Scripting]({{< relref "./bash-scripting" >}})

### Day Four

- Morning
  - [Cron]({{< relref "./cron" >}})
  - [Web Servers]({{< relref "./web-server" >}})
- Afternoon
  - [Web Servers Continued]({{< relref "./web-server" >}})

### Day Five

- Morning
  - [systemd]({{< relref "./systemd" >}})
- Afternoon
  - [Final Project]({{< relref "./final-project" >}})