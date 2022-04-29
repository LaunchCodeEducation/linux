---
title: "Home"
date: 2021-10-01T09:28:27-05:00
draft: false
---

## Linux

### What is this Course

<!-- #### Generally -->

This course is an introduction to the Linux and the Command Line.

<!-- #### Specifically -->

This course is designed to provide an understanding of the fundamental skills necessary to deploy web applications to a server using a Linux Operating System.
You will learn about many of the operational tools used when working with a server.

### Why take this Course

<!-- #### Generally -->

Learning how to give instructions to a computer so that it performs any given task is the job of someone who works in tech. In this course you will learn and practice giving text based commands to a computer using the terminal to accomplish tasks.

{{% notice note %}}
You have likely learned a programming language in the past. Programming languages are a great way to create applications that run on a computer that usually serve a third party user. Working with a terminal is a way of providing exact instructions to a computer with you as the end user.
{{% /notice %}}

<!-- #### Specifically -->

Linux can be used in many ways to solve many problems, but we will specifically be learning Linux to serve as the **deployment environment** for web applications.

You will learn:
1. How to Create, Read, Update, and Delete files with the Linux file system
1. How to deploy a React project, Angular project, Spring project, and .NET project.
1. How to configure a production grade web server (Caddy, NGINX)
1. Package managers
1. How to automate tedious tasks with bash scripting
1. How to schedule tasks to execute at a specific time or on a recurring schedule
1. How to configure a service to start upon system boot or failure
1. How to craft http requests and render responses from a terminal
1. How to search files or terminal output
1. Git Basics and Collaborative strategies

{{% notice note %}}
A large percentage of cloud resources are Linux based.

These resources talk about the prevelence of Linux in cloud computing:
- [Red Hat](https://www.redhat.com/en/resources/state-of-linux-in-public-cloud-for-enterprises)
- [Linux Article: zdnet](https://www.zdnet.com/article/microsoft-developer-reveals-linux-is-now-more-used-on-azure-than-windows-server/)
[]()
{{% /notice %}}

### Where this Course leads

Upon completing this course you will be capable of configuring a server with deployed web applications.

The next step would be to learn cloud basics so that you can make the deployed application available on the internet.

Additionally this leads to:
- Operations
- Docker/Containers
- CI/CD Pipelines

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