---
title: "VirtualBox Image Creation"
draft: false
weight: 10
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## VirtualBox Ubuntu Image Creation Instructions

Before we can create the Ubuntu Image and machine we need to open VirtualBox.

### Open VirtualBox

Open VirtualBox the same way you would open any software. Once it is open you should be greeted by the VirtualBox Manager Window:

![VirtualBox Manager Window](pictures/virtualbox-home.png?classes=border)

#### Create a New Virtual Machine

In the VirtualBox Manager Window click the `New` button. Its icon is the blue spiky icon.

After clicking the `New` button you will see the wizard that will guide you through creating a new Virtual Machine:

![Click new Button](pictures/click-new-button.png?classes=border)

{{% notice note %}}
If you have never used VirtualBox before, which is likely, you will be prompted by your host OS to give VirtualBox access to your files including your Downloads, and Documents directories.
Make sure to grant VirtualBox permission to these locations!
{{% /notice %}}

We need to configure all of the components on the first page of this wizard. We will be configuring Name, Type, and OS version.

#### Virtual Machine Name

In the Name textbox enter `student-VirtualBox`:

![image-name](pictures/image-name.png?classes=border)

#### Virtual Machine Type

In the Type dropdown select `Linux` from the dropdown box:

![image-type](pictures/image-type.png?classes=border)

#### Virtual Machine OS Version

In the Version dropdown select `Ubuntu (64 bit)`:

![image-version](pictures/image-version.png?classes=border)

After entering all three of the preceding components click the `Next` button.

{{% notice note %}}
We will not be **changing the default value** on the `Machine Folder` component. Your default location is dependent on your host opearating system. For a MacOS it will be similar to `/Users/user-name`. For a Windows OS it will be similar to `C:\Users\user-name`.
{{% /notice %}}


#### Virtual Machine Memory Size

We need to configure the amount of RAM this Virtual Machine has access to. Your host computer has a certain amount of RAM, we cannot give all of the RAM to the Virtual Machine because your host computer still needs access to some of the memory.

For this step we will be entering `2048` (2 GB) into the only textbox on this window:

![image-memory](pictures/image-memory.png?classes=border)

{{% notice note %}}
You could also use the slider bar to configure the amount of RAM to provide to the Virtual Machine. We don't recommend this, because it's difficult to be precise. Make sure to provide at least 2048 MB of RAM.
{{% /notice %}}

After entering `2048` into the textbox click the `Next` button.

#### Virtual Machine Hard Disk

Similar to the RAM of our Virtual Machine we need to provide a certain amount of hard disk space from the Host operating system. However, this hard disk space needs to be formatting in a way that allows for an operating system to function.

Luckily, VirtualBox will perform this formatting for us after we finish this wizard.

##### Create a Virtual Hard Disk

We will be creating a new VirtualBox managed virtual hard disk.

Leave the first setting on the default value `Create a virtual hard disk now`.

Click the `Create` button.

![image-hard-disk](pictures/image-hard-disk.png?classes=border)


##### Select Hard Disk Type

We will be using the VirtualBox preferred `VDI (VirtualBox Disk Image)` which should be the default value.

After confirming the `VDI` option click `Next`.

![image-hard-disk-type](pictures/image-hard-disk-type.png?classes=border)

##### Fixed or Dynamic Hard Disk

VirtualBox allows you to dynamically add more space to your Hard Disk. However, this slows down the entire Virtual Machine because of the flexible nature of the hard disk size.

For this reason we will be using the `Fixed size` for our virtual hard disk.

After selecting the `Fixed size` option click `Next`.

![image-hard-disk-fixed](pictures/image-hard-disk-fixed.png?classes=border)

{{% notice note %}}
If you are creating your own personal Virtual Machine after this class, you may want to use a dynamically sized hard disk. This will offer you more flexibility with regards to your hard disk usage.
{{% /notice %}}

##### File Location and Size

The file location for the VirtualBox you will leave as the default value. You will however want to adjust the size of the virtual hard disk. The default value is `10.00 GB`. You should change this to `12.00 GB` as shown in the image below.

![image-hard-disk-size](pictures/image-disk-size.png?classes=border)

##### VirtualBox Manager Homepage

After completing the above setup you will see the VirtualBox homepage that looks similar to the following image:

![new-image-home](pictures/new-image-home.png?classes=border)


### Review

Using the picture above as a reference take note of the configurations for this specific image:

#### General

- Name: `student-VirtualBox`
- Operatating System: `Ubuntu (64 bit)`

#### System

- Base Memory: `2048 MB`

#### Storage

- Controller :IDE:
  - IDE Secondary Device 0: `[Optical Drive] Empty`
- Controller :Sata: 
  - SATA Port 0: `student-VirtualBox.vdi (Normal 12.00 GB)`

Take note of the IDE Secondary Device 0, this is referencing the CD drive of this specific image. It is currently empty, which makes sense, as we don't have a CD in our computer! In order to load Ubuntu we are going take the Ubuntu.iso image we downloaded earlier and virtually insert it into this optical drive. This will allow us to boot into Ubuntu and load it into this virtual image.

{{% notice note %}}
In this course will not be discussing the audio, network, usb, shared folders, or description.
{{% /notice %}}

#### Next Steps

After completing the above instructions please move on to the next portion of the installation process located in the article below:

[Ubuntu ISO Image Setup]({{< ref "../ubuntu-iso-instructions/index.md" >}})