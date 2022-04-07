---
title: "Walkthrough"
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

## Name

> Cron - daemon to execute scheduled commands

## Purpose

Fire off a command at the exact time you wish and to repeat as often as you would like.
- Time interval options:
  - `minute`
  - `hour`
  - `day-of-month`
  - `month`
  - `day-of-week`

## Usage

```bash
crontab -e
```
- Commands:
  - `crontab <filename>`: command to run cron-jobs within a separate file as an argument
  - `crontab -e`: open current user  crontab file
  - `crontab -l`: list of all cronjobs within the current user crontab file
  - `crontab -r`: removes current cron jobs within current user crontab file
  - `crontab -i`: modifies above `-r` option to prompt user for a `y/n` response before removal

{{% notice green "Bonus" "rocket" %}}
You can also open the global crontab config file with the following command: `sudo vim /etc/crontab`. For the global crontab config file you will have to designate what user this command will be running for. `* * * * * user-name command-to-run`.
![global-crontab](pictures/global-crontab.png?classes=border)
{{% /notice %}}

- Syntax:
  - `* * * * *`: 5 options separated by a space:
  - minute / hour / day-of-month / month / day-of-week
- ranges
- multiple jobs
- step values
- lists

## Example cronjob within crontab:

Open up your crontab config file and add the following cronjob command:

```bash
* * * * * echo "$(date)" >> ~/Desktop/time.log
```

Run the command: `crontab -e`:

![crontab-time-log](pictures/crontab-time-log.png?classes=border)

Add the cronjob to the config file:

<!-- Possible Example: sudo apt update, upgrade, autoremove once a week -->
