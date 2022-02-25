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

`apt upgrade`

From man page:

```bash
upgrade (apt-get(8))
           upgrade is used to install available upgrades of all packages
           currently installed on the system from the sources configured via
           sources.list(5). New packages will be installed if required to
           satisfy dependencies, but existing packages will never be removed.
           If an upgrade for a package requires the removal of an installed
           package the upgrade for this package isn't performed.
```

`apt upgrade -y`