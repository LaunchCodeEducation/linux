---
title: "Walkthrough"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 105
---

## Name

> Cron - daemon to execute scheduled commands

## Purpose

Execute a command to be run at a specific time or interval.

**Time interval options**:
  - `minute`
  - `hour`
  - `day-of-month`
  - `month`
  - `day-of-week`

## Setup

For the distribution of Ubuntu used in this class `cron` comes as a preinstalled and configured package.

### Validation

The location of the tools used in this chapter can be viewed with the following commands:

```bash
which cron
```

```bash
which crontab
```

