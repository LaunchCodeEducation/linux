---
title: "sed"
date: 2021-03-22
draft: false
weight: 115
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Name

> sed - stream editor for filtering and transforming text

## Purpose

Edit streams of text allowing entire text files to be filtered, or transformed in any number of ways.

## Usage

- search and replace
- add content before or after specific patterns
- delete lines
- add lines

Like many of the Userspace Applications introduced in this course we will only be covering a small portion of what you can do with a tool.

In the case of `sed` we will simply be showing you how to use the substitute feature. You have likely used a similar feature in other software called `Find & Replace`.

## `sed` Command Pattern

```bash
sed '[script]' 'input-file'
```

## `sed` Substitute Syntax

```bash
sed 's/regex-pattern/replacement-text/flags' 'input-file'
```

- `s`: the action `sed` will be performing, this case a substitute action
- `regex-pattern`: a regular expression sed should search each line for
- `replacement-text`: the text to replace the regular expression with
- `flags`: which matching section(s) should be replaced

### Substitute Flags

- `N`: Only the Nth matched pattern of the line should be replaced
- `g`: All matched patterns of the line should be replaced

{{% notice note %}}
Not including the substitute flag will default to `1`, so only the first matched pattern on the line will be replaced. 
{{% /notice %}}

## `sed` substitute First Occurrence of `'a'` with `'q'`

```bash
sed 's/a/q/1'
```

Output:

![sed 's/a/q/1' output](pictures/sed-s-a-q-1.png?classes=border)

## `sed` substitute All Occurrences of `'a'` with `'q'`

```bash
sed 's/a/q/g'
```

Output:

![sed 's/a/q/g' output](pictures/sed-s-a-q-g.png?classes=border)
