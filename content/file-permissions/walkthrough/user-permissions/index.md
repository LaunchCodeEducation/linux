---
title: "User Permissions"
date: 2022-04-14T16:13:40-05:00
draft: false
weight: 1
originalAuthor: <no value> # to be set by page creator
originalAuthorGitHub: <no value> # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## User File Permissions

`ls -l` /path

`ls -l` /path/file

examples

- `drwxrwxrwx`
- `rwxrwxrwx`

d or - (directory or file)

1. `rwx`: permissions for owner
2. `rwx`: permission for other users in the owner's user group
3. `rwx`: permissions for all other user

`r`: read
`w`: write
`x`: execute

So a file with:

- `-rw-r-----`: a standard file: owner can read and write; user group can read; all other user's have NO permissions
- `drw-rw-r--`: a directory: owner can read/write; user group can read/write; all other user's can read
- `rwxr-x---x`: a standard file: owner can read/write/execute; user group can read/execute; all other user's can execute

`chown` command

`chmod` command:

bit notatation:

- 7 `4(r) + 2(w) + 1(x)` rwx: read, write and execute
- 6 `4(r) + 2(w)` 	rw-: read and write
- 5 `4(r) + 1(x)` r-x:	read and execute
- 4 `4(r)` r--: read only
- 3 `2(w) + 1(x)` 	-wx: write and execute
- 2 `2(w)` 	-w-: write only
- 1 `1(x)` 	--x: execute only
- 0 `0` ---: none 


numerical file permissions