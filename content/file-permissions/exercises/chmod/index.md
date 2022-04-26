---
title: "Chmod Exercises"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 1
---

## `chmod` Practice

Create a new file called `chmod.exercises`.

### Question: What are the default permissions for the new file?

{{% expand "CLICK FOR ANSWER" %}}
`-rw-rw-r--`:
- owner: `Read` and `Write`
- group: `Read` and `Write`
- all others: `Read`
{{% /expand %}}

### Bonus Question: What was the command to view the file permissions?

{{% expand "CLICK FOR ANSWER" %}}
`ls -l chmod.exercises`
{{% /expand %}}

## Change `chmod.exercises` permissions to `-r--r--r--`

Change the file permissions to **Read only** for the owner, group and all other users.

### Question: What was the command for changing the file permissions to `-r--r--r--`?

{{% expand "CLICK FOR ANSWER" %}}
`chmod 444 chmod.exercises`
{{% /expand %}}

## Change `chmod.exercises` permissions to `-rw-r-----`

Change the file permissions to match the following:

- owner: `Read` and `Write`
- group: `Read`
- other: no permissions (`None`)

### Question: What was the command for changing teh file permissions to `-rw-r-----`?

{{% expand "CLICK FOR ANSWER" %}}
`chmod 640 chmod.exercises`
{{% /expand %}}

## Change `chmod.exercises` permissions to `-rwxr-x--x`

Change the file permissions to match the following:

- owner: `Read`, `Write` and `Execute`
- group: `Read` and `Execute`
- other: `Execute`

### Question: What was the command for changing the file permissions to `-rwxr-x--x`?

{{% expand "CLICK FOR ANSWER" %}}
`chmod 751 chmod.exercises`
{{% /expand %}}

{{% notice note %}}
After completing the exercises feel free to delete the `chmod.exercises` file.
{{% /notice %}}