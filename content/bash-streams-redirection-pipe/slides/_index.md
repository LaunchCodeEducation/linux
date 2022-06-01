---
title: "Slides"
date: 2022-04-08T13:54:05-05:00
draft: false
hidden: false
# type: "slides"
weight: 1
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Bash: Streams, Redirection & Pipes

---

## Types of Streams

STDIN: Standard Input - 0 (file descriptor)

STDOUT: Standard Output - 1 (file descriptor)

STDERR: Standard Error - 2 (file descriptor)
___

### Standard Input

All Bash command are a form of STDIN
___

### Standard Output

STDOUT is always displayed inside of the terminal window by default

Should you ever wish for STDOUT not to be displayed this can be accomplished in different ways

Sometimes a command allows -s as a "silent" option

You can also redirect the stream into an alternate location
___

### Standard Error

Similar to STDOUT, STDERR is also displayed inside of the terminal window by default

STDERR is commonly the result of an incorrect bash command, incorrect arguments, or incorrect options provided

---

## Redirection

Redirect Write >

Redirect Append >>

___

### Redirect Write with STDOUT

The > operator is used to redirect STDOUT and write to a new location

Using the redirect write option will **overwrite** the contents of the target location

Redirecting the STDOUT will also prevent the STDOUT of the command to be displayed inside of the terminal window
___

### Redirect Append with STDOUT

The >> operator is used to redirect STDOUT and append to a provided location

Using the redirect append option will **append** the contents of the target location

This means that the STDOUT will be added to a given file in addition to what is already inside

As mentioned in the previous slide this will also prevent the STDOUT from being displayed inside of the terminal window
___

### Redirect STDERR

STDERR can also be redirected using its file descriptor

To write STDERR to a new location you would use 2>

To append STDERR to a new location you would use 2>>

---

## Pipes

The Bash pipe operator | allows the user to take STDOUT from the first command and use it as STDIN for the next

Piping allows the user to chain multiple commands together for more complex commands

{{< /slides >}}