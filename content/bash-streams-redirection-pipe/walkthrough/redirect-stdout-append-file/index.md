---
title: "Redirect STDOUT Append File"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 105
---

## Redirect `STDOUT` Append to File

Bash also provides a `STDOUT` redirection **append** to file operator. In this case the contents of the existing file would not be overwritten, but instead a new line(s) would be added (append) at the end of the file.

Let's try this out using the `echo` command:

```bash
echo "Hello, world!" >> hello-from-bash.txt
```

Output and Validation:

![echo "Hello, world!" >> hello-from-bash.txt && cat hello-from-bash.txt output](pictures/append-echo.png?classes=border)

Similarly to the write redirection operator, the append operator created a new file and added the contents from `STDOUT` to the file.

The difference is the file wasn't overwritten with the contents of `STDOUT`.

This can be tested by executing another append redirection from bash:

```bash
echo "Good morning!" >> hello-from-bash.txt
```

Output and Validation

![echo "Good morning!" >> hello-from-bash.txt && cat hello-from-bash.txt](pictures/append-echo-2.png?classes=border)

The `STDOUT` redirect append operator simply added the text to the contents of the file.