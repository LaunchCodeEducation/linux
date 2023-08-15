---
title: "Bonus Regular Expressions"
date: 2021-04-04
draft: false
weight: 190
hidden: true
---

## At Least One, Possibly More `+`

```bash
curl -s https://launchcodelearning.org/api/walkthrough/transaction?data_format=csv | grep '\$5[0-9]\+'
```

## Maybe One, Possibly More `*`

```bash
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv | grep '^Paula*'
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
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv | grep '\(Paul\|John\)'
```

```bash
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv | grep '^\(Paul\|John\),'
```

```bash
curl -s https://launchcodelearning.org/api/walkthrough/user?data_format=csv | grep '\(Accenture\|Boeing|)$'
```