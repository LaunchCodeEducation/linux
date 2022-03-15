---
title: "Adding Package & Repository"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 8
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Example: Adding New Package Repository & Package

In many cases you may want to add a new third party Package. You could do so manually, by downloading the package, and manually building the tool, then adding the tool to your `$PATH`.

However, when you need to update the new package you would have to replicate the steps after removing the old version. Many third party tools provide a Package Repository that you can simply add to your list of user-defined Package Repositories, and then you can manage it's installation, upgrading, and removal all from the Package Manager CLI.

We are going to use the Docker Engine as an example.

{{% notice note %}}
This specific course will not touch Docker at all. Docker provides solid documentation and their website provides exact instructions for adding their package repository and installing their package in Ubuntu (and other distros).
{{% /notice %}}

https://docs.docker.com/engine/install/ubuntu/

## Setup the Docker Repository

### Update Package Repository List

```bash
sudo apt update -y
```

### Check for Tools Necessary for Adding Repository

To add the Docker Package Repository we will need a few command line tools. They all come pre-installed as a part of Ubuntu 20.04.

The Docker Installation Guide makes no assumptions about your current distribution. So they include a snippet that installs all of the tools. When you use `apt` to install a tool that already exists, it doesn't throw an error, and will not stop the remaining tools from installing.

As the user of our machine it is our responsibility, and a good chance to practice, to ensure all of the tools are properly installed.

#### `ca-certificates`

```bash

```

#### `curl`

```bash

```

#### `gnupg`

```bash

```

#### `lsb_release`

```bash

```

#### Installing Anyway!

Let's see what happens when we run an install command when all of the tools are already installed on our machine.

```bash
sudo apt install ca-certificates curl gnupg, lsb-release
```

### Add Docker's GPG Key

<!-- TODO: high level blurb about GPG public/private key relationship to ensure a level of security -->

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

#### Command Breakdown

`curl` makes web requests from the terminal. We are requesting Docker's public key.

{{% notice bonus %}}
You can run `curl https://download.docker.com/linux/ubuntu/gpg` by itself to see the actual key.
{{% /notice %}}

We are passing the output (the key we just requested) to the next command `sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`.

This command is packing the key into the proper format and then writing the key to the file: `/usr/share/keyrings/docker-archive-keyring.gpg`.

This key will be used in the next step.

### Add the Docker `stable` Repository

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
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

### Install the Docker Tools

```bash
sudo apt update
```

```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```