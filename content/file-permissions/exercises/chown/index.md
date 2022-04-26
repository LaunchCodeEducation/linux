---
title: "Chown Exercises"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 2
---

## `chown` Practice

Create a new file called `chown.exercises`.

### Question: What are the default owner and group for the new file?

{{% expand "CLICK FOR ANSWER" %}}
`student student`

The `student` user owns the file.

The `student` user is a part of the `student` group.

{{% /expand %}}

### Bonus Question: What is the command to view the file owner and group?

{{% expand "CLICK FOR ANSWER" %}}
`ls -l chown.exercises`
{{% /expand %}}

## Change the `chown.exercises` file owner to the `root` user.

### Question: What was the command?

{{% expand "CLICK FOR ANSWER" %}}
`sudo chown root chown.exercises`
{{% /expand %}}

## Change the `chown.exercises` file group to the `root` group.

### Question: What was the command?

{{% expand "CLICK FOR ANSWER" %}}
`sudo chown :root chown.exercises`
{{% /expand %}}

## Change the `chown.exercises` file owner to `student` and group to `student`.

### Question: What wast he command?

{{% expand "CLICK FOR ANSWER" %}}
`sudo chown student:student chown.exercises`
{{% /expand %}}

{{% notice note %}}
After completing the exercises feel free to delete the `chown.exercises` file.
{{% /notice %}}