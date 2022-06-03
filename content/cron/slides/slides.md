---
title: "Slides"
date: 2022-02-08T15:07:22-06:00
draft: false
hidden: false
# type: "slides"
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Cron

---

## Purpose

Tool used to execute scheduled commands at a specific minute, hour, day, month, and day of the week
___

## Parameters

Cron requires five time parameters to be considered a valid command

* * * * * command to be run

minute | hour | day of month | month of year | day of week

---

## Crontab

Crontab is the file that will hold instructions for the cron daemon

You can have as many cronjobs within the crontab as you would like

___

### Global Crontab vs User Crontab

You can find the global crontab at the following location:

/etc/crontab - This crontab file is system wide

When you open crontab using the crontab -e command it is user specific

---

## Cronjobs

Every job within the Crontab is considered a cronjob

___

### Use Cases

Cronjob that updates your package repositories at the end of every week

Cronjob that clears unwanted files from specific directories at end of a month

Cronjob that reminds you of important dates

The list goes on

{{< /slides >}}

