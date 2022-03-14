---
title: "Updating the Ubuntu Display Size"
date: 2022-03-10T10:20:03-06:00
draft: false
weight: 1
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Updating the Ubuntu Display Size

From your Ubuntu Home screen:

![ubuntu home](pictures/ubuntu-home.png?classes=border)

Do an Activity search for `Displays`:

![Displays search](pictures/displays-search.png?classes=border)

Select the `Displays` option which will open up the Displays configuration window:

![Settings: Displays](pictures/settings-displays.png?classes=border)

Select `Resolution` and set it to a larger value than the default `800 x 600 (4:3)`. Be aware of your own monitor resolution. The monitor of the laptop I am using is `1920 x 1080 (16:9)` if I choose this option the new window will take up my entire monitor. I will use a smaller resolution, so I still have some monitor real estate.

I personally chose: `1360 x 768 (16:9)`:

![resolution dropdown](pictures/resolution-dropdown.png?classes=border)

After making your decision click the `Apply` button:

![apply button](pictures/apply-button.png?classes=border)

Upon clicking this button, two things will happen:

1. The window size of your VirtualBox will be automatically resized slightly larger than the resolution you chose.
1. Ubuntu will display a screen asking you to keep or revert the changes.

If you do not click the keep changes button, within the time frame, your resolution will be automatically reverted back to its original setting.

![confirm display setting](pictures/confirm-display.png?classes=border)

{{% notice note %}}
Ubuntu forces you to accept the changes manually because it is possible to configure your display in a way that would prohibit it from displaying information in a way you can understand it. For this reason, Ubuntu will automatically revert back to the original settings that it **knows** will work.
{{% /notice %}}

This change in Display resolution is stored within the machine. So next time you boot up this VirtualBox image it will automatically use the display resolution we just configured!

