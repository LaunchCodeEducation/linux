---
title: "Slides: Fullscreen"
date: 2022-04-08T13:54:20-05:00
draft: true
hidden: true
type: "slides"
weight: 1
---

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

---

## Cronjobs

Every job within the Crontab is considered a cronjob

___

### Use Cases

Cronjob that updates your package repositories at the end of every week

Cronjob that clears unwanted files from specific directories at end of a month

Cronjob that reminds you of important dates

The list goes on