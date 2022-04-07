---
title: "Create a Cronjob"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Example cronjob within crontab:

Open up your crontab config file and add the following cronjob command:

```bash
* * * * * echo "$(date)" >> ~/Desktop/time.log
```

Run the command: `crontab -e`:

![crontab-time-log](pictures/crontab-time-log.png?classes=border)

Add the cronjob to the config file: