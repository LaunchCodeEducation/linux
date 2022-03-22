---
title: "VirtualBox"
draft: false
weight: 100
originalAuthor: "John Woolbright" # to be set by page creator
originalAuthorGitHub: "jwoolbright23" # to be set by page creator
reviewer: "Paul Matthews" # to be set by the page reviewer
reviewerGitHub: "pdmxdd" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## VirtualBox

This configuration will walk you through the steps of downloading and installing [Oracle VM VirtualBox](https://www.virtualbox.org/).

VirtualBox is a *virtualization* tool. It will allow you to create a virtual operating system inside of your host operating system. Using this tool we will be able to begin working with a Linux Operating System inside of your personal operating system without compromising the integrity of your current Operating System. VirtualBox will handle all the implementation details and will create a isolated sandbox environment with the guest Linux Operating System.

## Downloading

First up we need to download the VirtualBox software onto our host machine.

At the time of writing VirtualBox 6.1 is the Oracle recommended version, however we recommend using the currently recommended version when you are downloading VirtualBox. See the following picture as an example.

![VirtualBox Homepage](pictures/virtualbox-homepage.png?classes=border)

Clicking the giant blue button stating `Download VirtualBox 6.1` should lead you to the [downloads page](https://www.virtualbox.org/wiki/Downloads) which has links for many common Operating Systems. The downloads page should like the following image.

![VirtualBox Downloads](pictures/virtualbox-downloads.png?classes=border)

On this page you should see multiple links that coincide with your Operating System. Upon clicking one of these links it should automatically start a download that will work for your OS.

{{% notice note %}}
If you are using a Linux based operating system the link from the downloads page will take you to another page with various options, find the one for your specific distribution. If you are currently using a Debian based Linux distribution you should be able to just use it with the instructions in this class and don't need to install VirtualBox, or setup an Ubuntu virtual machine. However, there will likely be slight differences between your outputs, and file locations from what is listed in this course.
{{% /notice %}}

## Installation Instructions

{{% children %}}
