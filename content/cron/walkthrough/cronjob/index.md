---
title: "Create a Cronjob"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 110
---

## Example cronjob within crontab:

Open up your crontab config file and add the following cronjob command:

```bash
* * * * * echo "$(date)" >> ~/Desktop/time.log
```

Run the command: `crontab -e` and add the cronjob to the config file:

![crontab-time-log](pictures/crontab-time-log.png?classes=border)

Write the file and navigate to your desktop. You should see the created time-log file created from the cronjob.

## Validation

![time-log-validation](pictures/time-log-validation.png?classes=border)

`cat` out the `time-log` file.

## Recap:
- Add a cronjob to crontab file
- check file created from cronjob for validation

