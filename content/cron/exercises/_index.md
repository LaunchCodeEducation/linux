---
title: "Exercises"
date: 2022-02-08T15:07:22-06:00
draft: false
weight: 110
---

## Exercises

Create a cronjob that removes all .txt files from your `Desktop` directory every 3 minutes.

 - Add a file to your Desktop directory for testing purposes:

```bash
touch /home/student/Desktop/example-file.txt
```

{{% expand "Click Here for Answer" %}}
```bash
*/3 * * * * rm /home/student/Desktop/*.txt
```
{{% /expand %}}

Create a cronjob that would append the current date the first minute of every month to a file called `new-month` on your Desktop.

{{% expand "Click Here for Answer" %}}
```bash
1 0 1 * * echo "$(date)" >> /home/student/Desktop/new-month
```
{{% /expand %}}

## Questions and Answers

### What is a Crontab?

{{% expand "Click Here for Answer" %}}
File that holds instructions for the cron daemon.
{{% /expand %}}

### How do you list the current user's Crontab?

{{% expand "Click Here for Answer" %}}
```bash
crontab -l
```
{{% /expand %}}

### How do you edit the current user's Crontab?

{{% expand "Click Here for Answer" %}}
```bash
crontab -e
```
{{% /expand %}}

### How many time parameters are required for a Cronjob?

{{% expand "Click Here for Answer" %}}
Five
{{% /expand %}}

### What would the syntax be to run a cronjob at 5:30 PM every Monday, Wednesday, and Friday?

{{% expand "Click Here for Answer" %}}
30 17 * * 1,3,5
{{% /expand %}}

### What is the syntax to run a cronjob at 5:00 AM the first day of every quarter of the year?

{{% expand "Click Here for Answer" %}}
0 5 1 3,6,9,12 *
{{% /expand %}}

