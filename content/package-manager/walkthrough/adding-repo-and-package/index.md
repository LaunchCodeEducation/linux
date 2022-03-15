---
title: "Adding Package & Repository"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 140
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Example: Adding New Package Repository & Package

In some cases you may want to add a new third party Package. You could do so manually by downloading the package, manually building the tool and then adding the tool to your `$PATH`.

However, when you need to update the new package you would have to replicate the steps after removing the old version. 

Many third party tools provide a **Package Repository** that you can simply add to your list of user-defined Package Repositories. Then you can manage its installation, upgrading, and removal all from the Package Manager CLI.

{{% notice note %}}
This specific course will not touch Docker at all. Docker provides excellent documentation and their website provides exact instructions for adding their package repository and installing their package in Ubuntu (and other popular Linux distributions). When you have some free time you should glance over the original [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/) documentation this article is based on.
{{% /notice %}}

This article will **walk you through the steps and explain what is happening**. The linked Docker Docs article provides the following steps:

### Set up the repository

1. Update the `apt` package index and install packages to allow `apt` to use a repository over HTTPS
1. Add Docker's official GPG key
1. Set up the stable repository

### Install Docker Engine

1. Update the `apt` package index, and install the latest version of Docker Engine and containerd
1. Install the `docker-ce` `docker-ce-cli` and `containerd.io` packages

## Setup the Docker Repository

The Docker Docs article beings with instructions around setting up the package repository. We could just run the command, or we can use some of our new Linux skills to check to see if we already have the packages that are being installed.

We will:

1. Update Package Repository List
1. Check for Installed Packages
1. Install any Required Packages
1. Add Docker's official GPG key
1. Add the Docker stable repository

### Update Package Repository List

Before adding any additional packages, or adding a new package repository it's a good idea to update existing package repositories.

```bash
sudo apt update -y
```

### Check for Tools Necessary for Adding Repository

Our first divergence from the Docker instructions.

To add the Docker Package Repository we will need a few command line tools. **Most of the required packages come pre-installed as a part of Ubuntu 20.04.**

{{% notice note %}}
The Docker Installation Guide makes no assumptions about your current distribution. So they include a snippet that installs all of the tools. When you use `apt` to install a tool that already exists, it doesn't throw an error, and will not stop the remaining tools from installing.
{{% /notice %}}

As the user of our machine it is our responsibility, and a good chance to practice, to ensure all of the tools are properly installed.

We will need to figure out if the following packages are installed, and if not to install them:

- `ca-certificates`
- `curl`
- `gnupg`
- `lsb-release`

#### `ca-certificates`

What command can we run to determine if the `ca-certificates` package is currently installed:

```bash
apt list ca-certificates
```

After running this command we can see the output:

![apt list ca certificates](pictures/apt-list-ca-certificates.png?classes=border)

It looks like the `ca-certificates` package is automatically installed as a part of this distribution.

What happens if we try to install it anyway?

```bash
sudo apt install ca-certificates
```

![apt install ca-certificates](pictures/apt-install-ca-certificates.png?classes=border)

#### `curl`

What command can we run to determine if the `curl` package is currently installed:

```bash
apt list curl
```

After running this command we can see the output:

![apt list curl](pictures/apt-list-curl.png?classes=border)

It looks like the `curl` package is **not currently installed** on this distribution.

How can it be installed with `apt`?

```bash
sudo apt install curl
```

![sudo apt install curl](pictures/apt-install-curl.png?classes=border)

{{% notice note %}}
Don't forget we will have to confirm the installation by entering `y` and hitting enter, or by simply hitting enter.
{{% /notice %}}

#### `gnupg`

What command can we run to determine if the `gnupg` package is currently installed:

```bash
apt list gnupg
```

After running this command we can see the output:

![apt list gnupg](pictures/apt-list-gnupg.png?classes=border)

It looks like the `gnupg` package is automatically installed as a part of this distribution.

What happens if we try to install it anyway?

```bash
sudo apt install gnupg
```

![sudo apt install gnupg](pictures/apt-install-gnupg.png?classes=border)

#### `lsb-release`

What command can we run to determine if the `lsb-release` package is currently installed:

```bash
apt list lsb-release
```

After running this command we can see the output:

![apt list lsb-release](pictures/apt-list-lsb-release.png?classes=border)

It looks like the `lsb-release` package is automatically installed as a part of this distribution.

What happens if we try to install it anyway?

```bash
sudo apt install lsb-release
```

![apt install lsb-release](pictures/apt-install-lsb-release.png?classes=border)

### Add Docker's GPG Key

After checking for and installing the prerequisite packages we need to add Docker's GPG key.

GPG stands for **G**NU **P**rivacy **G**uard. It is an implementation of OpenPGP which allows you to asymmetrically encrypt data and create and authenticate digital signatures. 

{{% notice bonus %}}
GPG works by having two linked keys a public key, and a private key. A public key can be shared with anyone, the private key remains secret and in the control of an individual. Data can be encrypted by either the public or private key and key be decrypted by the alternate key. Because of this encryption a user can create a digital signature that the other party can decrypt and verify.
{{% /notice %}}

In this specific case (adding a package repository from Docker) we are adding the Docker public key to our `gnupg` keychain. This way docker can create a digital signature (using their private key) that we can verify (using our public key). Docker can also encrypt (using their private key) the payload of data and we can decrypt (using our public key) the data.


```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

#### Command Breakdown

`curl` makes web requests from the terminal. We are requesting Docker's public key.

{{% notice green "Bonus" "rocket" %}}
You can run `curl https://download.docker.com/linux/ubuntu/gpg` by itself to see the actual key.
{{% /notice %}}

We are passing the output (the key we just requested) to the next command `sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`.

This command is packing the key into the proper format and then writing the key to the file: `/usr/share/keyrings/docker-archive-keyring.gpg`.

This key will be used in the next step.

### Add the Docker `stable` Repository

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb-release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Wow, that's a lot of stuff packed into one line.

#### Command Breakdown

In the command there are two Bash operators (`|` and `>`), meaning there are three separate bash commands. Let's break them down.

The Pipe Operator (`|`) passes the output from the first command and uses it as the input for the next command.

The Output Redirection Operator (`>`) passes the output from the first command to be written as a file in the second command.

##### `echo ...`

The `echo` command is just displaying something to the Bash shell's display (STDOUT).

You can run this part of the command completely on your own to see the contents of this command.

##### `sudo tee ...`

##### `/dev/null`

A special file that when you write to it the contents are immediately deleted.

## Install the Docker Tools

### Update the Package Repository List

```bash
sudo apt update -y
```

### Install the Packages with `apt`

```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```