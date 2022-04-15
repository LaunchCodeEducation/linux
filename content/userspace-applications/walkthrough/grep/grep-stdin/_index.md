---
title: "grep From STDIN"
date: 2021-04-04
draft: false
weight: 120
---

## `grep` from `STDIN`

So far you have only used grep to search a specific file. However, you can pass input directly to `grep` and match `STDIN` results against a Regular Expression pattern.

### `ls | grep` Example

Match patterns for all contents of the home directory:

Match all files with a `.` in our home directory.

```bash
ls ~ | grep '\.'
```

Output:

![ls to grep output](pictures/grep-stdin-one.png?classes=border)

{{% notice note %}}
The `.` is a Regular Expression special symbol meaning to match any character. In order to search for an actual `.` you need to escape the `.` so that RegEx knows that you are searching for an actual period and not referencing special symbol. The escape special symbol in RegEx is the backslash `\` symbol.

When you provide the regular expression: `'\.'` you are telling `grep` to match any lines that have a `.` in them.

{{% /notice %}}

### `history | grep` Example

Match all `grep` commands in our `bash history`

```bash
history | grep 'grep'
```

Output:

![history to grep '\.' output](pictures/grep-stdin-two.png?classes=border)

### `find | grep` Example

Match all `/bin/` for files containing the word `bash` in the root directory.

```bash
sudo find / -name 'bash' | grep '/bin/'
```

Output:

![find to grep output](pictures/grep-stdin-three.png?classes=border)

### `curl | grep` Example

Send a `curl` request directly to the API and match the results (`csv` in `STDIN`) to a specific pattern.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Microsoft$'
```

Output:

![curl to grep output](pictures/grep-stdin-four.png?classes=border)