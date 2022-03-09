---
title: "Start the Virtual Machine"
draft: false
weight: 3
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Starting the Virtual Machine

Within the VirtualBox Manager, click on the newly created VirtualBox so that it is highlighted and then click the green `Start` button.

![virtual-box-homepage](pictures/new-image-home.png?classes=border)

{{% notice bonus %}}
You may notice the options within the dropdown next to the start arrow, the options are normal start, headless, and detachable start. **During this course we will always be using the normal start. Without doing so you will not have access to the GUI.** To learn more about headless starts which are common, refer to the [Headless Software Wikipedia Article](https://en.wikipedia.org/wiki/Headless_software).
{{% /notice %}}

### First Time Start
The first time you start your machine it will load the `.iso` file in the virtual optical drive, which will trigger a new installation of Ubuntu. As it is setting up this installation you will see quite a few different screens, one of which will look similar to the following image:

![ubuntu-loading](pictures/ubuntu-loading.png?classes=border)

### Possible Install Error
{{% notice warning %}}
If the image is not set properly you will see the following error when you try to start the Virtual Machine:
**If you see this error you misconfigured your ISO image.** Please repeat the steps from the above section.
![kernel-driver-error-output](pictures/kernel-driver-error-output.png?classes=border)
{{% /notice %}}

## Installing Ubuntu (First Time Setup)

- Once the installation wizard has finished setting up, you will see the following screen:

- Select your language (default is english)

- After selecting the the language click the `Install Ubuntu` button underneath the laptop icon

{{% notice warning %}}
Do not click "try ubuntu"
{{% /notice %}}

![ubuntu-loading-completed](pictures/ubuntu-loading-completed.png?classes=border)

### Keyboard Layout

Select your Keyboard layout (keep default, unless you use a non english keyboard) and click `continue`.

![keyboard-layout-picture](pictures/keyboard-layout.png?classes=border)

### Updates and other Software

Select the `Minimal installation`. This will lower the amount of space taken up by software we do not need on the Virtual Machine.

Select `Download updates while installing Ubuntu`. As it mentions this will save time after installation.

Click `Continue`.

![installation-type-picture](pictures/installation-type.png?classes=border)

### Installation Type

For the Installation type you should select `Erase disk and install Ubuntu`.

{{% notice note %}}
If you can see that an Operating System has been detected that means you did not select `VDI (Virtual Disk Image)` in the **Virtaul Machine Hard Disk** portion of this setup. If this is the case you will need to recreate your Virtual Machine.
{{% /notice %}}

Click the `Install Now` button.

![erase-disk-and-install-ubuntu](pictures/erase-disk-and-install-ubuntu.png?classes=border)

### Write Changes to Disks

This popup is notifying us of the changes we are making to the Virtual Disk Image. Click the `Continue` button.

![erase-disk-popup](pictures/erase-disk-popup.png?classes=border)

### Selecting your Timezone

Select your Timezone (this option should default automatically).

Click the `Continue` button.

![tz-select-picture](pictures/tz-select.png?classes=border)

### Who are you?

This is where you will give your operating system user settings. You will use the following settings:
  - Your name: `student`
  - Your computer's name: `student-VirtualBox`
  - Pick a username: `student`
  - Choose a password: `admin`
  - Confirm your password: `admin`
  - select: `require my password to log in (default)`

![who-are-you-picture](pictures/who-are-you-blank.png?classes=border)

#### User Settings Review

After you review your settings and all form fields are filled out click the `Continue` button.

![who-are-you-filled](pictures/who-are-you-filled.png?classes=border)

## Welcome to Ubuntu

The setup for your Virtual Machine with a Ubuntu operating system is now complete. All that is left is to do is let the operating system finish its own configuration and log in!

![installing-system](pictures/installing-system.png?classes=border)

### Installation Complete

Once you receive a notification that the installation is complete you can click the `Restart Now` button.

![installing-system-final](pictures/installation-complete-popup.png?classes=border)

### System Restart

After clicking the restart now button your operating system will restart and you should see something similar to the image below:

![loading-screen-to-home](pictures/loading-screen-to-home.png?classes=border)

### Installation Medium

You will notice that it is asking you to remove the installation medium and then press enter. The virtual machine thinks that the medium used to install Ubuntu is an optical CD drive. However there is no such drive. 

You can press the `enter` key when you reach this page.

![after-restart](pictures/after-restart.png?classes=border)

{{% notice note %}}
Often times when someone is installing Ubuntu or any other Linux distribution on a new machine they will use a USB drive or CD. Once the operating system has been installed it asks that you remove the installation medium (the USB drive) so that it wont ever reboot or start up and go into installation mode again.
{{% /notice %}}

### User Login

Once you reach the user login page you can hit the `enter` key or click `student` to login.

![user-login](pictures/user-login.png?classes=border)

### User Password

Enter your password. If you followed the steps above during the user account creation the password is `admin`.

![user-login-password](pictures/user-login-password.png?classes=border)

### Optional Settings

You will now be prompted with some first time start up optional settings. You will have to click past these options since it is the first time you have logged in.

Click the `Skip` button.

![first-time-login](pictures/first-time-login.png?classes=border)

### Livepatch

Click `Next`

![click-through-1](pictures/click-through-1.png?classes=border)

### Help improve Ubuntu

Click `Next`

![click-through-2](pictures/click-through-2.png?classes=border)

### Privacy

Click `Next`

![click-through-3](pictures/click-through-3.png?classes=border)

### You're ready to go!

And lastly click `Done`

![click-through-4](pictures/click-through-4.png?classes=border)

### Software Update

You will most likely receive a notification at this point that there is updated software available. Best practice is to update your operating system whenever their is a new version available. You can click the `Install Now` button in order to install the updated software.

![software-updater](pictures/software-updater.png?classes=border)

### Ubuntu Desktop

You have reached the Ubuntu Desktop!

![ubuntu-desktop](pictures/ubuntu-desktop.png?classes=border)