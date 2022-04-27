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

## Working with the user.csv Dataset

Using the user.csv Dataset complete the following requirements:

{{% notice note %}}
If you need to get the `user.csv` Dataset again you can do so with the following command:
```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv > user.csv
```
{{% /notice %}}

Filter the results of the `user.csv` so that you only match users by the name of `James` with an email ending in `.org` that work for `Boeing`.

{{% expand "Click Here for Solution" %}}
```bash
grep '^James' user.csv | grep '.org' | grep 'Boeing$'
```
{{% /expand %}}

Filter the results of the `user.csv` so that you only match users with the last name `Campbell` that work for the organization `Freedom pay`.

{{% expand "Click Here for Solution" %}}
```bash
grep "Campbell," user.csv | grep "Freedom pay"
```
{{% /expand %}}

{{% notice green "Bonus" "rocket" %}}
How would you filter the results of the `user.csv` so that you only match users with the first name `John` or `Paul` and have a last name beginning with the letter `J` or `S` that work for the organization `Express Scripts`?
{{% /notice %}}

{{% expand "Click Here for Answer" %}}
```bash
grep -E '^John,[J,S]|^Paul,[J,S]' user.csv | grep "Express Scripts"
```
{{% /expand %}}