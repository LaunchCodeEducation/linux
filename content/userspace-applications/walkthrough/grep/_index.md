---
title: "grep"
date: 2021-03-22
draft: false
weight: 110
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

## Setup: Download Walkthrough Dataset

Before we can start searching text we need to first download the text we will be searching. From your home directory:

```bash
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv > user.csv
```

This command makes a `curl` request to the provided endpoint and whatever data is returned will be written to a file called `user.csv`.

### Validation

![curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv validation image](pictures/curl-dataset.png?classes=border)

You can `cat` out the file, but it has 25000 records in it.

![cat user.csv output](pictures/cat-user-csv.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You can use the `wc` package to count the lines in the file:

```bash
wc -l user.csv
```

Output:

![wc -l user.csv output](pictures/wc-l-user-csv.png?classes=border)

25001 total lines.
{{% /notice %}}

## Word & Phrase Matching

Any string is a valid regular expression. 

When using a string as the regular expression in the pattern **all lines containing the string** will be matched.

### Match `'Paul'`

```bash
grep 'Paul' user.csv
```

Trimmed Output:

![grep 'Paul' Output](pictures/grep-simple-string.png?classes=border)

`grep` is searching each line of our file for pattern matches.

This command has matched:

- `Paul` as the first name
- `Paula` as the first name
- `Paul` as the last name

It would also match `Paul` in any remaining sections like the company, or email address.

As long as `Paul` is found at any point in the line, the line will be returned.

### Match `'Paul,Ro'`

```bash
grep 'Paul,Ro' user.csv
```

Output:

![grep 'Paul,Ro' Output](pictures/grep-least-simple-string.png?classes=border)

This is a more specific string than the previous example.

Six records matched each last name started with `Ro` as dictated by the regular expression, but the rest of the name didn't matter which is why `Rogers`, `Robinson`, & `Rodriquez` all matched.

### Match `'Paul,Rogers'`

```bash
grep 'Paul,Rogers' user.csv
```

![grep 'Paul,Rogers' Output](pictures/grep-less-simple-string.png?classes=border)

This is an even more specific string resulting in even less results.

Two records matched:

1. `Paul,Rogers,richardmedina@exaxmple.org,Edward Jones`
2. `Paul,Rogers,richard72@example.org,mastercard`

**`grep` will parse the entire text and only return lines that contain the exact pattern provided**.

## More Specific Matching with Regex Concepts & Symbols

Regular Expressions are a very powerful tool. 

By learning the Regular Expression concepts and syntax you can create very specific patterns. Typically the more specific your pattern is, the better your result set will be.

This class doesn't really cover Regular Expressions, however we included some of the basics to show how to create better patterns by incorporating some RegEx basics.

## Content

{{% children %}}
