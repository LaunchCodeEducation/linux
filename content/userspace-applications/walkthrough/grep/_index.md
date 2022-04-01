---
title: "grep"
date: 2021-03-22
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Name

> grep, egrep, fgrep, rgrep - print lines that match patterns

## Purpose

Parse text and only return lines that match specific patterns (specific characters, words, phrases or regular expressions).

## Usage

- Search for file names matching a specific pattern in a directory
- Search contents of a file for specific patterns

## What is a Pattern?

A pattern can be a single character, a word, a phrase, or a regular expression (regex).

## Activity

- `ls` with grep
  - plain text (letter: `i`)
  - plain text (word: `hello`)
  - plain text (`hello.py`)
  - basic regex (`hello.\(py\|sh\)`) (regex group: `()`, regex or: `|`)
  - basic regex (filename must start with: `^i`) (regex line begin anchor: `^`)
  - basic regex (filename must end with: `\..*^`) (regex line end anchor: `$`)
- only the `.java` files
- `find` with grep
  - find 'bash' at root: `sudo find / -name 'bash'`
    - too much information, I just want `/bin` options: `sudo find / -name 'bash' | grep 'bin'`
- `wget` a CSV file
  - `cat [file] | grep "[search argument]"`: searching for names
  - `cat [file] | grep "[search argument]"`: searching for dates
  - `cat [file] | grep "[search argument]"`: searching for phone numbers
  - `cat [file] | grep "[search argument]"`: searching for addresses
  - `cat [file] | grep "[search argument]"`: searching for dollar amounts