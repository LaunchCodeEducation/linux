---
title: "Vim Exercises"
date: 2021-11-09T15:12:20-06:00
draft: false
weight: 120
---

## Questions & Answers

### What is the purpose of `vim`?

{{% expand "CLICK FOR ANSWER" %}}
To create, view, and edit files from the terminal.
{{% /expand %}}

### How do you open an existing file with `vim`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
vim path/to/file-name
```
{{% /expand %}}

### What are the three `vim` modes we learned in this course?

{{% expand "CLICK FOR ANSWER" %}}
1. Normal
1. Insert
1. Command Line (subset of Normal)
{{% /expand %}}

### What is the purpose of `Normal` mode?

{{% expand "CLICK FOR ANSWER" %}}
To navigate a file, perform commands on the file, search a file.
{{% /expand %}}

### What is the purpose of `Insert` mode?

{{% expand "CLICK FOR ANSWER" %}}
To modify the contents of a file directly with the keyboard.
{{% /expand %}}

### In `Normal` mode how do you execute a `write` command?

{{% expand "CLICK FOR ANSWER" %}}
```bash
:w
```
{{% /expand %}}

### In `Normal` mode how do you execute a `quit` command?

{{% expand "CLICK FOR ANSWER" %}}
```bash
:q
```
{{% /expand %}}

### In `Normal` mode how do you navigate through a file?

{{% expand "CLICK FOR ANSWER" %}}
Many ways:

1. directional pad arrow keys for moving left, down, up and right
1. `hjkl` keys for moving left, down, up, and right
1. `$` to move to the end of a line
1. `0` to move to the beginning of a line
1. `gg` to move to the top of a file
1. `G` to move to the end of a file
1. `:[line-number]` to move to an exact line number
1. `w` to navigate to the next word
1. `b` to navigate to the previous word
{{% /expand %}}

### In `Insert` mode how do you navigate through a file?

{{% expand "CLICK FOR ANSWER" %}}
Limited navigation. You must use the directional pad arrow keys for moving left, down, up and right.
{{% /expand %}}

### How do you change from `Normal` mode into `Insert` mode?

{{% expand "CLICK FOR ANSWER" %}}
Many ways. This course showed the `i` key which switches to `Insert` mode at the current cursor location.

The `a` key switches to `Insert` mode right after the current cursor location.
{{% /expand %}}

### How do you change from `Insert` mode to `Normal` mode?

{{% expand "CLICK FOR ANSWER" %}}
By pressing the escape `esc` key.
{{% /expand %}}