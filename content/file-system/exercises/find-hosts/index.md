---
title: "Finding Files"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
---

## Find the `hosts` files

- find **all** files containing the word `hosts` in the `/etc` directory
  - hint: you may need to elevate permissions
  - hint: you may need to use wildcards (`*`)
  - bonus: only return files: *checkout the man pages and look for the -type option*
- printout the terminal the contents of the `/etc/hosts`, which should be one of the files/directories you found in the last step
  - what do you think this file means?
  - hint: what is the relationship between `127.0.0.1` and the domain name `localhost`?

## Find the `passwd` file

- find the `passwd` file in the `/etc/` directory
  - find your username in this file
    - what does it say the home directory for that user is?

## Questions & Answers

### What command, arguments, and options did you use to find all files containing the word `hosts` in the `/etc` directory?

{{% expand "CLICK FOR ANSWER" %}}
`sudo find /etc --name *hosts*` 
{{% /expand %}}

### Why are the wildcards (`*`) necessary in the previous answer?

{{% expand "CLICK FOR ANSWER" %}} 
Without the wildcards the find command searches for file names matching exactly `hosts` of which it finds a couple, but it doesn't find **all** files that contain the word `hosts`.
{{% /expand %}}