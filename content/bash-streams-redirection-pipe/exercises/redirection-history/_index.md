---
title: "Redirection: Saving History"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 105
---

## Saving History as `myhistory.txt`

Using the `history` command and the redirection write operator `>`, create a new file named `myhistory.txt` that contains the full record of your history.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
history > myhistory.txt
```
{{% /expand %}}

## Verification of `myhistory.txt`

### How can you verify that `myhistory.txt` contains the history of your current shell?

{{% expand "CLICK FOR ANSWER" %}}
```bash
cat myhistory.txt
```

Example **trimmed** output:

```bash
  908  ls
  909  clear
  910  echo "Paul" > myname.txt
  911  ls
  912  cat myname.txt
  913  echo "firstName=Paul" > myname.txt
  914  cat myname.txt
  915  echo "lastName=Matthews" >> myname.txt
  916  cat myname.txt
  917  history > myhistory.txt
```

{{% /expand %}}