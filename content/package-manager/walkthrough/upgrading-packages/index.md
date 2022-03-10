---
title: "Upgrading Packages"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 7
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Upgrading Packages

Overtime the packages on your system will need to be upgraded to new versions. All of the packages on your system are maintained by individuals and they may be:

- adding new features
- fixing bugs
- patching vulnerabilities
- optimizing runtime or spacetime complexities

You will most certainly want the security patches and bug fixes, and having the newest features and most optimized version of the package is always nice.

How do we upgrade packages?

From the bash shell using the `apt` CLI `upgrade` command of course!

## `sudo apt upgrade`

Let's take a look at the `upgrade` command definition from the `apt` CLI Manual Reference page:

```bash
upgrade (apt-get(8))
           upgrade is used to install available upgrades of all packages
           currently installed on the system from the sources configured via
           sources.list(5). New packages will be installed if required to
           satisfy dependencies, but existing packages will never be removed.
           If an upgrade for a package requires the removal of an installed
           package the upgrade for this package isn't performed.
```

So the `upgrade` command will upgrade **all** currently installed packages in one fell swoop. It may take it some time to perform this action depending on how many packages needs to be upgraded.

{{% notice note %}}
If you want to see all the currently installed packages that have available upgrades run: `apt list --upgradeable`:
![apt list --upgradeable](pictures/apt-list-upgradeable.png?classes=border)
There are plenty to choose from.
{{% /notice %}}

Let's try out the `upgrade` command.

## `sudo apt upgrade`

Enter `sudo apt upgrade`:

![sudo apt upgrade confirm](pictures/apt-upgrade-confirm.png?classes=border)

And then confirm that we do want to upgrade **all** packages by entering `y` or hitting `enter`.

![sudo apt upgrade](pictures/apt-upgrade.png?classes=border)

Understandably, it took some time to perform the `apt upgrade` command. If you scroll the Bash shell display (STDOUT) you will see many lines describing the actions that were performed as a part of this command.

However, our distribution has been fully upgraded. Since all of our packages have been installed and managed through the `apt` CLI when we upgrade **all** installed packages we are performing a full upgrade of our Distribution!

{{% notice bonus %}}
You could run `sudo apt update -y` and `apt list --upgradeable` again to see if there are any available new package upgrades since we just upgraded. In my case there were a couple of additional package upgrades:
![small apt list --upgradeable](pictures/small-apt-list-upgradeable.png?classes=border)
However, this is a much smaller list than the 100+ I had earlier. And there's nothing stopping me from running `sudo apt upgrade` again!
{{% /notice %}}