---
title: "Windows Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 2
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

### Run the executable file

An executable file is simply a file with a predetermined set of instructions that our operating system will execute once we click it.

Double click the `.exe` file that we downloaded from the first step in this article. If you are having trouble locating the file it is more than likely localted in your downloads folder.

![virtualbox-windows-install-1](pictures/virtualbox-windows-install-1.png?classes=border)

This will start the installation process for VirtualBox and open up the installation wizard. 
Once you have the wizard open hit the `Next` button.

![virtualbox-wizard-2](pictures/virtualbox-wizard-2.png?classes=border)

- Custom Setup Page
- Leave the default settings enabled on this page
<!-- TODO: Decide whether or not we want to leave all options enabled or have the learner de-select all items. There is also the third option of letting them choose their own settings here -->
- Click next

![virtualbox-wizard-location-3](pictures/virtualbox-wizard-location-3.png?classes=border)

- Network Interfaces

![virtualbox-wizard-network-interfaces-4](pictures/virtualbox-wizard-network-interfaces-4.png?classes=border)

{{% notice warning %}}
Once you click yes to install your network connection will be lost temporarily
{{% /notice %}}

- Click Yes
  - This will bring up a Ready to install notification

![virtualbox-wizard-ready-install](pictures/virtualbox-wizard-ready-install-5.png?classes=border)

- Click Install
  - This will bring up a User Account Control windows. This will ask you if you want to allow this app (VirtualBox) to make changes to your device. We need to select yes here or the install will fail.
<!-- TODO: Add picture of User Account Control Windows either from phone img or Virtualbox Windows Documentation -->
- Click Yes
- Your setup will continue. 
  - You will then be asked if you would like to install the device software
  - Leave the "Always trust software from "Oracle Corporation" selected
- Click Install

![virtualbox-security-notification-8](pictures/virtualbox-security-notification-8.png?classes=border)

- Installation Complete
- VirtualBox has finished the install process

![virtualbox-wizard-complete-9](pictures/virtualbox-wizard-complete-9.png?classes=border)

{{% notice note %}}
You may receive a notification that a new version of VirtualBox is available. You can just hit ok to close this message.
{{% /notice %}}

![virtualbox-new-version-10](pictures/virtualbox-new-version-10.png?classes=border&height=650px)

finally this is what you should see when everything has been installed properly and you open the program.
<!-- TODO: Grab photo of virtualbox open on windows -->

## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.