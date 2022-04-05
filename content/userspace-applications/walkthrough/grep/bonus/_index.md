---
title: "Bonus Regular Expressions"
date: 2021-04-04
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: "" # UPDATE ANY TIME CHANGES ARE MADE
---

## At Least One, Possibly More `+`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/transaction?data_format=csv | grep '\$5[0-9]\+'
```

## Maybe One, Possibly More `*`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^Paula*'
```

## Match Exact Number `{}`


{{% notice green "Bonus" "rocket" %}}
```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paul'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paul$'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paula$'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paula*$'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paula\+$'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paula\{1\}$'
```

```bash
echo -e "Paul\nPaula\nPaulaaaaaa\nTim" | grep '^Paula\{6\}$'
```
{{% /notice %}}

## Regular Expression Groups `()`

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '\(Paul\|John\)'
```

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^\(Paul\|John\),'
```

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '\(Accenture\|Boeing|)$'
```