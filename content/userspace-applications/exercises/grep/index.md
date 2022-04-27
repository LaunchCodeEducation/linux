---
title: "Grep Exercises"
date: 2021-11-09T15:12:20-06:00
draft: false
weight: 110
---

## Questions and Answers

What is the purpose of Grep?

{{% expand "Click Here for Answer" %}}
> Parse text and return lines that match specific patterns.
{{% /expand %}}

What are some common uses of Grep?

{{% expand "Click Here for Answer" %}}
- Search for file names matching a specific pattern in a directory
- Search contents of a file for specific patterns
- Search web request data for lines matching specific patterns
{{% /expand %}}

What character represents the `Line Begin Anchor`?

{{% expand "Click Here for Answer" %}}
`^`
{{% /expand %}}

What character represents the `Line End Anchor?`?

{{% expand "Click Here for Answer" %}}
`$`
{{% /expand %}}

What is the `Any Character Symbol`??

{{% expand "Click Here for Answer" %}}
`*`
{{% /expand %}}

How would you search a file for lines beginning with the phrase `John`?

{{% expand "Click Here for Answer" %}}
```bash
cat file-name | grep "^John"
```
{{% /expand %}}

How would you search a directory for only files ending in `.csv`?

{{% expand "Click Here for Answer" %}}
```bash
ls /path/to/directory | grep ".csv$"
```
{{% /expand %}}