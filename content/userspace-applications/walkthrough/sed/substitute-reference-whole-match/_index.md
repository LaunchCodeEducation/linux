---
title: "Substitute: Reference Whole Match"
date: 2021-04-06
draft: false
weight: 125
---

## Whole Match Reference `&`

Using `sed` substitute you may want to keep the pattern you matched and simply add additional text to it. You can use the match reference symbol `&` to achieve this. 

Add `: PAID IN FULL` to each line ending in `Microsoft` as they have settled their fictional debts with us:

```bash
sed 's/Microsoft$/&: PAID IN FULL/' user-data.corrected.csv
```

Output (after scrolling up to find a line ending in `Microsoft`):

![sed 's/Microsoft$/&: PAID IN FULL/' user-data.corrected.csv output](pictures/sed-microsoft.png?classes=border)

{{% notice note %}}
This example could have been achieved with:

```bash
sed 's/Microsoft$/Microsoft: PAID IN FULL/' user-data.corrected.csv
```

However, there are some instances where you don't know the exact string that was matched because you gave a regex pattern, not an exact string. The following example covers this and introduces a new Regex concept.
{{% /notice %}}

## Match `Microsoft` or `Mastercard` and Reference

```bash
sed 's/\(Microsoft\|Mastercard\)$/&: PAID IN FULL/' user-data.corrected.csv
```

Output (after scrolling up to find both `Microsoft` and `Mastercard` records):

![sed 's/\(Microsoft\|Mastercard\)$/&: PAID IN FULL/' user-data.corrected.csv output](pictures/sed-microsoft-mastercard.png?classes=border)

In this case a Regex pattern was provided: `(Microsoft|Mastercard)$` instead of an exact string match `Microsoft$`. For the line where the match occurred when you used the match reference symbol: `&` it entered in the exact text that matched our pattern. 

There would have been no way to know which company would have matched, and you couldn't have hardcoded it like the example listed in the note above.

{{% notice green "Bonus" "rocket" %}}
This article introduced two new regex concepts:

- `()`: matching group
- `|`: logical or operator

Altogether: `(Microsoft|Mastercard)` creates a matching group where either `Microsoft` **or** `Mastercard` will match.
{{% /notice %}}