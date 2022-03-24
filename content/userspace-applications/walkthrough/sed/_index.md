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

- search and replace (substitute)
- convert CSV delimeter
- add text after or before specific patterns

## Activity

- `wget` a TSV
  - convert to CSV
- Threat Level Midnight
  - `wget` the Threat Level Midnight Script
    - substitute `Dwight` -> `Samuel L. Chang`
    - substitute all `Dwigh*t` -> `Samuel L. Chang`
- `wget` a TXT
  - add TRANSACTION: [remaining line] to each line that contains a transaction pattern
- `wget` a log file
  - transform contents into a trimmed version with only IP addresses from Russia
    - other countries
- `wget` a log file
  - transform contents with lines containing email address from specific domain endings