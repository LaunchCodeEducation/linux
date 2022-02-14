---
title: "Exercises"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 3
original_author: "Paul Matthews" 
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## Exercises

- create a hidden **notes** directory in you home directory
- create a `file-system-navigation.notes` file in your new hidden notes directory
- edit the `file-system-navigation.notes` file with a brief description of what each of the following commands do:
  - `pwd`
  - `ls`
  - `cd`
  - absolute path vs relative path
  - `.`, `..` and `~` shortcuts
  - `mkdir`
  - `touch`
  - `mv` 
- add a new bash alias called `allhomecontents` which shows all files (including hidden files) to your `.bashrc` profile
  - source the new file
  - run the new alias
- find all files containing the word `hosts` in the `/etc` directory
  - hint: sudo
  - hint: you may need to use multiple bash wildcards
  - bonus: only return files *checkout the man pages and look for the -type option*
- printout the contents of the `/etc/hosts`, which should be one of the files/directories you found in the last step
  - what do you think this file means?
  - hint: what is the relationship between `127.0.0.1` and the domain name `localhost`?
- find the `passwd` file in the `/etc/` directory
  - find your username in this file
    - what does it say the home directory for that user is?