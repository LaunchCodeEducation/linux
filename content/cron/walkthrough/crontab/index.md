---
title: "Crontab"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 105
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Usage

```bash
crontab -e
```
- Commands:
  - `crontab <filename>`: command to run cron-jobs within a separate file as an argument
  - `crontab -e`: edit user's crontab
  - `crontab -l`: list user's crontab
  - `crontab -r`: delete user's crontab
  - `crontab -i`: prompt before deleting user's crontab

{{% notice green "Bonus" "rocket" %}}
You can also open the global crontab config file with the following command: `sudo vim /etc/crontab`. For the global crontab config file you will have to designate what user this command will be running for. `* * * * * user-name command-to-run`.
![global-crontab](pictures/global-crontab.png?classes=border)
{{% /notice %}}