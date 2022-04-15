---
title: "Cron-syntax"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 100
---

## Cron Syntax

Cron requires you to provide 5 time parameters to designate the time you want a job to execute. The time is broken down as follows:

- `minute`: 0-59
- `hour`: 0-23
- `Day of Month`: 1-31
- `Month of Year`: 0-11
- `Day of the Week`: 1-7

You also need to provide the cronjob a command after designating the desired time:

```bash
* * * * * echo "Hello Cron" >> ~/Desktop/hello-cron.log
```

The above cronjob would run and append the phrase "Hello Cron" to the `hello-cron.log` file every minute.

## Special Characters

- `*` Asterisk: Specifies that the command will fire at every interval in a given time slot
- `-` Hyphen: Expression to designate a range of values within a given time slot
- `/` Forward Slash: Expression to allow dividing time slot into intervals
- `,` Comma: Expression to create a list within any given time slot

## Examples:

```bash
* * * * * 
```
- ranges
- multiple jobs
- step values
- lists