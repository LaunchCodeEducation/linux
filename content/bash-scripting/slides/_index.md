---
title: "Slides"
date: 2022-04-08T13:54:20-05:00
draft: false
hidden: false
# type: "slides"
weight: 1
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Scripting with Bash

---

## Bash Scripting Basics

A shell script is simply a file that holds a certain set of commands to be run within your terminal and executed by Bash

Commonly ending with the file extenstion .sh (although not necessary)

shebang - informs OS what shell to use when executing the script. The shebang points to the absolute path of the shell (#!/bin/bash)

___

### Executing a Script File

Executing or running a script file can be done in multiple ways

The two examples in this course:

By using the command "bash" and the script file as an argument

Invoking the script by using the absolute or relative path to the script file

### Slide 1 Vertical Slide

---

## Bash Variables

Similar to other programming languages you are familiar with Bash utilizes variables

Bash Variable: name="John"

JavaScript Variable: let name = "Paul";

Python Variable: name = "George"

Java variable: String name = "Ringo";
___

### Variable Types

Similar to Python a bash variable will respect any value type you assign to it

---

## Conditional Statements

Bash also contains conditional statements

if statements

if else

if elif else

if statements must be closed with "fi"

___

### Operators

Bash has built in binary operators for the following:

equal to: -eq

not equal to: -ne

less than: -lt

less than or equal to: -le

greater than: -gt

greater than or equal to: -ge

---

## Loops

Bash also contains loops

The two we will cover in class will be the for loop and while loop

For loops and While loops will have a "do" statement with a clause, and a closing "done" statement

We will also cover for loops with conditional statements

---

{{< /slides >}}