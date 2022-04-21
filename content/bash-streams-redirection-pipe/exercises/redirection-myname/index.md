---
title: "Redirection: myname.txt"
date: 2022-04-08T13:54:05-05:00
draft: false
weight: 100
---

## Creating `myname.txt`

Using the `echo` command and the redirection write operator `>`, create a new file named `myname.txt` that contains your first name.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
echo "Paul" > myname.txt
```
{{% /expand %}}

## Overwrite `myname.txt`

Using the `echo` command and the redirection write operator `>`, overwrite the `myname.txt` that contains a more informative line like `firstName=[YOUR FIRST NAME]`.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
echo "firstName=Paul" > myname.txt
```
{{% /expand %}}

## Appending to `myname.txt`

using the `echo` command and the redirection append operator `>>`, append your last name as a new line to the `myname.txt` file like `lastName=[YOUR LAST NAME]`.

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
echo "lastName=Matthews" >> myname.txt
```
{{% /expand %}}

## Verification of `myname.txt`

### How can you verify that `myname.txt` matches the following structure?

```bash
firstName=[YOUR FIRST NAME]
lastName=[YOUR LAST NAME]
```

{{% expand "CLICK FOR ANSWER" %}}
By using the `cat` command.
```bash
cat myname.txt
```
Output:
```bash
firstName=Paul
lastName=Matthews
```
{{% /expand %}}