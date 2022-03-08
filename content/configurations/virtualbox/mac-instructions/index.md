---
title: "MacOS Installation"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 1
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

#### MacOS - Installing

- double click the .dmg file

![click-dmg-file](pictures/click-dmg-file.png?classes=border&height=650px)

- double lick the PKG file

![dbl-click-pkg-file](pictures/dbl-click-pkg-file.png?classes=border&height=650px)

- brings up an installer, click the allow button

![installer-allow-picture](pictures/installer-allow-picture.png?classes=border&height=650px)
- This will bring up the following tab
  - click continue

![form-continue-image](pictures/form-continue-image.png?classes=border&height=650px)

{{% notice note %}}
You may be thinking that you are missing an image for the destination select view. The installer should skip past this automatically. If it does not leave the settings as they are defaulted
{{% /notice %}}

- installation type

![change-install-location](pictures/change-install-location.png?classes=border&height=650px)

  - click install
  - might ask for password, click on the use password button and provide your credentials

![installer-password](pictures/installer-password.png?classes=border&height=650px)

- installation
  - it will take some time as it's running scripts

![running-package-scripts](pictures/running-package-scripts.png?classes=border&height=650px)

{{% notice note %}}
In the picture below you will notice that there is a System Extension Updated. This may pop up at a different time during your installation process.  You can click the open security preferences button and we will continue with those instructions later in this walkthrough.
{{% /notice %}}


![system-extention-individual](pictures/system-extension-individual.png?classes=border&height=650px)

- When you click the Open Security Prefences button it will bring up the following window. We are going to set this window aside until our installation is complete.

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)


{{% notice note %}}
Before moving forward with the security preferences section of this installation process please ensure that the installation was successful. This should be indicated through the installer and look similar to the image below
{{% /notice %}}

![installation-successful-image](pictures/installation-successful-image.png?classes=border&height=650px)

{{% notice warning %}}
Do not move forward with the below instructions until the installation process is complete! Please see above image and details for more information.
{{% /notice %}}

  - unlock security preferences by hitting the padlock icon in the bottom left corner

![security-preferences-menu](pictures/security-preferences-menu.png?classes=border&height=650px)

- Enter your password

![system-preferences-password](pictures/system-preferences-password.png?classes=border&height=650px)

  - click the allow button next to "System software from developer "Oracle America, Inc" has been updated

![allow-oracle-software](pictures/allow-oracle-software.png?classes=border&height=650px)

  - Hit the restart button and your machine will restart
{{% notice warning %}}
Do not restart your machine until the installation has been completed

{{% /notice %}}
![restart-required](pictures/restart-required.png?classes=border&height=650px)
- After your machine restarts you should find your VirtualBox.app within your applications folder. You can locate this by openning your finder and selecting the applications tab.
{{% notice bonus %}}

Alternatively you can find it by hitting command + spacebar and typing in the program name "VirtualBox.app"
{{% /notice %}}

- summary
- installation was successful and close


finally this is what you should see when everything has been installed properly and you open the program.

![virtualbox-app](pictures/virtualbox-app.png?classes=border&height=650px)

## Summary

In this article we downloaded and installed Oracle VirtualBox onto our host computers. In the next configuration article we will be using VirtualBox to create a virtual machine image of Ubuntu, which will be the Linux distribution used in this class.

Look over the [Ubuntu Configuration Article]({{< relref "../../ubuntu" >}}) to complete the configurations necessary for this course.