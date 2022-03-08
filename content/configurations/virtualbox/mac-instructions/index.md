---
title: "MacOS Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
<<<<<<< HEAD
weight: 10
=======
weight: 1
>>>>>>> configurations/virtualbox
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

<<<<<<< HEAD
<<<<<<< HEAD
## MacOS Installation

### Run the .dmg file

A `.dmg` file is an Apple Disk Image file. This is often the type of file used to store software installers.

Double click the `.dmg` file that we downloaded from the first step in this article. If you are having trouble locating the file it is more than likely located in your downloads folder.

![click-dmg-file](pictures/click-dmg-file.png?classes=border&height=650px)

### Start the Installation

Once you open the `.dmg` file you will have a new window pop up on your screen. We want to double click the `VirtualBox.pkg` file. This will open up the VirtualBox installer window.

![dbl-click-pkg-file](pictures/dbl-click-pkg-file.png?classes=border&height=650px)

## VirtualBox Installer

Once the installer has started we will be prompted to allow the `VirtualBox.pkg` file to run. Click the `Allow` button.

![installer-allow-picture](pictures/installer-allow-picture.png?classes=border&height=650px)

### Introduction

After clicking the allow button you will find a brief overview of the installation process and what VirtualBox is capable of. After reading through the description click the `continue` button.
=======
#### MacOS - Installing
=======
## MacOS Installation
>>>>>>> configurations/virtualbox

### Run the .dmg file

A `.dmg` file is an Apple Disk Image file. This is often the type of file used to store software installers.

Double click the `.dmg` file that we downloaded from the first step in this article. If you are having trouble locating the file it is more than likely located in your downloads folder.

![click-dmg-file](pictures/click-dmg-file.png?classes=border&height=650px)

### Start the Installation

Once you open the `.dmg` file you will have a new window pop up on your screen. We want to double click the `VirtualBox.pkg` file. This will open up the VirtualBox installer window.

![dbl-click-pkg-file](pictures/dbl-click-pkg-file.png?classes=border&height=650px)

## VirtualBox Installer

Once the installer has started we will be prompted to allow the `VirtualBox.pkg` file to run. Click the `Allow` button.

![installer-allow-picture](pictures/installer-allow-picture.png?classes=border&height=650px)
<<<<<<< HEAD
- This will bring up the following tab
  - click continue
>>>>>>> configurations/virtualbox
=======

### Introduction

After clicking the allow button you will find a brief overview of the installation process and what VirtualBox is capable of. After reading through the description click the `continue` button.
>>>>>>> configurations/virtualbox

![form-continue-image](pictures/form-continue-image.png?classes=border&height=650px)

{{% notice note %}}
<<<<<<< HEAD
<<<<<<< HEAD
You may be thinking that you are missing an image for the destination select view. The installer should skip past this automatically. If it does not leave the settings as they are defaulted.
{{% /notice %}}

### Installation Type

We will be using the standard installation of VirtualBox for this walkthrough. This is the default type of installation. Click the `Install` button.

![change-install-location](pictures/change-install-location.png?classes=border&height=650px)

### Installer Credentials

You might receive a notification that your installer is trying to install new software. Click on the `Use Password...` button and provide your credentials to continue our installation process.

![installer-password](pictures/installer-password.png?classes=border&height=650px)

### Installation

The installer will now run the scripts included within the `VirtualBox.pkg` file. This may take a little bit of time.

![running-package-scripts](pictures/running-package-scripts.png?classes=border&height=650px)

{{% notice warning %}}
In the picture below you will notice that there has been a System Extension Updated. This may pop up at a different time during your installation process. You can click the `Open Security Preferences Button` and we will continue with those instructions later in this walkthrough.
{{% /notice %}}

![system-extention-individual](pictures/system-extension-individual.png?classes=border&height=650px)

### Security & Privacy

When you click the Open Security Prefences button it will bring up the following window. As mentioned in the warning above we are going to set this window aside until our installation is complete.

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)

{{% notice warning %}}
Before moving forward with the security preferences section of this installation process please ensure that the installation was successful. This should be indicated through the installer and look similar to the image below
{{% /notice %}}

After the installation is successful you can click the `close` button.

=======
You may be thinking that you are missing an image for the destination select view. The installer should skip past this automatically. If it does not leave the settings as they are defaulted
=======
You may be thinking that you are missing an image for the destination select view. The installer should skip past this automatically. If it does not leave the settings as they are defaulted.
>>>>>>> configurations/virtualbox
{{% /notice %}}

### Installation Type

We will be using the standard installation of VirtualBox for this walkthrough. This is the default type of installation. Click the `Install` button.

![change-install-location](pictures/change-install-location.png?classes=border&height=650px)

### Installer Credentials

You might receive a notification that your installer is trying to install new software. Click on the `Use Password...` button and provide your credentials to continue our installation process.

![installer-password](pictures/installer-password.png?classes=border&height=650px)

### Installation

The installer will now run the scripts included within the `VirtualBox.pkg` file. This may take a little bit of time.

![running-package-scripts](pictures/running-package-scripts.png?classes=border&height=650px)

{{% notice note %}}
In the picture below you will notice that there has been a System Extension Updated. This may pop up at a different time during your installation process.  You can click the open security preferences button and we will continue with those instructions later in this walkthrough.
{{% /notice %}}


![system-extention-individual](pictures/system-extension-individual.png?classes=border&height=650px)

### Security & Privacy

When you click the Open Security Prefences button it will bring up the following window. We are going to set this window aside until our installation is complete.

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)


{{% notice note %}}
Before moving forward with the security preferences section of this installation process please ensure that the installation was successful. This should be indicated through the installer and look similar to the image below
{{% /notice %}}

>>>>>>> configurations/virtualbox
![installation-successful-image](pictures/installation-successful-image.png?classes=border&height=650px)

{{% notice warning %}}
Do not move forward with the below instructions until the installation process is complete! Please see above image and details for more information.
{{% /notice %}}

<<<<<<< HEAD
<<<<<<< HEAD
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
=======
  - unlock security preferences by hitting the padlock icon in the bottom left corner
=======
To make the required changes to our Security & Privacy we will need to unlock the security preferences by hitting the padlock icon in the bottom left corner. This will ask you to enter your password. Please provide your credentials.
>>>>>>> configurations/virtualbox

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)

![system-preferences-password](pictures/system-preferences-password.png?classes=border&height=650px)

Once you have entered your password you will see a "System software from developer "Oracle America, Inc" has been updated towards the bottom of your settings window.

![allow-oracle-software](pictures/allow-oracle-software.png?classes=border&height=650px)

After clicking the allow button you will be prompted to restart your machine. If the VirtualBox installation has been completed click the `Restart` button.

{{% notice warning %}}
Do not restart your machine until the installation has been completed
{{% /notice %}}

![restart-required](pictures/restart-required.png?classes=border&height=650px)

## Installation Complete

After your machine restarts you should find your VirtualBox.app within your applications folder. You can locate this by opening your finder and selecting the applications tab.

{{% notice bonus %}}
Alternatively you can find it by hitting command + spacebar and typing in the program name "VirtualBox.app"
{{% /notice %}}

<<<<<<< HEAD
finally this is what you should see when everything has been installed properly and you open the program.
>>>>>>> configurations/virtualbox
=======
When you open your VirtualBox application this is what you should see when you open the program.
>>>>>>> configurations/virtualbox

![virtualbox-app](pictures/virtualbox-app.png?classes=border&height=650px)

## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.