---
title: "STDIN: Redirect Write"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 100
---

## Standard Input

<!-- TODO: What are the forms of standard input? Another way we can give data to various commands or scripts. Standard In. -->

- Bash accepts input from the user as text. 
  - redirect input from file into command:
    - `cat < filename`

{{% notice note %}}
Most bash commands and packages that take files as input are configured that you can pass them as a argument or `stdin`.
{{% /notice %}}

- redirect write command output to file with `>`
  - `ls -a > ls-a-example`