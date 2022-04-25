---
title: "Crontab"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 105
---

## Usage

A crontab is a file that holds the instructions for the cron daemon. 

Each cronjob within the crontab will run a specific command at a specific time based on the crontab configuration.

- Commands:
  - `crontab <filename>`: command to run cron-jobs within a separate file as an argument
  - `crontab -e`: edit current user's crontab
  - `crontab -l`: list current user's crontab
  - `crontab -r`: delete user's crontab
  - `crontab -i`: prompt before deleting user's crontab

## Open crontab

View the crontab file with the follwing command:

```bash
crontab -e
```

Output:

![crontab-e output](pictures/crontab-e.png?classes=border)

The default user crontab seen from the previous command will look similar to the above screenshot.

{{% notice green "Bonus" "rocket" %}}
The global crontab config file can be viewed with the following command: 

```bash
sudo vim /etc/crontab
```

In addition to the five time parameters, and command to execute, the global crontab config file requires the user that will execute the command

```bash
* * * * * user-name command-to-run
```

![sudo vim /etc/crontab output](pictures/global-crontab.png?classes=border)

The file was opened with `vim` and can be closed with `:q`.
{{% /notice %}}