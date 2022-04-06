---
title: "Substitute: Reference Whole Match"
date: 2021-04-06
draft: false
weight: 125
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-04-06 # UPDATE ANY TIME CHANGES ARE MADE
---

## Whole Match Reference `&`

```bash
cat user-data.csv | sed 's/Microsoft$/&: PAID IN FULL/'
```