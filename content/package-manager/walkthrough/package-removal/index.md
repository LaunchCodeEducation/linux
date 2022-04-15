---
title: "Removing Packages"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 130
---

## Removing Packages

You can remove a currently installed package with the `apt remove [package-name]` command.

Let's remove the packages we installed in the installation article.

## `apt remove vim`

Check that Vim is installed by entering: `which vim`:

![which vim](pictures/which-vim.png?classes=border)

Now remove the Vim package by entering: `sudo apt remove vim`:

![sudo apt remove vim](pictures/apt-remove-vim-confirm.png?classes=border)

Confirm the Vim package removal by entering `Y` (or simply hitting enter):

![sudo apt remove vim](pictures/apt-remove-vim.png?classes=border)

Since there wasn't a display message about the package being removed enter: `which vim`:

![empty which vim](pictures/empty-which-vim.png?classes=border)

The Vim package is gone!

## `apt remove gimp`

Now let's remove the GIMP package following the same steps.

Confirm it's existence: `which gimp`

![which gimp](pictures/which-gimp.png?classes=border)

Remove the GIMP package with the auto confirm flag: `sudo apt remove gimp -y`

![sudo apt remove gimp -y](pictures/apt-remove-gimp-y.png?classes=border)

Check for the package: `which gimp`

![empty which gimp](pictures/empty-which-gimp.png?classes=border)

And it's gone!

## `apt autoremove`

The `apt` CLI also provides an `autoremove` command.

Let's take a look at what this command does by searching the `apt` Manual Reference for the `autoremove` command. It may take a second to manually find it, so we provided a picture of the information:

![man apt autoremove](pictures/man-apt-autoremove.png?classes=border)

Pretty clearly this tool states that it will automatically remove packages that are no longer needed as dependencies to other packages.

As packages are maintained and features added they sometimes will change their package dependencies. The `apt autoremove` command will automatically find any packages that are currently installed as dependencies to other packages and remove them.

In fact if you take another look at the display message when you removed the GIMP package there was a message about running `apt autoremove`. Let's look at the picture again:

![sudo apt remove gimp -y](pictures/apt-remove-gimp-y.png?classes=border)

The output is clipped, but it's a large list of packages that are listed as dependencies for the GIMP package. At the very end of the list there is a statement `Use 'sudo apt autoremove' to remove them.`. This statement is telling us that when we removed the GIMP package there are still packages on this machine that were installed as dependencies for the GIMP package.

However, you can remove them and free up space on this machine by simply running `sudo apt autoremove`.

Give it a try: `sudo apt autoremove`

![sudo apt autoremove confirm](pictures/apt-autoremove-confirm.png?classes=border)

Clearly listed are all of the packages that will be removed since they are all flagged as dependencies and the packages that used them as dependencies have since been removed, or no longer require these dependencies.

These packages are doing nothing for you so enter `y` to have the `apt` CLI remove them:

![sudo apt autoremove](pictures/apt-autoremove.png?classes=border)

That's a lot of remove statements in the bash shell output (STDOUT).