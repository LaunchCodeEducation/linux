---
title: "Slides"
date: 2022-03-22
draft: false
hidden: true
# type: "slides"
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Userspace Applications

---

## wget

GNU software package used to retreive files using HTTP, HTTPS, FTP, and FTPS

___

### Usage

with wget you can download a file from the url holding that file

The download can be any format

Once downloaded you are able to manipulate the file as you see fit

---

## curl

tool used to craft HTTP and HTTPS requests while also displaying responses

Open source software
___

### Usage

Allows the user to transfer data from within your terminal or by the use of scripts

Great for testing APIs using HTTP methods GET, POST, PATCH, DELETE, and PUT requests

---

## grep

tool used to search content (using words and regular expressions)

___

### Usage

Search for file names matching a specific pattern in a directory

Search contents of a file for specific patterns

Search web request data for lines matching specific patterns

___

### Patterns

A pattern is written as a regular expression or RegEx as you may be more familiar with

This can be:

a single character

a word

an entire phrase

all of the above using the tools / syntax defined by regular expressions

---

## sed

tool used to edit streams of data (substitute)

___

### Usage

search and replace

add content before or after specific patterns

delete lines

add lines

---

## vim

tool used to edit files within your terminal

___


### Usage

Allows the user to edit files within your terminal

Create new files

Edit existing files

Read files

___

### Why it is Useful

Vim and other similar tools are useful when working inside of a remote server

The reason being is that the remote server has no GUI

No provided text editor that you are comfortable with

___

### Modes

Normal - mainly used for navigation

Visual - making changes to selected text

Insert - allows user to insert new characters or remove them

You may see additional modes listed inside of this curriculum but the two modes you are expected to learn and be comfortable with are Normal and Insert modes

___

### Vimtutor

type "vimtutor" in your terminal and hit enter to begin a vim tutorial

{{< /slides >}}