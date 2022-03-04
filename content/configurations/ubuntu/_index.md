---
title: "Ubuntu"
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

<!-- TODO: add note about having 15 GB free on their computer before performing the steps in this section -->

## Ubuntu

In this class we will be using Ubuntu Desktop 20.04.3 LTS, you can find it's download [on their website](https://ubuntu.com/download/desktop).

### Download Image

![Ubuntu Desktop Download Homepage](pictures/ubuntu-download-desktop.png)

Click the green `Download` button to start the download. It is a large file and will take some time.

You will likely have to confirm the download, in the picture below the user will need to click `Save File` for the file to be downloaded onto the host computer.

![Ubuntu Desktop Download Initiated Page](pictures/ubuntu-download.png)

Regardless of your host OS we will all be using a similar file `ubuntu-20.04.3-desktop-*.iso`. An `.iso` file is a Disk Image which is the instruction for installing an Operating System. We will be using this file inside of Virtualbox to create an isolated Ubuntu 20.04.3 virtual operating system inside of our host computer.
<<<<<<< HEAD
=======

### VirtualBox Ubuntu Image Creation Instructions

- Open VirtualBox

![VirtualBox Homescreen](pictures/virtualbox-home.png?classes=border)

- Within VirtualBox click the new  button

![Click new Button](pictures/click-new-button.png?classes=border)

{{% notice note %}}
If you have never used VirtualBox before, which is likely, you will be prompted by your host OS to give VirtualBox access to your files including your Downloads, and Documents directories.
![File-access-button](pictures/file-access-button.png?classes=border)
Make sure to grant VirtualBox permission to these locations!
{{% /notice %}}
<!-- TODO: get the file-access-button.png photo -->
- give it a name (student-VirtualBox) (it should automatically change type to linux)

![image-name](pictures/image-name.png?classes=border)

![image-type](pictures/image-type.png?classes=border)

![image-version](pictures/image-version.png?classes=border)

