---
title: "Bonus: Pipe Operator"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 110
---

## Bonus: Selecting commands containing redirection write operators from `history` and saving.

Pipe the `STDOUT` from the `history` command to `grep` and search all lines for a redirection write operator `>` and write the output to `myhistory-write-commands.txt`.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
history | grep '>' > myhistory-write-commands.txt
```
{{% /expand %}}

## Verification

{{% expand "CLICK FOR ANSWER" %}}
```bash
cat myhistory-write-commands.txt
```

Example output:

```bash
  910  echo "Paul" > myname.txt
  913  echo "firstName=Paul" > myname.txt
  915  echo "lastName=Matthews" >> myname.txt
  917  history > myhistory.txt
  919  history | grep '>' > myhistory-write-commands.txt
```

In the command above `grep` is searching each line of output from the `history` command for a specific character (the redirect write operator `>`) and only putting matched lines into `STDOUT` which is then written to `myhistory-write-commands.txt`!


Take note that the redirect append operator was matched as a part of the `grep` search because it is made up of two characters that matched the `grep` search!

{{% /expand %}}