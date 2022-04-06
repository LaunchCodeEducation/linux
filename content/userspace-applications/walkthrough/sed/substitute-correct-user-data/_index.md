---
title: "Substitute: Correct user-data.csv"
date: 2021-04-06
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## `sed` substitute 'mastercard' with 'Mastercard'

```bash
sed 's/mastercard/Mastercard/g' user-data.csv
```

```bash
grep 'mastercard' user-data.csv
```

```bash
sed 's/mastercard/Mastercard/g' user-data.csv > user-data.corrected.csv
```

### Validation

- grep
- cat

bonus: `git diff user-data.csv user-data.corrected.csv`
double bonus: `git diff user-data.csv user-data.corrected.csv | grep -A1 '^-'`

## `sed` substitute 'spectrum' with 'Spectrum'

## `sed` substitute 'Stephens-Griffin' with 'Stephens-Griffin-Matthews'