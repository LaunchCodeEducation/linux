---
title: "Sed From STDIN"
date: 2021-04-06
draft: false
weight: 120
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## `sed` Johnson Family Email List

```bash
grep -E '^[^,]+,Johnson' user-data.csv | sed -E 's/[^,]+//4'
```

You don't like that hanging `,` let's chain another `sed substitute`:

```bash
grep -E '^[^,]+,Johnson' user-data.csv | sed -E 's/[^,]+//4' | sed 's/,//3'
```