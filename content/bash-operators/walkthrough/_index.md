---
title: "Walkthrough"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 2
---

## Walkthrough

Under  normal  circumstances every UNIX program has three streams opened for it when it starts up, one for input, one for output,
and one for printing diagnostic or error messages.

Bash and most Linux shells use the following Input / Output streams:
- `stdin`: Standard Input
- `stdout`: Standard Output
- `stderr`: Standard Error

{{% notice note %}}
By default all forms of stdin and stderr are printed within your terminal window
{{% /notice %}}

{{% children %}}