---
title: "Pipe Operator"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 115
originalAuthor: <no value> # to be set by page creator
originalAuthorGitHub: <no value> # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Piping

Using the pipe operator `|` allows bash to redirect `stdout` to a new command or place. Piping allows you to send data from one program or command to another.
  - Generally used to combine two or more commands
  - Output continues to input into the next command
    
## Examples    

- `ls -a | grep "bash`
  - output from ls as input to grep
- `ls -a | less`
  - output from ls as input to less
- `ls -a | more`
  - output from ls as input to more
- `history | grep "git"`
  - output from history as input to grep
- `echo "hello piping" | grep "piping"`
  - output from echo as input to grep