- machine folder leave as default (`/Users/username/VirtualBox` Vms
{{% notice note %}}
Your default location is dependent on your host operating system. If it is Mac it will be /Users/your-name, if you are on Windows it will be `C:\Users\username>`
{{% /notice %}}
- click next
- allocating the memory size
  - minimum: 2048
  - ideal: 3072 or greater

![image-memory](pictures/image-memory.png?classes=border)

- click next
- hard disk
  - create a virtual disc (click the blue create button)

![image-hard-disk](pictures/image-hard-disk.png?classes=border)

  - leave it on the default VDI

![image-hard-disk-type](pictures/image-hard-disk-type.png?classes=border)

  - storage on physical hard disk: select Fixed size

![image-hard-disk-fixed](pictures/image-hard-disk-fixed.png?classes=border)

  - file location and size
    - location: default
    - size: at least 12GB
    - click create

![image-hard-disk-size](pictures/image-disk-size.png?classes=border)

After completing the follow setup you will see the VirtualBox homepage that looks similar to:

![new-image-home](pictures/new-image-home.png?classes=border)

Using the picture above as a reference take note of the configurations for this specific image:

##### General

- Name: `student-VirtualBox`
- Operatating System: `Ubuntu (64 bit)`

##### System

- Base Memory: `2048 MB`

##### Storage

- Controller :IDE:
  - IDE Secondary Device 0: `[Optical Drive] Empty`
- Controller :Sata: 
  - SATA Port 0: `student-VirtualBox.vdi (Normal 12.00 GB)`

Take note of the IDE Secondary Device 0, this is referencing the CD drive of this specific image. It is currently empty, which makes sense, as we don't have a CD in our computer! In order to load Ubuntu we are going take the Ubuntu.iso image we downloaded earlier and virtually insert it into this optical drive. This will allow us to boot into Ubuntu and load it into this virtual image.

{{% notice note %}}
In this course will not be discussing the audio, network, usb, shared folders, or description.
{{% /notice %}}

#### setting up this machine to use our ISO image

![new-image-home](pictures/new-image-home.png?classes=border)

- settings wheel (while the name is selected)

![settings-view](pictures/settings-view.png?classes=border)

  - click the storage option

![click-storage-tab](pictures/click-storage-tab.png?classes=border)

  - under controller:IDE it says Empty (that's because we haven't told the machine which ISO to use for this machine)

![empty-section-undercontrolleride-image](pictures/empty-section-undercontrolleride-image.png?classes=border)

    - on the right side under attributes you should see optional drive drop down box, to the right of that is a disk icon button
    - click that button

![CE-disk-icon-dropdown-image](pictures/CE-disk-icon-dropdown-image.png?classes=border)

    - choose a disk file ...
      - file explorer (ISO)
      - most likely inside downloads (ubuntu-20.04.3-desktop-amd64.iso)
    - after you select the ISO file click the ok button

Upon clicking `Choose a disk file` your host OS will open the default file manager. Using that file manager you need to select the `ubuntu-20.04.3-desktop-amd64.iso` file you downloaded earlier. 

{{% notice note %}}
The location of the `ubuntu-20.04.3-desktop-amd64.iso` will likely be in a different location than the example image posted below. 
![personal-file-manager](pictures/personal-file-manager.png?classes=border)
This image is an example of the default file manager on a Pop!_OS which is an Ubuntu derived distribution.
{{% /notice %}}




#### starting the machine

![virtual-box-homepage](pictures/new-image-home.png?classes=border)

- click start button
{{% notice bonus %}}
You may notice the options within the dropdown next to the start arrow, the options are normal start, headless, detachable start. **During this course we will always be using the normal start. Without doing so you will not have access to the GUI.** To learn more about headless starts which are common, refer to the [Headless Software Wikipedia Article](https://en.wikipedia.org/wiki/Headless_software).
{{% /notice %}}

The first time you start your machine it will load the `.iso` file in the virtual optical drive, which will trigger a new installation of Ubuntu. As it is setting up this installation you will see quite a few different screens one of which will look similar to the following image:

![ubuntu-loading](pictures/ubuntu-loading.png?classes=border)

Once the installation wizard has finished setting up, you will see the following screen:

![ubuntu-loading-completed](pictures/ubuntu-loading-completed.png?classes=border)

{{% notice warning %}}
If the image is not set properly you will see the following errors (kernel drive not installed) and Failed to open a session for the virtual machine for ubuntu-launchcode
![error-output](pictures/error-output.png?classes=border)
If you see this error you misconfigured your ISO image. Please repeat the steps from the above section.
{{% /notice %}}


### Granting priveleges

{{% expand "Click here if you are working on MacOS for further instructions" %}}

#### granting your Macbook access to Oracle

- open settings
- click security & privacy
- unlock by clicking padlock and providing your password
- click allow for (System software from developer "Oracle America, Inc." was blocked from loading
- then restart your machine

- keystroke permission on Mac
- open system preferences
- unlock if necessary

![padlock-mac-security-picture](pictures/padlock-mac-security-picture.png?classes=border)

- select the checkbox for virtualbox

![virtualbox-checkbox](pictures/virtualbox-checkbox.png?classes=border)

- exit system preferences
- quit and reopen virtualbox

{{% /expand %}}

{{% expand "Click here if you are working on Windows for further instructions" %}}
<!-- TODO: Double check security permissions for windows OS -->
Content coming soon!
{{% /expand %}}

#### Installing Ubuntu (First Time Setup)

{{% notice warning %}}
For Macbook users, if you haven't granted oracle permissions in your security and privacy your machine will not start with a kernel error. If you see this error checkout the section on Granting your Macbook access to Oracle above.
{{% /notice %}}


- select your language (default is english)

![ubuntu-loading-completed](pictures/ubuntu-loading-completed.png?classes=border)

- click `Install Ubuntu` underneath the laptop icon
{{% notice warning %}}
Do not click "try ubuntu"
{{% /notice %}}

- keyboard layout (keep default, unless you use a non english keyboard)

![keyboard-layout-picture](pictures/keyboard-layout.png?classes=border)

- click continue
- select minimal installation
- select download updates while installing (accept all the defaults)

![updates-and-other-software](pictures/updates-and-other-software.png?classes=border)

- erase disk and install ubuntu (if it detected an OS that means they didn't select a VDI)

![installation-type-picture](pictures/installation-type.png?classes=border)

- click install now
- click continue
- select your TZ (should default accurately)

![erase-disk-and-install-ubuntu](pictures/erase-disk-and-install-ubuntu.png?classes=border)

click `Install Now`

![erase-disk-popup](pictures/erase-disk-popup.png?classes=border)

click `Continue`

![tz-select-picture](pictures/tz-select.png?classes=border)

- who are you?

![who-are-you-picture](pictures/who-are-you-blank.png?classes=border)
  - your name: `student`
  - your computer's name: `student-VirtualBox`
  - username: `student`
  - password: `admin`
  - confirm: `admin`
  - select: `require my password to log in (default)`
  - click: `Continue`

![who-are-you-filled](pictures/who-are-you-filled.png?classes=border)

![installing-system](pictures/installing-system.png?classes=border)

![installing-system-final](pictures/installation-complete-popup.png?classes=border)

![loading-screen-to-home](pictures/loading-screen-to-home.png?classes=border)

![after-restart](pictures/after-restart.png?classes=border)

![user-login](pictures/user-login.png?classes=border)

![user-login-password](pictures/user-login-password.png?classes=border)

![first-time-login](pictures/first-time-login.png?classes=border)

![click-through-1](pictures/click-through-1.png?classes=border)

![click-through-2](pictures/click-through-2.png?classes=border)

![click-through-3](pictures/click-through-3.png?classes=border)

![click-through-4](pictures/click-through-4.png?classes=border)

![software-updater](pictures/software-updater.png?classes=border)

![ubuntu-desktop](pictures/ubuntu-desktop.png?classes=border)
>>>>>>> fixed spacing around photos
