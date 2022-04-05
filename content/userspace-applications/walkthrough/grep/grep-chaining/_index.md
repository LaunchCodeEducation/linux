---
title: "grep Chaining"
date: 2021-04-04
draft: false
weight: 125
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: "" # UPDATE ANY TIME CHANGES ARE MADE
---

## Chaining `grep`

We can even pass the output from a `grep` command to another `grep` command to build complex filter chains.

### Step One: Get our Dataset

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv
```

25000 records is too much.

### Step Two: Filter Matches `'^John'`

Filter data to include only `'^John'`:

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,'
```

### Step Three: Filter Matches `'Microsoft$'`

Using the output from the previous filter, filter further to include lines that match `'Microsoft$'`.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,' | grep 'Microsoft$'
```

### Step Four: Filter Matches `@example\.com`

Using the output from the previous filter, filter further to include lines that match `'@example\.com'`.

```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv | grep '^John,' | grep 'Microsoft$' | grep '@example\.com'
```