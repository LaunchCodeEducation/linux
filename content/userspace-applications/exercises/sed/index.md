---
title: "Sed Exercises"
date: 2021-11-09T15:12:20-06:00
draft: false
weight: 115
---

## Questions and Answers

How do you run a substitute command with `sed`?

{{% expand "Click Here for Answer" %}}
```bash
sed 's/word-or-phrase-to-replace/replacement-word-or-phrase/' file-name
```
{{% /expand %}}

How do you use the substitute command to add additional text?

{{% expand "Click Here for Answer" %}}
```bash
sed 's/word-or-phrase/& additional-text-to-add/' file-name
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

Substitute all employers by the name of `Hunter Engineering` for `LaunchCode`

{{% expand "Click Here for Solution" %}}
```bash
sed 's/Hunter Engineering/LaunchCode/' user.csv
```
{{% /expand %}}

Substitute all email signatures (`@example.org, @example.net, @example.com`) for `@launchcode.org`

{{% expand "Click Here for Solution" %}}
```bash
sed 's/\(@example.org\|@example.net\|@example.com\)/@launchcode.org/' user.csv > launchcode-emails.csv
```
or
```bash
sed 's/@example.org/@launchcode.org/' user.csv | sed 's/@example.net/@launchcode.org/' | sed 's/@example.com/@launchcode.org/' > all-launchcode-emails.csv
```
{{% /expand %}}