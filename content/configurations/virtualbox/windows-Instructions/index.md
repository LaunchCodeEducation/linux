---
title: "Windows Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 15
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Windows Installation Instructions

#### Windows - Download

The direct link for the Windows VirtualBox download can be found [here](https://download.virtualbox.org/virtualbox/6.1.28/VirtualBox-6.1.28-147628-Win.exe)

{{% notice warning %}}
The link will start a download for the **.exe** file needed to install VirtualBox on a Windows system.
{{% /notice %}}

## Windows - Installation

### Run the .exe file

An executable file is a file with a predetermined set of instructions that our operating system will execute once we click it.

Double click the `.exe` file that we downloaded from the first step in this article. If you are having trouble locating the file it is more than likely located in your downloads folder. 

This will start the installation process for VirtualBox and open up the installation wizard. 

![virtualbox-windows-install-1](pictures/virtualbox-windows-install-1.png?classes=border)

### Setup Wizard

Once you have the wizard open hit the `Next` button.

![virtualbox-wizard-2](pictures/virtualbox-wizard-2.png?classes=border)

#### File Location and Structure

Next you will want to double check that your settings look similar to the image below. These are the default settings for the setup wizard and we will not be changing them. Click the `Next` button.

![virtualbox-wizard-location-3](pictures/virtualbox-wizard-location-3.png?classes=border)

#### Optional Settings

The next portion of the wizard will provide options for your installation including the following

- `Create start menu entries`
- `Create a shortcut on the desktop`
- `Create a shortcut in the Quick Launch Bar`
- `Register file associations`

For this setup walkthrough we will be leaving all of the above options selected and clicking the `Next` button.

![virtualbox-wizard-features-3](pictures/virtualbox-wizard-features-3.png?classes=border)
<!-- TODO: Decide whether or not we want to leave all options enabled or have the learner de-select all items. There is also the third option of letting them choose their own settings here -->

{{% notice note %}}
If you would prefer to unselect any of the above options based on personal preference that is okay.
{{% /notice %}}

#### Network Interfaces

In the following section we will install the VirtualBox Networking feature. Simply click the `Yes` button to continue.

{{% notice warning %}}
Once you click yes to install the VirtualBox networking feature your network connection will be lost temporarily.
{{% /notice %}}

![virtualbox-wizard-network-interfaces-4](pictures/virtualbox-wizard-network-interfaces-4.png?classes=border)

#### Ready to Install

The setup portion of this installation process has been completed. The next step is to begin the actual installation. Once you have the "Ready to Install" window open click the `Install` button.

![virtualbox-wizard-ready-install](pictures/virtualbox-wizard-ready-install-5.png?classes=border)

#### User Account Control

{{% notice bonus %}}
After clicking the `Install` button you should receive a windows notification bringing up a separate User Account Control window. This will ask you to allow VirtualBox to make changes to your device. We need to select `yes` or the install will fail.
{{% /notice %}}
<!-- TODO: Add picture of User Account Control Windows either from phone img or Virtualbox Windows Documentation -->

#### Windows Security Check
After allowing VirtualBox to make changes to your device you will be prompted once more asking if you would like to install the device software.

{{% notice note %}}
There is the option here to "Always trust software from "Oracle Corporation". It is your decision whether or not you would like to leave it selected or unselect that option. This will not have any effect on our installation process.
{{% /notice %}}

Click the `Install` button.

![virtualbox-security-notification-8](pictures/virtualbox-security-notification-8.png?classes=border)

Your installation will continue to complete. It will vary on how long it takes to finish the process.

![virtualbox-status-bar-7](pictures/virtualbox-status-bar-7.png?classes=border)

#### Installation Complete

Once your installation has complete you will have a window notification. This window will also allow us to open up VirtualBox after clicking the `Finish` button.

![virtualbox-wizard-complete-9](pictures/virtualbox-wizard-complete-9.png?classes=border)

{{% notice note %}}
You may receive a notification that a new version of VirtualBox is available. You can just click `ok` to close this message.
{{% /notice %}}

![virtualbox-new-version-10](pictures/virtualbox-new-version-10.png?classes=border&height=650px)

Now that our installation is complete we can open up VirtualBox. If you are having trouble locating VirtualBox it is in your `C:\Program Files\Oracle\VirtualBox\` directory.

![virtualbox-installation-complete](pictures/virtualbox-installation-complete.png?classes=border)
## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.