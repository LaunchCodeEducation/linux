---
title: "grep From STDIN"
date: 2021-04-04
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: "" # UPDATE ANY TIME CHANGES ARE MADE
---

## `grep` from `STDIN`

So far we have only used grep to search a specific file. However, you can pass input directly to `grep` and match `STDIN` results against a Regular Expression pattern.

### `ls | grep` Example

Let's match patterns for the contents of the home directory:

Find all files with a `.` in our home directory.

```bash
ls ~ | grep '\.'
```

Output:

![ls to grep output](pictures/grep-stdin-one.png?classes=border)

### `history | grep` Example

Find all `grep` commands in our `bash history`

```bash
history | grep 'grep'
```

Output:

![history to grep '\.' output](pictures/grep-stdin-two.png?classes=border)

### `find | grep` Example

Find all `/bin/bash` in the root directory.

```bash
sudo find / -name 'bash' | grep '/bin/'
```

Output:

![find to grep output](pictures/grep-stdin-three.png?classes=border)

### `curl | grep` Example

Send a `curl` request directly to the API and search the results (`csv` in `STDIN`) for a specific pattern.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Microsoft$'
```

Output:

![curl to grep output](pictures/grep-stdin-four.png?classes=border)