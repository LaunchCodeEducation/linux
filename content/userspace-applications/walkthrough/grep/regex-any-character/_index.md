---
title: "Regex: Any Character Symbol"
date: 2021-04-04
draft: false
weight: 110
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: "" # UPDATE ANY TIME CHANGES ARE MADE
---

## Regular Expression Any Character: `.`

You can use the any character reserved symbol (`.`) to instruct the Regular Expression pattern to match **any** single character.

### Match `'^.a'`

Let's match all lines that start with any character, but the second character must be the lowercase letter `a`:

```bash
grep '^.a' user.csv
```

Output:

![grep '^.a'](pictures/grep-any-character.png?classes=border)

{{% notice note %}}
This RegEx pattern `'^.a'` is combining the Line Begin Anchor and the match any character symbol `.`. RegEx allows you to mix and match the special syntax to create highly specific patterns.
{{% /notice %}}

### Match `'.7@example.com`

```bash
grep '.7@example.com' user.csv
```

Output:

![grep '.7@example'](pictures/grep-any-character-two.png?classes=border)

{{% notice note %}}
The match any character symbol provides great flexibility for all patterns.
{{% /notice %}}