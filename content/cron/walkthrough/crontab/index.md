---
title: "Crontab"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 105
---

## Usage

A crontab file holds the instructions for the cron daemon. Each job within the crontab will run a specific command at a specific time on the designated date.

- Commands:
  - `crontab <filename>`: command to run cron-jobs within a separate file as an argument
  - `crontab -e`: edit current user's crontab
  - `crontab -l`: list current user's crontab
  - `crontab -r`: delete user's crontab
  - `crontab -i`: prompt before deleting user's crontab

## Open crontab

Open up your crontab file:

![crontab-e](pictures/crontab-e.png?classes=border)

Run the command `crontab -e`

The default user crontab file will look similar to the above screenshot.


{{% notice green "Bonus" "rocket" %}}
You can also open the global crontab config file with the following command: `sudo vim /etc/crontab`. For the global crontab config file you will have to designate what user this command will be running for. `* * * * * user-name command-to-run`.
![global-crontab](pictures/global-crontab.png?classes=border)
{{% /notice %}}