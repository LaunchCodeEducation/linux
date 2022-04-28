---
title: "Cron-syntax"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 100
---

## Cron Syntax

Cron will schedule a command to be executed at a specific time. Cron expects **five time parameters**, and a valid **command**.

The times are correlated with:
- `minute`: 0-59
- `hour`: 0-23
- `Day of Month`: 1-31
- `Month of Year`: 0-11
- `Day of Week`: 1-7

 After the five time parameters are provided to Cron, it expects a valid command resulting in the line:

```bash
* * * * * echo "Hello Cron" >> ~/Desktop/hello-cron.log
```

The above cronjob would run and append the phrase "Hello Cron" to the `hello-cron.log` file every minute.

{{% notice note %}}
In the preceding example the five time parameters are each `*` indicating to run at every minute, hour, day of the month, month of the year, and day of the week.

Cron will execute the command `echo "Hello Cron" >> ~/Desktop/hello-cron.log` every minute of every hour of every day of the month of every day of the year of every day of the week.
{{% /notice %}}

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