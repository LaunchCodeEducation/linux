---
title: "Reading Package Repositories"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 105
---

## Reading Package Repositories

We can view **all** of the managed package repositories with the `apt` CLI by using the `list` argument.

### `apt list`

![apt list](pictures/apt-list.png?classes=border)

There are so many package repositories they exceed the number of lines our terminal will render significantly.

{{% notice green "Bonus" "rocket" %}}
You can redirect the output from the `apt list` command directly into `less` by using the Bash Pipe operator (`|`). You would need to enter: `apt list | less`. This gives us the ability to manually scroll through the entire list. We will learn more about various Bash operators in a future article.
{{% /notice %}}

#### The Source of `apt list`

Everything is a file in Linux. So let's look for the source of the `apt list` command.

`sudo find /etc -name apt`

![sudo find /etc -name apt](pictures/find-etc-apt.png?classes=border)

Let's take a look inside the `/etc/apt` directory.

`ls /etc/apt`

![ls /etc/apt](pictures/ls-etc-apt.png?classes=border)

There's a few things here. But let's take a look at `/etc/apt/sources.list`.

`cat /etc/apt/sources.list`

![cat /etc/apt/sources.list](pictures/cat-etc-apt-sources.png?classes=border)

The `/etc/apt/sources.list` file contains some important statements that are directing the APT package manager on where to find the list of packages!

{{% notice note %}}
Many of the lines of this file are commented out with the number sign (`#`). Some of these are comments explaining the various sections, and some of them are alternate lines you could use instead. There's even an interesting section that reads: 
![uncomment for additional repositories](pictures/uncomment-for-additional-repositories.png?classes=border)
Additional repositories that can be easily added by uncommenting some lines! We won't be using any of the packages from that repository in this class, but feel free to follow the link to get an idea of the available packages.
{{% /notice %}}

#### User Added Repositories

If you were to add repositories outside of the base Ubuntu repositories you would do so in the `/etc/apt/sources.list.d` directory.

{{% notice note %}}
We will see an example of this in the Adding Additional Repositories section.
{{% /notice %}}

### Ubuntu Packages Website

Accessing the external documentation is **always** a good idea.

Trying to wrap our head around all of the package repositories on our machine is a daunting task.

Let's take a look at the [Ubuntu Packages Homepage](https://packages.ubuntu.com/).

It provides a list of various Ubuntu versions, we are using 20.04 the canonical name is `focal`.

{{% notice green "Bonus" "rocket" %}}
If you have forgotten your version of Ubuntu there are many ways to figure it out from your computer. There is a `lsb_release` command that displays distribution specific information. Try running `lsb_release -a` from your Bash shell:
![lsb_release -a](pictures/lsb-release-a.png?classes=border)
{{% /notice %}}

Upon looking at the [webpage for the `focal`](https://packages.ubuntu.com/focal/) repositories we can see they are organized by easier to digest sections.