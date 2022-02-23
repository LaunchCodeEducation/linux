---
title: "Bash Alias"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 2
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Create a new Bash Alias

- add a new bash alias called `allhomecontents` which shows all files (including hidden files) to your `~/.bashrc` profile
  - source the new file
  - run the new alias

## Questions

- What is a Bash Alias?
{{% expand "ANSWER" %}} 
A Bash Alias is a command shortcut. It allows you to create a new command name that will run whatever command or collection of commands you want.
{{% /expand %}}
- When you invoke the `allhomecontents` alias what command is being run?
{{% expand "ANSWER" %}} 
`ls`
{{% /expand %}}
- For the previous answer did you include any options to be run with that command?
{{% expand "ANSWER" %}}
**Yes**. The `-a` option so all files, including hidden files, would be displayed. 
{{% /expand %}}