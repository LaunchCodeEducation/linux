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

Parse text and return lines that match specific patterns.

## Usage

- Search for file names matching a specific pattern in a directory
- Search contents of a file for specific patterns
- Search web request data for lines matching specific patterns

## What is a Pattern?

A pattern is written as a regular expression.

Regular expressions can be:

- a single character
- a word
- a phrase
- all of the above using the additional tools defined by regular expressions

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

## Word & Phrase Matching

Any string is a valid regular expression. When using `grep` with a string as the regular expression to match lines against, any line that contains the string will be matched.

### Match `'Paul'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Paul'
```

Output:

![grep 'Paul' Output](pictures/grep-simple-string.png?classes=border)

`grep` is searching each line of our file for pattern matches.

This command has matched:

- `Paul` as the first name
- `Paula` as the first name
- `Paul` as the last name

It would also match `Paul` in any remaining sections like the company, or email address.

Matches all first_name = "Paul", also matches with first_name = "Paula", also matches with last_name = "Paul".

It would match any line that contains the exact string "Paul" in any part of the line.

### Match `'Paul,Rogers'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Paul,Rogers'
```

![grep 'Paul,Rogers' Output](pictures/grep-less-simple-string.png?classes=border)

This is a much more specific string we are matching resulting in far less results.

Two records matched:

1. `Paul,Rogers,richardmedina@exaxmple.org,Edward Jones`
2. `Paul,Rogers,richard72@example.org,mastercard`

### Match `'Paul,Ro'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Paul,Ro'
```

Output:

![grep 'Paul,Ro' Output](pictures/grep-least-simple-string.png?classes=border)

This is a less specific string.

Six records matched each last name started with `Ro` as dictated by the regular expression, but the rest of the name didn't matter which is why `Rogers`, `Robinson`, & `Rodriquez` all matched.

**`grep` will parse the entire text and only return lines that contain the exact pattern provided**.

## More Specific Matching with Regex Concepts & Symbols

Regular Expressions are a very powerful tool. By learning the Regular Expression concepts and syntax you can create very specific patterns.

This class doesn't really cover Regular Expressions, however we included some of the basics to show how better patterns can be created by using some of the Regular Expression Syntax.

## Regular Expression Line Begin Anchor: `^`

You can match the beginning of a line with the Regular Expression line begin anchor: `^`.

Earlier `grep 'Paul'` matched lines that had `'Paul'` at any point in the line. If we want to match `'Paul'` at the very beginning of each line we could use the line begin anchor: `^`.

### Match `'^Paul'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^Paul'
```

Output:

![grep '^Paul' Output](pictures/grep-line-begin-anchor.png?classes=border)

Take note that **`Bianca,Paul,...` is not** in our matched lines.

### Match `'^Paul,'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^Paul,'
```

Output:

![grep '^Paul,' Output](pictures/grep-line-begin-anchor-two.png?classes=border)

Take note that **`Paula,Richardson,...` is not** in our matched lines.

## Regular Expression Line End Anchor: `$`

You can match the end of a line with the Regular Expression line end anchor `$`.

In the case of our data-set company names come at the end of each line.

### Match `'s$'`

Let's match all lines that end with the letter `s`:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 's$'
```

Output:

![grep 's$' output](pictures/grep-line-end-anchor.png?classes=border)

Any line that ends with the letter `s` has been matched, in the case of this dataset `Express Scripts` and `Edward Jones` both match our provided pattern.

### Match `'Accenture$'`

Since the last entry in each record is a company name let's match all records that have `Accenture` as the company:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep 'Accenture$'
```

![grep 'Accenture$'](pictures/grep-line-end-anchor-two.png?classes=border)

Every line that ends with `Accenture` is a part of the output from this `grep` command.

## Regular Expression Any Character: `.`

You can use the any character reserved symbol (`.`) to instruct the Regular Expression pattern to match **any** single character.

### Match `'^.a'`

Let's match all lines that start with any character, but the second character must be the lowercase letter `a`:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^.a'
```

Output:

![grep '^.a'](pictures/grep-any-character.png?classes=border)

### Match `'.7@example.com`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '.7@example.com'
```

Output:

![grep '.7@example'](pictures/grep-any-character-two.png?classes=border)

## Regular Expression Sets: `[]`

### Match `'3[0-9]`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '3[0-9]'
```

### Match `'3[5-9]'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '3[5-9]'
```

### Match `'^Paul,[A-F]'`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^Paul,[A-F]'
```

