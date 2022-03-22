---
title: "Download Ubuntu Image"
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

In this class we will be using Ubuntu Desktop 20.04.3 LTS, you can find its download [on their website](https://ubuntu.com/download/desktop).

{{% notice note %}}
The Ubuntu ISO that you will be using is 3.4 GB in size. You will also be allocating 12.00 GB of space onto our Virtual Machine Image. Please ensure that you have a minimum of 16 GB of free space on your host machine before moving forward with the next steps in this walkthrough.
{{% /notice %}}

## Download Image

![Ubuntu Desktop Download Homepage](pictures/ubuntu-download-desktop.png?classes=border)

Click the green `Download` button to start the download. It is a large file and will take some time.

You will likely have to confirm the download, in the picture below the user will need to click `Save File` for the file to be downloaded onto the host computer.

![Ubuntu Desktop Download Initiated Page](pictures/ubuntu-download.png?classes=border)

Regardless of your host OS we will all be using a similar file `ubuntu-20.04.3-desktop-*.iso`. An `.iso` file is a Disk Image which is the instruction for installing an Operating System. We will be using this file inside of Virtualbox to create an isolated Ubuntu 20.04.3 virtual operating system inside of our host computer.