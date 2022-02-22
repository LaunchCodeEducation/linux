---
title: "Finding files"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 3
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Find the `hosts` files

- find **all** files containing the word `hosts` in the `/etc` directory
  - hint: you may need elevate permissions
  - hint: you may need to use wildcards (`*`)
  - bonus: only return files *checkout the man pages and look for the -type option*
- printout the terminal the contents of the `/etc/hosts`, which should be one of the files/directories you found in the last step
  - what do you think this file means?
  - hint: what is the relationship between `127.0.0.1` and the domain name `localhost`?

## Find the `passwd` file

- find the `passwd` file in the `/etc/` directory
  - find your username in this file
    - what does it say the home directory for that user is?

## Questions

- What command, arguments, and options did you use to find all files containing the word `hosts` in the `/etc` directory?
{{% expand "ANSWER" %}}
`sudo find /etc --name *hosts*` 
{{% /expand %}}
- Why are the wildcards (`*`) necessary in the previous answer?
{{% expand "ANSWER" %}} 
Without the wildcards find searches for file names matching exactly `hosts` of which it finds a couple, but it doesn't find **all** files that contain the word `hosts`.
{{% /expand %}}