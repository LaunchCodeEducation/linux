---
title: "Regex: Matching Set"
date: 2021-04-04
draft: false
weight: 115
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: "" # UPDATE ANY TIME CHANGES ARE MADE
---

## Regular Expression Sets: `[]`

### Match `'3[0-9]`

```bash
grep '3[0-9]' user.csv
```

Output:

![grep '3[0-9]' user.csv output](pictures/grep-set-one.png?classes=border)

### Match `'3[5-9]'`

```bash
grep '3[5-9]' user.csv
```

![grep '3[5-9]' user.csv output](pictures/grep-set-two.png?classes=border)

### Match `'^Paul,[A-F]'`

```bash
grep '^Paul,[A-F]' user.csv
```

![grep '^Paul,[A-F]' user.csv Output](pictures/grep-set-three.png?classes=border)