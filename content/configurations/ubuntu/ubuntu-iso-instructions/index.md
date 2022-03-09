---
title: "Ubuntu ISO Image Setup"
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Setting up the Virtual Machine to use our ISO Image

With the VirtualBox we just created selected, click the `settings wheel` icon.

![new-image-home](pictures/new-image-home.png?classes=border)

## Storage

Click on the `Storage Option` located on the left side of the menu

![settings-view](pictures/settings-view.png?classes=border)

### Storage View

After clicking the storage option it will bring up the following view:

![click-storage-tab](pictures/click-storage-tab.png?classes=border)

### Empty Attributes Section

Under Controller:IDE it says Empty. This is because we haven't told the machine which ISO to use for this Virtual Machine. Click on the `Empty` section below the Controller: IDE.

![empty-section-undercontrolleride-image](pictures/empty-section-undercontrolleride-image.png?classes=border)

### Optical Drive

On the right side under attributes you should now see an Optical Drive drop down, to the right of that is a disk icon button.
Click the `blue disc icon button` and it will bring up a couple of options:
  - `Choose/Create a Virtual Optical Disk...`
  - `Choose a disk file...`

Click on the `Choose a disk file...` option.

![CE-disk-icon-dropdown-image](pictures/CE-disk-icon-dropdown-image.png?classes=border)

<!-- TODO: Add image of Optical Drive populated with ubuntu ISO -->

## Selecting the Ubuntu ISO

Upon clicking `Choose a disk file` your host OS will open the default file manager. Using that file manager you need to select the `ubuntu-20.04.3-desktop-amd64.iso` file you downloaded earlier. 

{{% notice note %}}
The location of the `ubuntu-20.04.3-desktop-amd64.iso` will likely be in a different location than the example image posted below. The file is likely located in your downloads folder.
![personal-file-manager](pictures/personal-file-manager.png?classes=border)
This image is an example of the default file manager on a Pop!_OS which is an Ubuntu derived distribution.
{{% /notice %}}

#### Next Steps

After completing the above instructions please move on to the next portion of the installation process located in the article below:

[Start the Virtual Machine]({{< ref "../first-time-start/index.md" >}})