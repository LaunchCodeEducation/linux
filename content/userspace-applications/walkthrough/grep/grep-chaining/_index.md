---
title: "grep Chaining"
date: 2021-04-04
draft: false
weight: 125
---

## Chaining `grep`

We can even pass the output from a `grep` command to another `grep` command to build complex filter chains.

### Step One: Get our Dataset

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv
```

Output:

![](pictures/grep-chaining-one.png?classes=border)

25000 records is too much.

### Step Two: Filter Matches `'^John'`

Filter data to include only `'^John'`:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,'
```

Output:

![alt-text](pictures/grep-chaining-two.png?classes=border)

### Step Three: Filter Matches `'Microsoft$'`

Using the output from the previous filter, filter further to include lines that match `'Microsoft$'`.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,' | grep 'Microsoft$'
```

Output:

![](pictures/grep-chaining-three.png?classes=border)

### Step Four: Filter Matches `@example\.com`

Using the output from the previous filter, filter further to include lines that match `'@example\.com'`.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,' | grep 'Microsoft$' | grep '@example\.com'
```

Output:

![alt-text](pictures/grep-chaining-four.png?classes=border)