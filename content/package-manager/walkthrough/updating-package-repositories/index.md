---
title: "Updating Package Repositories"
date: 2021-11-09T15:13:39-06:00
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

`apt update`

From Man page:
```bash
update is used to download package information from all configured
           sources. Other commands operate on this data to e.g. perform
           package upgrades or search in and display details about all
           packages available for installation.
```

{{% notice note %}}
When entering `apt update` you may want to include the `-y` option will aut
{{% /notice %}}