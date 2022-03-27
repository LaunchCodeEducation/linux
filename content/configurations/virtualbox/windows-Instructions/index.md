---
title: "Windows Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 105
originalAuthor: "John Woolbright" # to be set by page creator
originalAuthorGitHub: "jwoolbright23" # to be set by page creator
reviewer: "Paul Matthews" # to be set by the page reviewer
reviewerGitHub: "pdmxdd" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Windows Installation Instructions

#### Windows - Download

The direct link for the Windows VirtualBox download can be found [here](https://download.virtualbox.org/virtualbox/6.1.28/VirtualBox-6.1.28-147628-Win.exe)

{{% notice warning %}}
Upon clicking the link a download will begin of the **.exe** file needed to install VirtualBox on a Windows system.
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

For `File Location` we will be using the **default settings**.

Double check that your settings look similar to the image below. These are the **default settings** for the setup wizard and you should not change them. 

![virtualbox-wizard-location-3](pictures/virtualbox-wizard-location-3.png?classes=border)

After confirming, click the `Next` button.

#### Optional Settings

The next portion of the wizard will provide options for your installation including the following

- `Create start menu entries`
- `Create a shortcut on the desktop`
- `Create a shortcut in the Quick Launch Bar`
- `Register file associations`

For this configuration article we will be accepting all of the **default options** for the values listed above.

![virtualbox-wizard-features-3](pictures/virtualbox-wizard-features-3.png?classes=border)

After confirming your selections click the `Next` button.

{{% notice note %}}
If you feel strongly about not including a start menu, shortcut, quick launch shortcut, or registering file associations feel free to unselect the appropriate box. However all of the articles in this course assume you left the options with their default values.
{{% /notice %}}

#### Network Interfaces

In the following section we will install the VirtualBox Networking feature. 

{{% notice warning %}}
Once you click yes to install the VirtualBox networking feature your network connection will be lost temporarily. It goes down momentarily as it is being re-configured to allow any VirtualBox images to share access to your host OS configured network.
{{% /notice %}}

![virtualbox-wizard-network-interfaces-4](pictures/virtualbox-wizard-network-interfaces-4.png?classes=border)

Click the `Yes` button to continue.

#### Ready to Install

The setup portion of this installation process has been completed. The next step is to begin the actual installation. 

![virtualbox-wizard-ready-install](pictures/virtualbox-wizard-ready-install-5.png?classes=border)

Once you have the "Ready to Install" window open click the `Install` button.

#### User Account Control

{{% notice green "Bonus" "rocket" %}}
After clicking the `Install` button you should receive a windows notification bringing up a separate User Account Control window. This will ask you to allow VirtualBox to make changes to your device. We need to select `yes` or the install will fail.
<!-- TODO: picture here? -->
{{% /notice %}}

#### Windows Security Check

After allowing VirtualBox to make changes to your device you will be prompted once more asking if you would like to install the device software.

![virtualbox-security-notification-8](pictures/virtualbox-security-notification-8.png?classes=border)

{{% notice note %}}
The "Windows Security" window contains an option to "Always trust software from "Oracle Corporation". It is your decision whether or not you would like to leave it selected or unselect that option. This will not affect your installation process. For the purposes of this article we left the checkbox selected.
{{% /notice %}}

Click the `Install` button.

Upon clicking the `Install` button your installation will run the various files and scripts to complete the installation. It will take a few moments for the installation to complete.

![virtualbox-status-bar-7](pictures/virtualbox-status-bar-7.png?classes=border)

#### Finish Installation

Once your installation has complete you will have a window notification. This window will automatically open VirtualBox after clicking the `Finish` button.

![virtualbox-wizard-complete-9](pictures/virtualbox-wizard-complete-9.png?classes=border)

{{% notice note %}}
You may receive a notification that a new version of VirtualBox is available. You can just click `ok` to close this message.
{{% /notice %}}

## Validate Installation

Now that our installation is complete we can open up VirtualBox. If you are having trouble locating VirtualBox it is in your `C:\Program Files\Oracle\VirtualBox\` directory.

![virtualbox-installation-complete](pictures/virtualbox-installation-complete.png?classes=border)

{{% notice note %}}
You may see a popup window about a newer version of VirtualBox that is available. Click the `Ok` or `x` window button to close the popup.
![virtualbox-new-version-10](pictures/virtualbox-new-version-10.png?classes=border)
{{% /notice %}}

## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.