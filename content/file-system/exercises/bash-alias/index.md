---
title: "Bash Alias"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 2
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
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