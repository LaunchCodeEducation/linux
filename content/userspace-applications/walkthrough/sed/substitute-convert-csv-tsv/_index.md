---
title: "Substitute: Convert CSV to TSV"
date: 2021-04-06
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## `sed` substitute ',' with '\t'

Convert the user-data.corrected.csv to a tsv file:

Run:

```bash
sed 's/,/\t/g' user-data.corrected.csv > user-data.corrected.tsv
```

### Validation

```bash
ls
```

Output:

![ls output](pictures/ls.png?classes=border)

A new file exists: `user-data.corrected.tsv`.

Inspect it:

```bash
cat user-data.corrected.tsv
```

Output:

![cat user-data.corrected.tsv output](pictures/cat-tsv.png?classes=border)