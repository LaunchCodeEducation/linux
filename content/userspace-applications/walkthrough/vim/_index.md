---
title: "vim"
date: 2021-03-22
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Name

> vim - Vi IMproved, a programmer's text editor

## Purpose

CLI for editing text files. Provides various modes and actions that allow the user to navigate, search and transform text files manually, or automatically.

## Usage

- create new files in terminal
- edit files in terminal
- read files in terminal

## Setup

You have likely installed `vim` already, if you have not you can with `apt`:

```bash
sudo apt install vim
```

## `vim` Modes

`vim` has a few different modes:

Basic Modes:
- Normal
- Visual
- Select
- Insert
- Command-line
- Ex

Additional Modes:
- Operator-pending
- Replace
- Virtual Replace
- Insert Normal
- Insert Visual
- Insert Select

{{% notice green "Bonus" "rocket" %}}
The listed modes can be found in the [Vim Docs / vim-modes](http://vimdoc.sourceforge.net/htmldoc/intro.html#vim-modes).
{{% /notice %}}

This curriculum will only utilize the following modes:

- **Normal**
- **Insert**

Our goal is to learn how to **create**, **edit**, and **read** files from the terminal using `vim`.
