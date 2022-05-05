---
title: "Final Project"
date: 2022-03-10T15:47:05-06:00
draft: false
weight: 160
---

## Recap

This class has touched many subjects:

- terminal
- bash
- bash streams, redirection & pipes
- Linux file system & permissions
- package manager
- version control
- bash scripting
- cron
- web servers
- systemd
- additional user space applications

At this point multiple web projects have been deployed to your Linux machine.

Going through the concepts and practicing is how you will become comfortable with the concepts and skills in this course.

For your final project you will be required to **create two initialization scripts**.

An **initialization script** is a **bash** script that is executed after a new virtual machine is created and configures the machine completely and automatically.

Once you have an initialization script for a specific project you can spin up a new Ubuntu machine on any device and run one script which will go through all the steps necessary to deploy a project. Initialization scripts are used commonly in the cloud computing world.

## The Scripts

- `react-tic-tac-toe-configuration-and-deployment.sh`
- `spring-todo-mvc-configuration-and-deployment.sh`

### React

Create an initialization script that when run on a new `Ubuntu 22.04` image configures the machine and deploys the `react-tic-tac-toe-tutorial` project.

### Spring

Create an initialization script that when run on a new `Ubuntu 22.04` image configures the machine and deploys the `spring-todo-mvc` project.

{{% notice note %}}
More information about each required deployment will be provided in an upcoming article.
{{% /notice %}}

## Example Initialization Script

As you have not seen an example of an initialization script we will provide one example for the `angular-tour-of-heroes` project in the next article.

{{% notice note %}}
You are more than welcome to look at the example before starting to write your own initialization scripts, but if you feel like you have an idea of how to begin we recommended starting with your ideas first and referencing the example only when necessary.
{{% /notice %}}

## Content Links

{{% children %}}
