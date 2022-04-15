---
title: "Adding Package & Repository"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 140
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

{{% notice green "Bonus" "rocket" %}}
GPG works by having two linked keys a public key, and a private key. A public key can be shared with anyone, the private key remains secret and in the control of an individual. Data can be encrypted by either the public or private key and key be decrypted by the alternate key. Because of this encryption a user can create a digital signature that the other party can decrypt and verify.
{{% /notice %}}

In this specific case (adding a package repository from Docker) we are adding the Docker public key to our `gnupg` keychain. This way docker can create a digital signature (using their private key) that we can verify (using our public key). Docker can also encrypt (using their private key) the payload of data and we can decrypt (using our public key) the data.

The command for requesting the Docker public gpg key and adding it to our personal pgp keyring is as follows:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

That is a complex command that is using the pipe (`|`) operator. Which means the output from the first command is being passed as the input to the second command.

Let's break these commands down to get a better understanding of what's happening.

#### Command Breakdown

`curl` makes web requests from the terminal. The `curl https://download.docker/com/linux/ubuntu/gpg` command is requesting Docker's public key to be printed out to the terminal (STDOUT).

{{% notice green "Bonus" "rocket" %}}
You can run `curl https://download.docker.com/linux/ubuntu/gpg` by itself to see the actual key.
![curl https://download.docker.com/linux/ubuntu/gpg](pictures/curl-docker-gpg-key.png?classes=border)
We don't need to understand this key, we simply need it to verify Docker's signature.
{{% /notice %}}

The output (the text of the key listed in the picture above) is being passed to the next command `sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`.

This command is packing the key into the proper format (`.gpg`) and then writing the key to the file: `/usr/share/keyrings/docker-archive-keyring.gpg`.

After running the full command, the Docker public key is now on our `gpg` keyring and will be used to verify any signatures from Docker! 

### Add the Docker `stable` Repository

Now that we have the Docker public key on our keyring we can add the Docker repository to our computer. It's another complex command we will break down:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb-release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Wow, that's a lot of stuff packed into one line. Let's break it down.

#### Command Breakdown

In the command there are two Bash operators (`|` and `>`), meaning there are three separate bash commands. Let's look at them one at a time:

The Pipe Operator (`|`) passes the output from the first command and uses it as the input for the next command.

The Output Redirection Operator (`>`) passes the output from the first command to be written as a file in the second command.

#### The `echo ...` portion

The `echo` command is just displaying something to the Bash shell's display (STDOUT).

You can run this part of the command completely on your own to see the contents of this command:

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb-release -cs) stable"
```

Which results in the following output:

![echo package repo](pictures/echo-package-repo.png?classes=border)

The output is difficult to see so we will share it here:

```bash
deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu focal stable
```

Overall it's a simple line. One line of output that contains:

- the architecture of our computer (`amd64`)
- the key to use when using this repo (`docker-archive-keyring.gpg`)
- the package repo URL (`https://download.docker.com/linux/ubuntu`)
- our distributions canonical name (`focal`)
- the type of repository to add (`stable`)

This is the information necessary for a package repository to work.

{{% notice green "Bonus" "rocket"  %}}
This information is eerily similar to the Ubuntu provided package repositories that come standard with your distribution. Print out the contents of the package repositories in `/etc/apt/sources.list` with `cat /etc/apt/sources.list`.
![cat /etc/apt/sources.list](pictures/cat-etc-apt-sources-list.png?classes=border)
There are multiple uncommented out lines that are similar to the line we just printed out.
{{% /notice %}}

#### The `sudo tee ...` portion

The output from the previous `echo` command is passed to: `sudo tee /etc/apt/sources.list.d/docker.list`.

By simply taking a look at the `tee` package's man page we will see it's description:

![man tee](pictures/man-tee.png?classes=border)

It reads from standard input (the result of the `echo command` in the previous step) and writes it to a file in this case `etc/apt/sources.list.d/docker`. So the contents we printed to our display in the previous step will simply be written to this new file.

#### The `/dev/null` portion

Finally a really weird section the output from the previous `tee` command is being directed to a file called `/dev/null`.

`/dev/null` is a special file that when you write to it the contents are immediately deleted.

The `tee` command expects to write the result of creating the new file to a completely different file and will throw an error if the results aren't written somewhere.

So we are using the `/dev/null` file as a location to write the expected output, where it is immediately discarded.

## Install the Docker Tools

Now that we have written the package repository to the appropriate location `/etc/apt/sources.list.d/docker` we can use the package repository to install and maintain the packages associated with that repo.

### Update the Package Repository List

Not only is a good idea to update our package repository list, but we need to because we just added a brand new package repository, and we need to instruct the `apt` CLI to update itself.

```bash
sudo apt update -y
```

### Install the Packages with `apt`

Finally we can install the packages associated with docker using the `apt` CLI.

```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

## Review

We have successfully:

- web requested the Docker public key
- added the Docker public key to our gpg keyring
- added the Docker Package Repository
- installed Docker and associated packages using the `apt` CLI