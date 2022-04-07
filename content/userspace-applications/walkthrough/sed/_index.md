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

## Setup

This and the following articles use the `user-data.csv` file you may have downloaded it during the `grep` examples.

If you don't already have the `user-data.csv` file in your home directory run the following command:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv > ~/user-data.csv
```

{{% notice green "Bonus" "rocket" %}}
You can validate the `user-data.csv` file with the following command:

```bash
wc -l ~/user-data.csv
```

The output you see should confirm there are 25001 lines in the file.

{{% /notice %}}


## `sed` substitute First Occurrence of `'a'` with `'q'`

{{% notice warning %}}
All commands in this and following articles assume your current working directory is the directory where the `user-data.csv` file resides, most likely your home directory.

You can change into your home directory from anywhere with the command:

```bash
cd ~
```
{{% /notice %}}

Replace the first `a` in each line with `q`:

```bash
sed 's/a/q/1' user-data.csv
```

Output:

![sed 's/a/q/1' user-data.csv output](pictures/sed-s-a-q-1.png?classes=border)

Looking at the last record displayed in `STDOUT`:

`Kristy,Strong,nwilliqms@example.com,Hunter Engineering`

It looks like `nwilliams` was changed to `nwilliqms`. Take a look at the other lines to notice tha the first instance of each `a` character was replaced with a `q` character.


{{% notice note %}}
STDOUT shows the substitution that was made, however `sed` does not edit the original file by default. You would need to instruct `sed` to save the changes by writing STDOUT to a file with the redirection operator (`>`) or use the `-i` option. Both of these options for saving changes will be covered in future sections.
{{% /notice %}}

## `sed` substitute All Occurrences of `'a'` with `'q'`

Replace all occurrences of `a` with `q`:

```bash
sed 's/a/q/g' user-data.csv
```

Output:

![sed 's/a/q/g' user-data.csv output](pictures/sed-s-a-q-g.png?classes=border)

The last record: `Kristy,Strong,nwilliams@example.org,Hunter Engineering` was changed to: `Kristy,Strong,nwilliqms@exqmple.org,Hunter Engineering`