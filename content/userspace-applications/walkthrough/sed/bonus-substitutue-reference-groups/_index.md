---
title: "Bonus: Substitute: Reference Match Groups"
date: 2021-04-06
draft: false
weight: 130
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## BONUS

## Bonus: Reference Groups

### Enter a Nickname

```bash
cat user-data.csv | sed -E 's/(Phillip),(Holmes),/\1 "Phil",\2,/'
```

### Switch first_name & last_name columns

```bash
cat user-data.csv | sed -E 's/^([^,]+,)([^,]+,)/\2\1/'
```

## Switch all the columns around

```bash
cat user-data.csv | sed -E 's/^([^,]+),([^,]+),([^,]+),(.*)/\4,\2,\1,\3/'
```