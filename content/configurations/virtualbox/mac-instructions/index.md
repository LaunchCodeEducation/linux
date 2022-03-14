---
title: "MacOS Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 10
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## MacOS Installation Instructions

#### MacOS - Download

The direct link for the MacOS VirtualBox download can be found [here](https://download.virtualbox.org/virtualbox/6.1.28/VirtualBox-6.1.28-147628-OSX.dmg).

{{% notice warning %}}
The link will start a download for the **.dmg** file needed to install VirtualBox on a MacOS system.
{{% /notice %}}

## MacOS Installation

### Run the .dmg file

A `.dmg` file is an Apple Disk Image file. Apple commonly uses this type of file (`.dmg`) to store software installers.

Double click the `.dmg` file that we downloaded from the first step in this article. 

{{% notice note %}}
If you are having trouble locating the downloaded `.dmg` file it is more than likely located in your downloads folder.
{{% /notice %}}

![click-dmg-file](pictures/click-dmg-file.png?classes=border&height=650px)

### Start the Installation

Once you open the `.dmg` file a new window will pop up on your screen. You will need to double click the `VirtualBox.pkg` file. This will open up the VirtualBox installer window.

![dbl-click-pkg-file](pictures/dbl-click-pkg-file.png?classes=border&height=650px)

## VirtualBox Installer

Once the installer has started you will be prompted to allow the `VirtualBox.pkg` file to run. Click the `Allow` button.

![installer-allow-picture](pictures/installer-allow-picture.png?classes=border&height=650px)

### Introduction

After clicking the allow button you will find a brief overview of the installation process and what VirtualBox is capable of. After reading through the description click the `continue` button.

![form-continue-image](pictures/form-continue-image.png?classes=border&height=650px)

{{% notice note %}}
Take note that the installer skips past the `Destination Select` screen. VirtualBox changed how you can specify the installation location, but left the option on the installer. This article uses the default installation location. **If you are ever prompted to change, or select an installation location leave it on the default option**. At the time of creating this article the installation location was hidden behind the `Change Install Location...` button. You can see this button in the following images. This article will not even click the button as we want the default location.
{{% /notice %}}

### Installation Type

You will be using the standard installation of VirtualBox for this walkthrough. This is the default type of installation. Click the `Install` button.

![change-install-location](pictures/change-install-location.png?classes=border&height=650px)

### Installer Credentials

You might receive a notification that your installer is trying to install new software. Click on the `Use Password...` button and provide your credentials to continue our installation process.

![installer-password](pictures/installer-password.png?classes=border&height=650px)

### Installation

The installer will now run the scripts included within the `VirtualBox.pkg` file. This may take a few seconds.

![running-package-scripts](pictures/running-package-scripts.png?classes=border&height=650px)

{{% notice warning %}}
In the picture below you will notice that there has been a System Extension Updated. **The System Extension Updated may pop up at a different time during your installation process. Whenever the System Extension Updated window pops ups click the `Open Security Preferences` button and set it to the side.** We will continue with those instructions after finishing the installation. When you see the following image click the `Open Security Preferences` button and set the resulting window to the side.
![system-extention-individual](pictures/system-extension-individual.png?classes=border&height=650px)
{{% /notice %}}


### Security & Privacy

When you click the Open Security Preferences button it will bring up the following window. As mentioned in the warning above we are going to set this window aside until our installation is complete.

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)

{{% notice warning %}}
Before moving forward with the security preferences section of this installation process **ensure that the installation was successful**. This should be indicated through the installer and look similar to the image below.
![installation-successful-image](pictures/installation-successful-image.png?classes=border&height=650px)
{{% /notice %}}

**After the installation is successful you can click the `close` button.**



{{% notice warning %}}
Do not move forward with the below instructions until the installation process is complete! Please see above image and details for more information.
{{% /notice %}}

To make the required changes to our Security & Privacy we will need to unlock the security preferences by clicking the `padlock icon` in the bottom left corner. This will ask you to enter your password. Please provide your credentials.

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)

![system-preferences-password](pictures/system-preferences-password.png?classes=border&height=650px)

Once you have entered your password you will see a "System software from developer "Oracle America, Inc" has been updated towards the bottom of your Security & Privacy window. Click the `Allow` button.

![allow-oracle-software](pictures/allow-oracle-software.png?classes=border&height=650px)

After clicking the allow button you will be prompted to restart your machine. If the VirtualBox installation has been completed you can click the `Restart` button.

{{% notice warning %}}
Do not restart your machine until the installation has been completed
{{% /notice %}}

![restart-required](pictures/restart-required.png?classes=border&height=650px)

## Installation Complete

After your machine restarts you should find your VirtualBox.app within your applications folder. You can locate this by opening your finder and selecting the applications tab.

{{% notice bonus %}}
Alternatively you can find the VirtualBox.app by hitting command + spacebar and typing in the program name "VirtualBox.app"
{{% /notice %}}

When you open your VirtualBox application this is what you should see when you open the program.

![virtualbox-app](pictures/virtualbox-app.png?classes=border&height=650px)

## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.