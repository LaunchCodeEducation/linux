---
title: "Regex: Matching Set"
date: 2021-04-04
draft: false
weight: 115
---

## Regular Expression Sets: `[]`

You may not want to match every character, but a large number of specific characters. RegEx gives you the ability to match any character in a given set by using the special bracket characters `[]`.

For example:

- match any lowercase letter `[a-z]`
- match any uppercase letter `[A-Z]`
- match any single digit `[0-9]`
- match a comma, period, or semicolon `[,.;]`
- match any case letter and the numbers 1-5 `[a-zA-Z1-5]`

You can build whatever set fits your specific needs.

### Match `'3[0-9]`

Match any two digit number starting with `3`.

```bash
grep '3[0-9]' user.csv
```

Output:

![grep '3[0-9]' user.csv output](pictures/grep-set-one.png?classes=border)

### Match `'3[5-9]'`

Match the numbers `35`, `36`, `37`, `38` and `39`.

```bash
grep '3[5-9]' user.csv
```

![grep '3[5-9]' user.csv output](pictures/grep-set-two.png?classes=border)

### Match `'^Paul,[A-F]'`

Match the beginning of the line, then exactly `Paul,` and then any uppercase letter between `A` and `F`.

```bash
grep '^Paul,[A-F]' user.csv
```

![grep '^Paul,[A-F]' user.csv Output](pictures/grep-set-three.png?classes=border)

{{% notice note %}}
RegEx sets give you fine tuned control over what can and cannot be matched.
{{% /notice %}}

{{% notice green "Bonus" "rocket" %}}
You can also define an exclusion set in RegEx.

Match the beginning of the line, then any character not in `A`, `E`, `I`, `O`, `U`.

```bash
grep '^[^AEIOU]' user.csv
```

The exclusion group symbol is a set with the `^` character. Making it very similar to the begin line anchor `^`.

{{% /notice %}}