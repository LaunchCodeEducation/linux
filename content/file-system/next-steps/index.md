---
title: "Next Steps"
date: 2021-11-09T15:12:13-06:00
draft: false
weight: 115
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-11 # UPDATE ANY TIME CHANGES ARE MADE
---

## Next Steps

We mainly explored navigating the file-system from a Bash shell. You can continue building Bash shell skills by referencing the official [GNU Bash Reference Manual](https://www.gnu.org/software/bash/manual/html_node/index.html)

The entire manual will take you through the entire Bash shell and how it can be used. That may be overwhelming. We recommend checking out some specific sections as a great place to continue your Bash shell learning journey:

- [Bash Shell Pipelines](https://www.gnu.org/software/bash/manual/html_node/Pipelines.html#Pipelines): to learn how to pass the output (STDOUT) of one command to another command.
  - example: `cat /etc/passwd | grep student` how has the output been modified from running `cat /etc/passwd` alone?
- [Redirecting Output](https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirecting-Output): to learn how to redirect the various input/output streams in Linux.
  - example: `echo "My name is Paul!" > name.file` look for a new file called `name.file`
  - example: `cat /etc/passwd > users.file` look for a new file called `users.file`


It is also a good idea to start learning about the importance of **files** in Linux. You can begin this journey with the [Ubuntu: FilePermissions](https://help.ubuntu.com/community/FilePermissions) article.