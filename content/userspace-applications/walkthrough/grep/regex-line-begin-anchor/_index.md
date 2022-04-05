---
title: "Regex: Line Begin Anchor"
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

## Regular Expression Line Begin Anchor: `^`

You can match the beginning of a line with the Regular Expression line begin anchor: `^`.

Earlier `grep 'Paul'` matched lines that had `'Paul'` at any point in the line. If we want to match `'Paul'` at the very beginning of each line we could use the line begin anchor: `^`.

### Match `'^Paul'`

```bash
grep '^Paul' user.csv
```

Output:

![grep '^Paul' Output](pictures/grep-line-begin-anchor.png?classes=border)

Take note that **`Bianca,Paul,...` is not** in our matched lines.

### Match `'^Paul,'`

```bash
grep '^Paul,' user.csv
```

Output:

![grep '^Paul,' Output](pictures/grep-line-begin-anchor-two.png?classes=border)

Take note that **`Paula,Richardson,...` is not** in our matched lines.

{{% notice note %}}
Using the RegEx **line begin anchor** we have already created a pattern that is more effective than just searching for the string by itself.
{{% /notice %}}